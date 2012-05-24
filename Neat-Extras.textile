h1. Neat Extras

Besides the "well advertised feature set":https://github.com/xing/wysihtml5/#readme wysihtml5 offers some hidden gems that might be useful to developers (this is an uncomplete list).

* When the browser supports rich text formatting the <code><body></code> of the page receives a css class "wysihtml5-supported". This can be useful if you want to display some hints or activate certain UI elements.
* When the browser supports rich text formatting a hidden <code><input></code> with name "_wysihtml5_mode" and value "1" is inserted after the textarea. This can be used on the server side to specially treat wysihtml5 output after form submit.
* If within a <code><form></code> the editor hooks into the "reset" and "submit" events and ensures that the rich text element is in sync with the original <code><textarea></code>
* Following keyboard shortcuts are supported: bold (CTRL + B), italic (CTRL + I), underline (CTRL + U)