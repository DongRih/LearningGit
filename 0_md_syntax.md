# Learning Git

## 0. Markdown Syntax

### Headers

    #H1#
    ##H2
    ###....

Hashes after the header are optional.

### Blockqoutes

This

    >This is a blockqoute.
    >lorem ipsum

or this

    >This is a blockqoute.
    lorem ipsum
looks the same:

>This is a blockqoute.
>lorem ipsum

Blockqoutes can be nested

    >like
    >>this

as

    >     all
    >###  md syntax
    >1.   applies
    >     in qouted blocks.

### Lists

Lists

    1. can
    2. be
    3. ordered

    * or
    * not
    * or-
    +   der-
    -      ed

    1. or
       contain many lines
    2. really many lines

* which looks like this:
* In
  this
  sentence,
  each
  word
  starts
  a
  new
  line,

1. but the lines are automatically connected by the     engine.
2. That's because markdown recognizes paragraphs by     newlines.

Markdown syntax is highly flexible, so you should be aware of possible unintended lists like this:

1987. What a wonderful season!

use a backslash as escape:

    1987/. What a wonderful season!

### Codeblocks

 Simply use a tab to create one.

    like this

But remember to seprate it from other paragraphs.

### Horizontal Rules

    ------
    or
    ******

effect will be like this:

-------

### Links

    This is [an example](http://example.com/ "title to display when you move cursor on it") inline link.

This is [an example](http://example.com/ "title to display when you move cursor on it") inline link.

    Relative paths also work:
    See my [About](/about/) page for details.


See my [About](/about/) page for details.

    This is [an example][goo] reference-style link.

    lable form 1: [goo]: google.com "google"
               2: [goo]: google.com (google)

    Link label like above (on a line by itself) can be anywhere in the document.

This is [an example][goo] reference-style link.

[goo]: google.com "google"


    <automaticlinks.com>
<automaticlinks.com>

### Emphasis

    text text *emphasis level 1* text text _another form_

text text *emphasis level 1* text text _another form_

    text text **level 2** text text __also lv.2__

text text **level 2** text text __also lv.2__

### Code Blocks

* Use **two** backticks(`) to include inline code:

        use ``printf()`` function
    use ``printf()`` function



* Use **four** to form a code block:

        ```` c
        int main(){
        printf("test");
        return 0;
        }
        ````

    ```` c
    int main(){
       printf("test");
       return 0;
    }
    ````

### Pics

    ![Alt text](/path/to/img.jpg "Optional title")

![Alt text](/path/to/img.jpg "Optional title")

    ![Alt text][id]
    [id]: url/to/image  "Optional title attribute"

![Alt text][id]

[id]: url/to/image  "Optional title attribute"


