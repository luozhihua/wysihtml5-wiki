1. Include scripts

`<!-- wysihtml5 parser rules --> <script src="/path-to-wysihtml5/parser_rules/advanced.js"></script>`
`<!-- Library --> <script src="/path-to-wysihtml5/dist/wysihtml5-0.3.0.min.js"></script>`

The first script contains the html5 parser rules that are needed for wysihtml5 in order to create valid and desired markup.
Either use one of the existing parser rules sets or create your own.
Check the advanced.js parser rules for details.
The second script is the minified wysihtml5 library. It’s located in the dist folder of this repository.
2. Create a textarea
<form><textarea id="wysihtml5-textarea" placeholder="Enter your text ..." autofocus></textarea></form>
wysihtml5 takes a textarea and transforms it into a rich text editor. The textarea acts as a fallback for unsupported browsers (eg. IE < 8). Make sure the textarea element has an id, so we can later access it easily from javascript.
The resulting rich text editor will much behave and look like the textarea since behavior (placeholder, autofocus, …) and css styles will be copied over.

Please note: The textarea will always hold the editor’s generated markup. Therefore wysihtml5 integrates smoothly with forms.

3. Create a toolbar
<div id="wysihtml5-toolbar" style="display: none;">
  <a data-wysihtml5-command="bold">bold</a>
  <a data-wysihtml5-command="italic">italic</a>
  
  <!-- Some wysihtml5 commands require extra parameters -->
  <a data-wysihtml5-command="foreColor" data-wysihtml5-command-value="red">red</a>
  <a data-wysihtml5-command="foreColor" data-wysihtml5-command-value="green">green</a>
  <a data-wysihtml5-command="foreColor" data-wysihtml5-command-value="blue">blue</a>
  
  <!-- Some wysihtml5 commands like 'createLink' require extra paramaters specified by the user (eg. href) -->
  <a data-wysihtml5-command="createLink">insert link</a>
  <div data-wysihtml5-dialog="createLink" style="display: none;">
    <label>
      Link:
      <input data-wysihtml5-dialog-field="href" value="http://" class="text">
    </label>
    <a data-wysihtml5-dialog-action="save">OK</a> <a data-wysihtml5-dialog-action="cancel">Cancel</a>
  </div>
</div>
The toolbar contains the formatting options. Make sure the toolbar element has an id and has display: none.

Please note: wysihtml5 supports many more formatting commands. Check the advanced demo or find a full list of all supported commands here.

4. Initialize wysihtml5
<script>
var editor = new wysihtml5.Editor("wysihtml5-textarea", { // id of textarea element
  toolbar:      "wysihtml5-toolbar", // id of toolbar element
  parserRules:  wysihtml5ParserRules // defined in parser rules set 
});
</script>
wysihtml5 supports many more configuration options.

5. Use a set of CSS classes to style the editor’s content
Browsers use a default style sheet to style elements, so if you use b, i, ul and li, there is already some styling visible in the editor.

But for the colors, we use classes like .wysiwyg-color-fuchsia, and for floats, we use .wysiwyg-float-right or -left.

See the CSS of the advanced demo (see the whitelist of allowed classes). You can add these classes with the stylesheets – configuration option (when you initialize wysihtml5, see above), i.e.

stylesheets: ["css/reset.css", "css/editor.css"]
The stylesheets are linked from within the head of the iframe’s content then.

6. There you go
Congrats you just integrated wysihtml5 into your website.
Now enjoy a cold beer.
Last edited by dharmavir, a month ago
Delete this Page