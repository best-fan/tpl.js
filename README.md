## tpl.js
Lightweight javascript template engine. Adaptation AMD, CMD and global environment

## Usage

1. Include `tpl.js`:
``` html
    <script type="text/javascript" src="path/to/tpl.js"></script>
```
Or in sea.js, you can include by: `var tpl = require('path/to/tpl');`


2. Template in your html:
``` html
    <script type="text/template" id="demo">
        <p>Hi, I'm <%=$.author%></p>
        <p>I can write:
        <% for(var i=0; i<$.languages.length; i++) { %>
        <%=(i===0?"":",")+$.languages[i]%>
        <%}%>
        </p>
    </script>
```
Or use internal method `echo()`:
``` html
    <script type="text/template" id="demo">
        <p>Hi, I'm <%=$.author%></p>
        <p>I can write:
        <% 
        for(var i=0; i<$.languages.length; i++) { 
            echo( (i===0?"":", ") + $.languages[i] );
        }%>
        </p>
    </script>
```
    

3. Execution rendering:
``` js
    tpl('#demo', {author: "Jony", languages: ["javascript", "php", "shell"]});
```

4. Result is:
<p>Hi, I'm Jony</p>
<p>I can write: javascript, php, shell</p>


## Browser Support

  * IE6+
  * Chrome
  * Safari 4+
  * Firefox 3.5+
  * Opera

## Bugs / Contributions
- [Report a bug](https://github.com/niceue/tpl.js/issues)
- To contribute or send an idea, github message me or fork the project

## Build
tpl.js use [UglifyJS2](https://github.com/mishoo/UglifyJS) 
you should have installed [nodejs](nodejs.org) and run `npm install uglify-js -g`.

On Windows, you can run `build.bat` from root directory and it will package `tpl.debug.js` into `tpl.js`.

  
## License

tpl.js is available under the terms of the [MIT License](https://github.com/niceue/tpl.js/blob/master/LICENSE.txt).
