---
title: How To Markdown
date: 2020-05-18 10:40
categories: web howto markdown
---
*note. This page is a work in progess.*
# 0 Index


# 1 What is Markdown

Markdown is a lightweight language that transforms simple, plain text to HTML and others.

# 2 Syntax
## 2.1 Titles and subtitles
### 2.1.1 Heading

To mark a heading, use equal signs `=` below the text.

    This is a heading.
    ==================

This is a heading.
==================

### 2.1.2 Sub-heading

To mark a sub-heading, use hyphens `-` below the text.

    This is a sub-heading.
    ----------------------

This is a sub-heading.
----------------------

### 2.1.3 Explicit headers

To use explicit headers, use hash-tags `#` .

    # This is h1.
    ## This is h2.
    ### This is h3.
    #### This is h4.
    ##### This is h5.
    ###### THis is h6.

# This is h1.
## This is h2.
### This is h3.
#### This is h4.
##### This is h5.
###### THis is h6.

## 2.2 Page layout
### 2.2.1 Paragraphs

Paragraphs are separated by a blank line.

    This is the first paragraph.
  
    This is the second paragraph.
    Without a blank line, it's in the same paragraph.

This is the first paragraph.

This is the second paragraph.
Without a blank line, it's in the same paragraph.

### 2.2.2 Line break
--------------
A line break is marked by two spaces at the end.

    This is the first line  
    and this is the next line.
    Without two spaces, the line continues.
    Like so.

This is the first line  
and this is the next line.
Without two spaces, the line continues.
Like so.

### 2.2.3 Horizontal line
--------------
To use a horizontal line, use any of the following

    ***  
    * * *  
    ---  
    - - -  
  

***
* * *
---
- - -
  
## 2.3 Text emphasis
### 2.3.1 Bold letters

To use bold letters, wrap the text in two asterisks `**` or two underscores `__` .

    The following word is in **bold**.
    The next word is also in __bold__.

The following word is in **bold**.  
The next word is also in __bold__.

### 2.3.2 Italic letters

To use italic letters, wrap the text in single asterisk `*` or single underscore `_`.

    The following word is in *italic*.
    The next word is also in _italic_.

The following word is in *italic*.  
The next word is also in _italic_.

### 2.3.3 Strikethrough

To use a strikethrough, wrap the text in two tildes `~~` .

    The following word has a ~~strikethrough~~.
  
The following word has a ~~strikethrough~~.

### 2.3.4 Monospace

To use a monospace, wrap the text in a backquote ` ` `.

    The following word is in `   mono space        `.

The following word is in `   mono space        `.

## 2.4 Data representation
### 2.4.1 Code block

To use a code block, use any of the following to begin your code.

1. four spaces(or one tab)
2. `<pre><code>your code</code></pre>`
3. triple back quotes ````

This is plain text.

    This is a code block.
    Code block runs until it meets a plain text.

Back to plain text.  
You can also note the specific language of the code to enable syntax highlighting.

```html
<a href="">This code is in html.</a>
```

```javascript
alert('This code is in javascript.');
```

```java
System.out.println("This code is in java");
```

### 2.4.2 Block quotes

To use block quotes, begin your quotes with `>`.

    > This is a block quotes.
    >    > Block quotes can be layered.
    >    >    > Use four spaces or one tab to leyer a block quote.

> This is a block quotes.
>    > Block quotes can be layered.
>    >    > Use four spaces or one tab to leyer a block quote.

### 2.4.3 Ordered lists

To use ordered lists, begin your text with a number and a dot.

    1. First item in the list.
    3. Second item in the list.
    2. The number you type does not mean its sequence. It can be any numbers.

1. First item in the list.
3. Second item in the list.
2. The number you type does not designate its sequence. It can be any numbers.

### 2.4.4 Unordered lists

To use unordered lists, begin your text using any of the following in any sequence.

    * Top item
        + Middle item
            - Bottom item

* Top item
    + Middle item
        - Bottom item

### 2.4.5 Tables

To mark a table, use `|` to separate columns,  
use  three `-` or more to separate heders,  
use linebreak to separate any other rows.  
You can also set alignment by using `:` under your headers.


    |Header|Col1|Col2|
    |:---|:------:|-------:|
    |row1|data 1.1|data 1.2|
    |row2|data 2.1|data 2.2|

|Header|Column 1|Column 2|
|----|--------|--------|
|row1|data 1.1|data 1.2|
|row2|data 2.1|data 2.2|

## 2.4.6 Links

To use links, denote the keyword in brackets `[ ]` and the url in parantheses `( )`.

    The following word has a [link](www.google.com) to google.
    You can also write an optional title to your [link](www.google.com "This is google.").

The following word has a [link](www.google.com) to google.
You can also write an optional title to your [link](www.google.com "This is google.").

### 2.4.7 Images

To mark an image, denote alternative text in brackets `[ ]` and the image url in parantheses `( )`.

    [Google](https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_92x30dp.png)
    [Google](https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_92x30dp.png "This is the Google logo.")
    

