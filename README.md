# mediumEditor-codemode
Extension for code blocks in [mediumEditor](https://github.com/yabwe/medium-editor) for javascript.  I developed this for my own website to embed small code snippets.  It can be combined with a syntax highlighting script such as [Prism.js](http://prismjs.com/).  The code is clunky and very rough around the edges, so feel free to fork your own version or send in a pull request if you'd like to tidy it up.

## Usage

If you'd like to have a combobox on each code block to set the programming language, then you need to define a list of languages to support like this:

    const languages = ['c-like', 'css', 'javascript', 'markup'];
    addLanguageDropdown(languages); // addLanguageDropdown creates the combo-box for
                                    // all existing code blocks.  codemode will
                                    // automatically call it again whenever it adds
                                    // another code block.
    
This is just to provide information to a syntax highlighting script.  codemode doesn't have any special support for formatting any particular programming language.

Next, initialise mediumEditor like this.

      const editor = new MediumEditor('#element-to-edit', {
        toolbar: {
          buttons:['bold', 'italic', 'anchor', 'h2', 'h3', 'quote', 'code']
        },
        extensions: {
          'code': new CodeButton()
        }
      });

You need to add `'code': new CodeButton()` to the extensions list, and `'code'` to the list of buttons.

That's it.  Now you have some (admittedly janky) support for source code blocks in your mediumEditor.

