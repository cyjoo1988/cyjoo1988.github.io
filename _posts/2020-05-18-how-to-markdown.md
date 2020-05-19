---
title: How To Markdown
date: 2020-05-19 10:00
categories: web howto markdown
---

# 0. Index
1. What is Markdown
2. Syntax
  * 2.1 Titles and subtitles  
  * 2.2 Page layout  
  * 2.3 Text emphasis  
  * 2.4 Data representation  

-------

# 1. What is Markdown

Markdown is a lightweight language that transforms simple, plain text to HTML and others.

# 2. Syntax
## 2.1 Titles and subtitles
### 2.1.1 Heading

To mark a heading, use equal signs `=` below the text.  
`Code:`  

    This is a heading.
    ==================

`Output:`  

This is a heading.
==================

-------

### 2.1.2 Sub-heading

To mark a sub-heading, use hyphens `-` below the text.  
`Code:`  

    This is a sub-heading.
    ----------------------

`Output:`  

This is a sub-heading.
----------------------

-------

### 2.1.3 Explicit headers

To use explicit headers, use hash-tags `#` .  
`Code:`  

    # This is h1.
    ## This is h2.
    ### This is h3.
    #### This is h4.
    ##### This is h5.
    ###### This is h6.

`Output:`  
# This is h1.
## This is h2.
### This is h3.
#### This is h4.
##### This is h5.
###### THis is h6.

-------

## 2.2 Page layout
### 2.2.1 Paragraphs

Paragraphs are separated by a blank line.  
`Code:`  

    This is the first paragraph.
  
    This is the second paragraph.  
    Without a blank line, it's in the same paragraph.

`Output:`  
This is the first paragraph.

This is the second paragraph.  
Without a blank line, it's in the same paragraph.

-------

### 2.2.2 Line break

A line break is marked by two spaces at the end.  
`Code:`  

    This is the first line  
    and this is the next line.
    Without two spaces, the line continues.
    Like so.

`Output:`  
This is the first line  
and this is the next line.
Without two spaces, the line continues.
Like so.

-------

### 2.2.3 Horizontal line

To use a horizontal line, use any of the following  
`Code:`  

    ***  
    * * *  
    ---  
    - - -  

`Output:`  
***
* * *
---
- - -
  
## 2.3 Text emphasis
### 2.3.1 Bold letters

To use bold letters, wrap the text in two asterisks `**` or two underscores `__` .  
`Code:`  

    The following word is in **bold**.
    The next word is also in __bold__.

`Output:`  
The following word is in **bold**.  
The next word is also in __bold__.

-------

### 2.3.2 Italic letters

To use italic letters, wrap the text in single asterisk `*` or single underscore `_`.  
`Code:`  

    The following word is in *italic*.
    The next word is also in _italic_.

`Output:`  
The following word is in *italic*.  
The next word is also in _italic_.

-------

### 2.3.3 Strikethrough

To use a strikethrough, wrap the text in two tildes `~~` .  
`Code:`  

    The following word has a ~~strikethrough~~.

`Output:`  
The following word has a ~~strikethrough~~.

-------

### 2.3.4 Monospace

To use a monospace, wrap the text in a backquote `` ` ``.  
`Code:`

    The following word is in `   mono space        `.

`Output:`  
The following word is in `   mono space        `.

You can escape a backquote by wraping it with more backquotes.  
`Code:`  

    This is a backquote `` ` ``.  
    These are backquotes ```` `` ````.

`Output:`  
This is a backquote `` ` ``.  
These are backquotes ```` `` ````.

-------

## 2.4 Data representation
### 2.4.1 Code block

To use a code block, you can use;

1. four spaces(or one tab) at the beginning of each line
2. wrap your code as follows; `<pre><code>your code</code></pre>`
3. wrap your code in triple back quotes ```` ``` ````

This is plain text.

    This is a code block.
    It is advised to separate plain text and code blocks with at least one blank line.

Back to plain text.  

You can also note the specific language of the code to enable syntax highlighting.

`HTML`  

```html
<div>
    <a href="" _blank id="someId">This code is in html.</a>
</div>
```

`JS`  

```javascript
function someFunction() {
    var str = 'This code is in javascript.';
    alert(str);
}
```

`Java` 

```java
public class SomeClass {
    public static void main(String[] args) {
        String str = "This code is in java.";
        System.out.println(str);
    }
}
```

-------

### 2.4.2 Block quotes

To use block quotes, begin your quotes with `>`.  
`Code:`  

    > This is a block quote.
    >    > Block quotes can be nested.
    >    >    > Use four spaces or one tab within the quote followed by > to mark a nested block quote.

`Output:`  
> This is a block quote.
>    > Block quotes can be nested.
>    >    > Use four spaces or one tab within the quote followed by > to mark a nested block quote.

-------

### 2.4.3 Ordered lists

To use ordered lists, begin your text with a number and a dot.  
`Code:`  

    1. First item in the list.
    3. Second item in the list.
    2. The number you type does not mean its sequence. It can be any numbers.

`Output:`  
1. First item in the list.
3. Second item in the list.
2. The number you type does not designate its sequence. It can be any numbers.

-------

### 2.4.4 Unordered lists

To use unordered lists, begin your text using any of the following in any sequence `*` `+` `-`.  
`Code:`  

    * Top item
        + Middle item
            - Bottom item

`Output:`  
* Top item
    + Middle item
        - Bottom item

-------

### 2.4.5 Tables

To mark a table, use `|` to separate columns,  
use  three `-` or more to separate heders,  
use linebreak to separate any other rows.  
You can also set alignment by using `:`.  
`Code:`  

    |Header|Column 1|Column 2|
    |:---|:------:|-------:|
    |row1|data 1.1|data 1.2|
    |row2|data 2.1|data 2.2|

`Output:`  
|Header|Column 1|Column 2|
|:---|:------:|-------:|
|row1|data 1.1|data 1.2|
|row2|data 2.1|data 2.2|

-------

## 2.4.6 Links

To use links, denote the keyword in brackets `[ ]` and the url in parantheses `( )`.  
`Code:`  

    The following word has a [link](www.google.com) to google.  
    You can also write an optional title to your [link](www.google.com "This is google.").

`Output:`  
The following word has a [link](www.google.com) to google.  
You can also write an optional title to your [link](www.google.com "This is google.").

-------

### 2.4.7 Images

To mark an image, denote alternative text in brackets `[ ]` and the image url in parantheses `( )`.  
`Code:`  

    [Google](https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_92x30dp.png)  
    [Google](https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_92x30dp.png "This is the Google logo.")
    
`Output:`  
[Google](https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_92x30dp.png)  
[Google](https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_92x30dp.png "This is the Google logo.")

***
**END OF DOCUMENT**
***
