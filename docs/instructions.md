# How to write instructions

Instructions can be written in [Markdown](https://commonmark.org/help/) (we use
[Marked](https://marked.js.org/) for parsing, so you can
[try the demo to validate your Markdown](https://marked.js.org/demo/)), HTML,
or plain text.

### Markdown
To use our Markdown renderer, simply name your files with a .md extension.
Markdown can also contain arbitrary HTML, so you can add additional
customizations not possible through standard markdown. We use Markdown for most
of our packs since it's simpler to write than HTML but still has support for
better styling, linking, etc., than plain text.

### HTML
To use our HTML renderer, simply name your files with a .html extension.

### Plain Text
To use our plain text renderer, simply name your files with a .txt extension.
We do render the text monospaced, so various ASCII art is fair game!
```
  |\_/|
 / @ @ \
( > º < )
 `>>x<<´
 /  O  \
```
Be sure to wrap long lines, since we don't do that for you.

### Multiple files
We support having multiple files. They will be served with the names you create,
minus extensions. (e.g. to access index.md, either refer to `/` or to `/index`,
but not to `/index.html`. To reference [another file](./index), simply add a link
to `./<filename>`. 

We do _not_ currently support nested directories of files in the documentation
folder.
