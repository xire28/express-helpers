# Express Helpers

Express Helpers is a port of EJS's ViewHelpers.


## Features

Express Helpers provides view helpers for common tasks. These helpers are very similar to those found in the Ruby on Rails framework.

* date_tag
* time_tag
* date_time_tag
* css_tag
* checkbox_tag
* form_tag
* form_tag_end
* hidden_field_tag
* img_tag
* input_field_tag
* js_tag
* label_for
* link_to
* link_to_if
* link_to_unless
* password_field_tag
* radio_tag
* select_tag
* submit_tag
* text_area_tag/text_tag
* text_field_tag

## Installation

    npm install express-helpers
    
    
## How to use

Require express and create a server.

    var express = require('express');
	var app = express.createServer();

To automatically inclue all helpers initialize like this

	var helpers = require('express-helpers')(app);

If you want to only use some helpers require without the app and register necessary view helpers...
	
	var helpers = require('express-helpers')();

    app.helpers({
      date_tag: helpers.date_tag
    });

## Details


### date_tag(name, [value, html_options])
Creates a date tag

    date_tag('Installation[date]', new Date(1982, 10,20) )
    date_tag('Installation[date]') // just on current time
	
### time_tag(name, [value, html_options])
Creates a time tag

    time_tag('Installation[time]', new Date(1982, 10,20) )
    time_tag('Installation[time]') // just on current time
	
### date_time_tag(name, [value, html_options])
Creates a time tag

    date_time_tag('Installation[time]', new Date(1982, 10,20) )
    date_time_tag('Installation[time]') // just on current time

### css_tag(src, html_options)
Creates a css tag

	css_tag('/stylesheet/style.css') =>
	"<link rel='stylesheet' 
			   href='/stylesheet/style.css' 
			   type='text/css' 
			   charset='utf-8' />"
			   
### checkbox_tag(name, value, html_options)
Creates a checkbox

	checkbox_tag('user_check_box', 'user') => 
	"<input id='user_check_box' value='user' type='checkbox' name='user_check_box' />"

### radio_tag(name, value, html_options)
Creates a radio button

	radio_tag('user_radio', 'user')  =>
	"<input id='user_radio' value='user' type='radio' name='user_radio' />"

### form_tag(action, html_options)  
Creates a start form tag.

    form_tag('/myaction',{multipart: true}) 


### end_form_tag() 
Creates a end form tag.

    form_tag_end()


### hidden_field_tag( name,  value,  html_options)
Creates a hidden field.

	hidden_field_tag('something[interesting]', 5) => 

    "<input id=\'something[interesting]\' 
            value=\'5\' 
            type=\'hidden\' 
            name=\'something[interesting]\'/>"


### img_tag
Creates an image tag.

    img_tag('/some.png', 'something') => "<img src='/some.png' alt='something' />"


### input_field_tag
Creates an input field tag.

    input_field_tag('something[interesting]', 5) => 

    "<input id='something[interesting]' 
            value='5' 
            type='text' 
            name='something[interesting]'/>"

### js_tag
Creates a javascript script tag

	js_tag('/javascript/script.js') =>
	"<script type='text/javascript' 
				  src='/javascript/script.js' 
				  charset='utf-8' ></script>"
				  
### label_for
Creates a label for tag
	
	label_for('user_id') => "<label for=\'user_id\' >User</label>"
     
	label_for('book[user_id]') => "<label for=\'book[user_id]\' >User</label>"

### link_to
Creates a link to another page.

    link_to('hello world', '/something/here') => "<a href='/something/here' >hello world</a>"

### link_to_if(condition, name, url, html_options, post, block)
Just like link_to if the condition is true. If condition is false it returns name.

### link_to_unless(condition, name, url, html_options, block)
Just like link_to if the condition is false. If condition is true it returns name.

### password_field_tag
Returns a password field.

    password_field_tag('something[interesting]', 5) => 

    "<input id='something[interesting]' 
            value='5' 
            type='password' 
            name='something[interesting]'/>"



### select_tag
Returns a select tag.

    var choices = [ {value: 1,    text: 'First Choice' }, 
                    {value: 2,    text: 'Second Choice'},
                    {value: 3,    text: 'Third Choice'}  ]
    select_tag('mySelectElement', 2,  choices) => 
    
    "<select id='mySelectElement' value='2' name='mySelectElement'>
        <option value='1' >First Choice</option>
        <option value='2' selected='selected'>Second Choice</option>
        <option value='3'>Third Choice</option>
     </select>"

### submit_tag
Creates a submit tag.

    submit_tag('Submit') => "<input type=\'submit\' value=\'Submit\' />"
	
	submit_tag('holla', '/new/location') =>    
	
	"<input onclick='window.location=\"/new/location\";return false;' 
            value='holla' 
            type='submit' />"

### text_area_tag / text_tag
Both create a text area tag

    text_area_tag('task[description]', 'Here is some text.\nA new line.') =>
    text_tag('task[description]', 'Here is some text.\nA new line.') =>
	
    "<textarea id='task[description]' 
               name='task[description]' 
               cols='50' 
               rows='4' >Here is some text.\nA new line.</textarea>"



### text_field_tag

    text_field_tag('something[interesting]', 5) => 

    "<input id='something[interesting]' 
            value='5' 
            type='text' 
            name='something[interesting]'/>"

## License

(The MIT License)

EJS - Embedded JavaScript

Copyright (c) 2007 Edward Benson 

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.


Ported by Masahiro Hayashi <hayashi.masahiro@gmail.com>

