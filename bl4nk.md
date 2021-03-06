# BL4NK

BL4NK is a great starting point for a new Joomla!™ template project. It's a fully functional template \(can be installed directly\) and has responsive support. Internet Explorer is obsolete, HTML5 and CSS3 are the present. And that is how I build BL4NK. HTML5 tags can be used that all browsers correctly interpret. The CSS file [Normalize.css](http://necolas.github.io/normalize.css/) is to all values neutral and independently to render by the browser. It is a advanced HTML5 alternative to the last CSS resets. All style sheets will be combined in one file and load compressed, which are compiled by [Gulp](https://gulpjs.com/) before. The browser loads only a single CSS file with just one line. You can't get it any faster than that.

To write your CSS you can choose between [LESS](http://lesscss.org/) and [SASS](https://sass-lang.com/). Wait a moment, you don't know both? LESS and Sass are preprocessors of CSS. Similar to PHP and HTML you can write code with them that will put out clear CSS. You will use LESS or SASS to write CSS more effective. You can use variables, e.g. to use the same hexadecimal color values on different points. There are a lot of functions, also, and much more. We will get it later.

Then there is a [BL4NK Bootstrap Edition](https://github.com/Bloggerschmidt/Blank-Bootstrap-Edition) \(short BBE\). For those of you who don't know [Bootstrap](http://getbootstrap.com/): you should! Bootstrap allows you to design a template responsive with mobile-first strategy. If you are using the grid system your template will be responsive for desktops, tabletts and smartphones. Frameworks and APIs \(Applications Programming Interfaces\) make your life easier. If you are use them, your coding will be much faster as stand alone coding.

## Features

* Loading brutally fast
* Start browsing through constant normalize.css
* CSS compressor
* Integrated LESS and SASS compiler
* Support for desktops, tablets and smartphones
* Own error, offline and print pages
* [BL4NK Bootstrap Edition](https://github.com/Bloggerschmidt/Blank-Bootstrap-Edition)
* Great icons in Bootstrap with Font Awesome

## Photoshop files

Download [psd.zip](http://itr.im/psd) \(10.8 MB\) to create icons and preview images faster. The ZIP package contains the following files:

* App Icon Template \[2.0\] .psd
* template\_preview.psd
* template\_thumbnail.psd

All files in Blank, starting with the most important file named index.php until favicon.ico will be explained in the following. However, as said by Sherlock Holmes: "To a great mind, nothing is little". And so it is. Every detail is important!

Following the Unix principle, each file is a text file and can be opened and edited with your editor. Okay, okay - for image files you'd rather use an image editing program.

## File structure

Have you downloaded the Blank Template and unpacked, find you the following folders and files:

* build
* css
* js
* .gitignore
* component.php
* error.php
* favicon.ico
* gulpfile.js
* index.php
* logic.php
* offline.php
* package.json
* README.md
* template\_preview.png
* template\_thumbnail.png
* templateDetails.xml

Strictly speaking, you only need two files to create a working template:

* index.php
* templateDetails.xml

Combining these two files gives you [Mini](https://github.com/Bloggerschmidt/Mini), the template with the smallest possible number of files. Follow the idea of minimalism further and look for the smallest index.php in the world.

## index.php \(Mini\)

The index.php file is the core of the template. This makes all the files work together. It is crucial for the source code responsible and ultimately it's all about the source to create and influence.

The minimal structure of the index.php looks like this:

```markup
<?php defined('_JEXEC') or die; ?>
<!doctype html>
<html>
  <head>
    <jdoc:include type="head" />
  </head>
  <body>
    <jdoc:include type="message" />
    <jdoc:include type="component" />
  </body>
</html>
```

The first line is written in PHP. The good thing about PHP and HTML is that it can be written together. You can add PHP statements in an HMTL file, and vice versa. `<?php` opens a PHP statement - no matter where - and `?>` closes it again. In the first line we forbid direct access to this file. This is done via the Joomla!™ API with the `_JEXEC` command. This statement checks if the file is being called from within a Joomla!™ session and it protects your site by making it more difficult for a hacker to damage your site.

On line two we declare with `<!doctype html>` the document type. This line is one of the many little improvements in HTML5. Before HTML5 cryptic document types had to be declared for each different version and every application. Long arcane lines of code, impossible to jot down from memory. This was necessary to ensure browsers correctly interpret the source code. With HTML5 that's over, because it is backward compatible.

What follows in line three, is the smallest possible construction of a HTML page. This page is opened with `<html>` and ends with `</html>`. The header section begins with `<head>` and ends with `</head>`. The body starts with `<body>` and ends with `</body>`. Within the header area while we load the header information with `<jdoc: include type="head" />` from the Joomla!™ \(API\) in line five. This `jdoc:include` command will include the normal header information a website needs. It is a Joomla!™ statement that picks up the necessary bits from your Joomla!™ configuration. For example, the global metadata of the system load, the css stylesheets, JavaScripts and the RSS feeds.

The `jdoc:include` command you'll find twice more in the index.php: once as message type and then as a component type \(on lines 8 and 9\). In line eight we see `<jdoc:include type="message" />`, this makes the system messages work. Whenever Joomla!™ needs to talk to you, this line will show it on your screen. For example, if you send an email on a contact form, you'll see the message “your message has been successfully send” after you hit the send button.

Last item to discuss is `<jdoc:include type="component" />` in line nine. This element should only appear once in the `<body>` element of the template to render the main content of the page with respect to the current page being viewed. So, enough explained. This is how the generated source looks like:

```markup
<!doctype html>
<html>

<head>
  <base href="http://localhost/joomla/" />
  <meta http-equiv="content-type"
        content="text/html; charset=utf-8" />
  <meta name="generator" content="Joomla! ..." />
  <title>Home</title>
  <link href="http://localhost/joomla/?view=featured"
        rel="canonical" />
  <link href="/joomla/index.php?format=feed&amp;type=rss"
        rel="alternate" type="application/rss+xml"
        title="RSS 2.0" />
  <link href="/joomla/index.php?format=feed&amp;type=atom"
        rel="alternate" type="application/atom+xml"
        title="Atom 1.0" />
  <link href="/joomla/templates/frontend/favicon.ico"
        rel="shortcut icon"
        type="image/vnd.microsoft.icon" />
  <script src="/joomla/media/system/js/mootools-core.js"
        type="text/javascript"></script>
  <script src="/joomla/media/system/js/core.js"
        type="text/javascript"></script>
  <script src="/joomla/media/system/js/caption.js"
        type="text/javascript"></script>
  <script type="text/javascript">
    window.addEvent('load', function() {
      new JCaption('img.caption');
    });
  </script>
</head>

<body>
  <div id="system-message-container">
    <div id="system-message"></div>
  </div>
  <div class="blog-featured">
    <div class="page-header">
      <h1>Home</h1>
    </div>
  </div>
</body>

</html>
```

The code begins with the document type `<!doctype html>` on line one. Followed by the `<html>` tag on line two. The next line, line three, begins the header information with `<head>`. Here the header information loaded \(base, meta, title, link and script\). In the body `<body>` to display a div an `id="system-message-container"` for system messages and the div `class="blog featured"` for the actual content. In the last div \(line 25\) the article title as the title as a first degree heading \(h1\) is generated.

This source-code comes from the default settings of a content-less Joomla!™ installation. The global meta-data \(keywords and description\) are not defined and are therefore not displayed. In the previous main-menu the entry "Home" is responsible for the title and heading. This entry is specified as a blog layout hence the class "blog-featured" with activated feed display. Therefore the links in the head-section are titled "RSS 2.0" and "Atom 1.0". On the remaining source-code - for now - you don't have an impact on the backend. At a later stage you will get a chance to take influence on the meta tag called "generator" with code snippets and to take out unneeded JavaScripts. Besides JavaScripts belong to the end of the HTML page before the closing body tag `</body>`. To increase performance, all JavaScripts should be loaded combined and compresses into a single file. There are exceptions, such as the JavaScript modernizr.js, which expressly is to be included in the head-section `<head>`. So much for the generated source code of the minimal index.php.

## templateDetails.xml \(Mini\)

The file templateDetails.xml \(note the capital D\) is the second most important file after index.php within the template. The templateDetails.xml includes general template information \(name, author, etc.\) and defines the installation routine. The installation routine is nothing else than a listing of all folders and files that belong to the template, in order to have them unpacked and stored with the installation. Additionally the module positions are stored here in order to be integrated via the `jdoc:include` command in the index.php. Optionally, you can create parameters to make the template adjustable within the backend. Perhaps you want your template to shine in different colours, then you adjust those parameters. How about a pretty pink as in the BEEZ template \(Joomla!™ 1.5\), for example?

Now please, check out the minimum version of templateDetails.xml:

```markup
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE install Public "-//Joomla! 2.5//DTD template 1.0//EN"
  "http://www.joomla.org/xml/dtd/1.6/template-install.dtd">

<extension version="3.8" type="template" method="upgrade">
   <name>mini</name>
   <creationDate>14.01.14</creationDate>
   <author>Alexander Schmidt</author>
   <copyright>Copyright © 2018 Alexander Schmidt</copyright>
   <authorEmail>alexander.schmidt@edvas.de</authorEmail>
   <authorUrl>https://alexanderschmidt.info</authorUrl>
   <version>1.0.0</version>
   <description>The smallest template ever.</description>
   <files>
      <filename>index.php</filename>
      <filename>templateDetails.xml</filename>
   </files>
   <positions>
      <position>debug<position>
   </positions>
</extension>
```

What do you see here? The first line creates \(similar to PHP\) an XML section determining version and character set \(utf-8\). Then comes, what a horror, the document type declaration. Here you will probably want to see the same concept, which was responsible for simplifying the document type in HTML5. But what do you find instead? A declaration, which you and I and the creators of XML simply could not write down from memory. Oh no! But luckily we have the BL4NK where everything is already pre-coded. Phew! Further explanations on this can be avoided as under the given joomla.org address there is no file to be found. And you're right if you ask yourself: Why bother?

Fine! Lets get to the fun part of templateDetails.xml. It begins with the install-section that includes the Joomla!™ version for which the template is determined. The type is called "template". The `method="upgrade"` allows the template to install over an existing version at a later stage \(do you smell the danger?\). Thereby newer versions of the files will be installed. However old files that are no longer needed will remain, thus will not be deleted. Next are the template's general information \(template name, creation date, author, copyright, e-mail address, website, version and description\) being displayed within the template manager in the Joomla!™ backend. After this the installation routine is listed. Folders `<folder>` and files `<filename>` are embedded belonging to the template. The module `<positions>` find their place hereafter. Each position is written on a separate line and is now ready to be integrated into the index.php. This file is also selectable via the module manager in the Joomla!™ backend.

If you would copy the two test files index.php and templateDetails.xml in a folder called mini and zip it into a file \(.zip\) you could successfully install this mini template in Joomla!™.

The mini template is not all suited as the starting point of your template development and is therefore going to be extended. Essential components of the extensions are:

* LESS and SASS compiler
* CSS files
* error, offline and print pages

## Cascading Style Sheets

The Cascading Style Sheets of Blank are located in folder css. If you open this folder, you find other files beside the css files:

* custom.css
* editor.css
* error.css
* normalize.css
* offline.css
* print.css
* template.css
* template.less
* template.scss

The files template.less and template.scss are not css files. For what are these files?

### template.less

LESS is a preprocessor of CSS. Or to say it with the official words: [It's CSS, with just a little more.](http://lesscss.org/). So, you can write simple CSS in every LESS-file. Maybe for someone is CSS enough, but to build more complex templates imports, variables, functions, advanced selectors, mixins and a lot more could be usefull. You will get a very short overview of what LESS offers. For a deep dive read the official documentation.

[LESS Documentation](http://lesscss.org/features/)

By installing BL4NK you install the LESS compiler and the compiling process comes with Gulp. With Gulp you compile your less files into css. More on this later.

Let's take a look into template.less.

```css
// FRONTEND LESS
// ==========================================================================

// This file will be used to generate the template.css

html {
}

body {
}

@media (min-width: 768px) {}
@media (min-width: 992px) {}
@media (min-width: 1200px) {}
```

Well, "This file will be used to generate the template.css". There are only the comment at the first lines, two selectors `html` and `body` with no attributes and three media queries. This structure should give you the idea of the mobile first strategy. First you write your rules for mobile. If you do it well, there is no need to write other rules. This is called mobile only strategy. But maybe, there should display something in a different way, than you go with your definitions from mobile to tablett to desktop.

#### Imports

It is a good idea to put the styles of an object into a separate file and then import it to you main file. For example, if you want to design the navigation of a website, create a file called navigation.less. If it is created, you can import it to your template.less. The following statements can be used.

```css
@import "navigation";
@import "navigation.less";
```

There are also [more options for @import At-Rules](http://lesscss.org/features/#import-atrules-feature), which you can read in the official manual of LESS.

#### Variables

Often you need the same value some times in your CSS. Variables make it easier to controll those values from a single location.

```css
@link-color: #B22222;

a {
  color: @link-color;
}
```

If you handle a lot of variables, it makes sense to put them in a separate file called variables.less.

#### Functions

You find a [list of all built-in functions supported by LESS](http://lesscss.org/functions/) on the main manual. Here is a short example of the function to darken a color.

```css
@link-color: #B22222;
@link-color-hover: darken(@link-color, 10%);

a {
  color: @link-color;
}

a:hover {
  color: @link-color-hover;
}
```

#### Advanced selectors

With the ampersand `&` you can reference parent selectors the following way.

```css
a {
  color: @link-color;
  &:hover {
    color: @link-color-hover;
  }
}
```

Compiling this LESS results in

```css
a {
  color: #B22222;
}

a:hover {
  color: #B22222;
}
```

You can [take use of multiple `&` and change selector order](http://lesscss.org/features/#parent-selectors-feature) \(follow the link\).

#### Mixins

You can mix-in class and id selectors.

```css
.class, #id {
  color: red;
}
.mixin-class {
  .class();
}
.mixin-id {
  #id();
}
```

Results in

```css
.class, #id {
  color: red;
}
.mixin-class {
  color: red;
}
.mixin-id {
  color: red;
}
```

There is [a lot more what you can do with mixins](http://lesscss.org/features/#mixins-feature).

### template.scss

SASS is also a preprocessor of CSS. "Sass is the most mature, stable, and powerful professional grade CSS extension language in the world." SASS-files normally ends with .scss \(in the past it was .sass, but with an upgrade it changes the ending\). You can use imports, variables, functions, advanced selectors, mixins and a lot more. I will give you a short overview of what is possible. Take a look in the official documentation for deep diving.

[SASS Documentation](https://sass-lang.com/documentation/)

By installing BL4NK you install the SASS compiler and the compiling process comes with Gulp. With Gulp you compile your less files into css. More on this later.

Let's take a look into template.scss.

```css
// FRONTEND SASS
// ==========================================================================

// This file will be used to generate the template.css

html {
}

body {
}

@media (min-width: 768px) {}
@media (min-width: 992px) {}
@media (min-width: 1200px) {}
```

Same like LESS above, "This file will be used to generate the template.css". There are only the comment at the first lines, two selectors `html` and `body` with no attributes and three media queries. This structure should give you the idea of the mobile first strategy. First you write your rules for mobile. If you do it well, there is no need to write other rules. This is called mobile only strategy. But maybe, there should display something in a different way, than you go with your definitions from mobile to tablett to desktop.

#### Imports

It is a good idea to put the styles of an object into a separate file and then import it to you main file. For example, if you want to design the navigation of a website, create a file called navigation.scss. If it is created, you can import it to your template.scss. The following statements can be used.

```css
@import "navigation";
@import "navigation.scss";
```

There are also [@-Rules and Directives](https://sass-lang.com/documentation/file.SASS_REFERENCE.html#import), which you can read in the official manual of SASS.

#### Variables

Often you need the same value some times in your CSS. Variables make it easier to control those values from a single location.

```css
$link-color: #B22222;

a {
  color: $link-color;
}
```

If you handle a lot of variables, it makes sense to put them in a separate file called variables.scss.

#### Functions

You find a [list of all built-in functions supported by SASS](http://sass-lang.com/documentation/Sass/Script/Functions.html) on the main manual. Here is a short example of the function to darken a color.

```css
$link-color: #B22222;
$link-color-hover: darken($link-color, 10%);

a {
  color: $link-color;
}

a:hover {
  color: $link-color-hover;
}
```

#### Advanced selectors

With the ampersand `&` you can reference parent selectors the following way.

```css
a {
  color: $link-color;
  &:hover {
    color: $link-color-hover;
  }
}
```

Compiling this SASS results in

```css
a {
  color: #B22222;
}

a:hover {
  color: #B22222;
}
```

[Referencing Parent Selectors: &](https://sass-lang.com/documentation/file.SASS_REFERENCE.html#parent-selector) \(follow the link\)

#### Mixins

You can mix-in class and id selectors.

```css
.class, #id {
  color: red;
}
.mixin-class {
  .class();
}
.mixin-id {
  #id();
}
```

Results in

```css
.class, #id {
  color: red;
}
.mixin-class {
  color: red;
}
.mixin-id {
  color: red;
}
```

There is [a lot more what you can do with mixins](https://sass-lang.com/documentation/file.SASS_REFERENCE.html#mixins).

### custom.css

This is a file for fixing styles in a fast way in the browser \(Joomla!™ backend\). It's bad to use it but sometimes you have to. So it is empty a ready for your fixes.

```css
/* CUSTOM
   ========================================================================== */

/**
 * In best case you don't use this file.
 * It's for fast fixes in browser only.
 */
```

Only the comment shows you which file you just opened.

### editor.css

The editor.css file is used to display your own definitions in your Joomla WYSIWYG editor in the backend, if you use one. For example, the JCE editor. This is most popular editor, but there are many more. In the configuration of this editor it is possible to include your own stylesheets. And that's what we do.

```css
/* EDITOR
   ========================================================================== */

/**
* This file is for backend editors like JCE.
* It will be used for print style, too.
*/

body {
    background-color: #fff;
    color: #000;
    font: normal normal normal 75%/125% arial,sans-serif;
}
```

By default, the text appears black on a white background. It is highly advisable to use the same definitions as in template.css. You may ask yourself: "why not assign the same template.css to the editor?” Well, that usually leads to an ugly editor screen. Also, only some sections of the template.css are responsible for the content. You don't need the remainder. That's why we define what you need in a separate file, without the initial IDs and container classes.

### error.css

The file error.css is linked via the file error.php. Both files are used for the error output that appears when the user visits a non existent page \(error 404\). The standard Joomla!™ error 404 page is so ugly that it's necessary to code something better. Customized error pages are part of every good template and are therefore not something optional.

The default "error.css" definitions are as follows:

```css
/* ERROR
   ========================================================================== */

html,
body {
  height: 100vh;
}

body {
  color: #111;
  font-family: Arial,Sans Serif;
  font-size: 1rem;
  margin: 0;
  padding: 0;
  text-align: center;
}

#error {
  margin: 0 auto;
  padding: 20px;
  max-width: 100%;
}

@media (min-width: 768px) {
  #error {
    padding-top: 32vh;
    max-width: 400px;
  }
}

h1 {
  margin:0 0 20px 0;
}

.search label {
  display:none
}
```

The body are the background and typography defined. The padding is set to zero and output the contents are centered \(text-align\). The container with the ID \#error then defines padding and width. The heading \(h1\) gets a smaller margin. The label of the search box is set not to be displayed \(`display:none`\).

### normalize.css

The normalize.css file is a small CSS file written by [Nicolas Gallaghers](https://github.com/necolas/normalize.css). It provides better cross-browser consistency of our HTML tags. It is a modern HTML5 compliant alternative to the traditional CSS reset. In more then 400 lines of code the HTML tags are defined. Look it over in your editor, when you have some free time. Don't mess around with it!

### offline.css

Just like the error page, the file offline.css is linked within offline.php. The offline page will appear when Joomla is set offline in the global configuration. The visitor will then see the information as defined in this configuration. The appearance \(our CSS definitions\), is stored in this file.

```css
/* OFFLINE
   ========================================================================== */

html,
body {
  height: 100vh;
}

body {
  color: #111;
  font-family: Arial,Sans Serif;
  font-size: 1rem;
  margin: 0;
  padding: 0;
  text-align: center;
}

img {
  border: 0 none;
}

#frame {
  margin: 0 auto;
  padding: 20px;
  max-width: 100%;
}

@media (min-width: 768px) {
  #frame {
    padding-top: 32vh;
    max-width: 400px;
  }
}

.inputbox {
  width: 130px;
}

form {
  margin: auto;
}

form p {
  margin: 0;
  padding: 0;
}

form fieldset {
  border: 0 none;
  margin: 0;
  padding: 0.2em;
}

input {
  padding: 5px;
  font-size: 1rem;
}

input.button {
  cursor: pointer;
  width: auto;
}

form p {
  padding: 0.3em 0;
}

label[for="remember"] {
  font-size: .85rem;
}

.alert {
  padding: 15px;
  margin-bottom: 20px;
  border: 1px solid transparent;
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}

.alert h4 {
    margin-top: 0;
    margin-bottom: 10px;
    color: inherit;
    font-family: inherit;
    font-size: 18px;
    font-weight: 500;
    line-height: 1.1;
}

.close {
    float: right;
    font-size: 21px;
    font-weight: 700;
    line-height: 1;
    color: #000;
    text-shadow: 0 1px 0 #fff;
    filter: alpha(opacity=20);
    opacity: .2;
}

.close:focus,
.close:hover {
    color: #000;
    text-decoration: none;
    cursor: pointer;
    filter: alpha(opacity=50);
    opacity: .5;
}
```

### print.css

The print.css file is linked within the file component.php. Joomla offers to display the content as a print preview. This is done by clicking on the print icon. The icon's view can be set within the article options. Using this file enables you to define a printer-friendly output. You can, for example, increase the contrast of the text color to it's background to improve the readability. The background is best to be defined in white, to save printer ink.

In Blank the reset style sheet normalize.css is imported into the print.css file, also the file editor.css to create a printer-friendly version.

```css
/* PRINT
   ========================================================================== */

@import url('normalize.css');
@import url('editor.css');
```

### template.css

In this file, CSS is written which is created by the LESS or SASS compiler generated with the help of your style sheet file template.less or template.scss. You don't need to edit the template.css file.

## index.php \(Blank\)

It is and remains the core of every template: the file index.php. This is where all the files come together. The articles and modules created by you on the backend show up here. All on the right place of the page.

### defined\( '\_JEXEC' \) or die;

This is my favorite command and should be on every Joomla T-shirt! This is a direct call to prevent manipulation by others. Only Joomla is allowed to execute the file containing this script.

```php
<?php defined( '_JEXEC' ) or die;
```

The PHP script remains open. Normally it would be closed with ?&gt; but there there is more to follow.

### logic.php

The logic.php file is not only explained separately \(after the index.php file described here\), but also included.

```php
include_once JPATH_THEMES.'/'.$this->template.'/logic.php';
```

The logic.php file is included exactly once with the command `include_once` and integrated and executed as PHP script. Joomla specifies the path to the templates into `JPATH_THEMES`. Then it goes on with a slash \(/\) and the folder of the actual templates in `$this->template` inserted in the variable. Another slash and the file name logic.php form the end. Perhaps it would be easier to write the path directly.

```php
include_once 'templates/frontend/logic.php';
```

However, this notation is error-prone. Just remember, if you renaming the template to mytemplate from frontend. In this case, you should know that you have to change the path in index.php. That's it. We close the area of PHP with `?>`.

### Document type

Now we leave the PHP part behind us and have a look at the HTML area. Starting with the document type. Old fogies like myself still remember the complexity of this tag in days gone by. Depending on which "dialect" was spoken, whether HTML 4 or XHTML 1.1, whether or strict standard, you had set a correct lengthy and complicated line of code. That's fortunately over in HTML5:

```markup
<!doctype html>
```

Cool!

### html

We open the Hyper Text Markup Language document with the `<html>` tag and it is closed with `</html>`. Therein is the header `<head>` part and the body `<body>` part.

### head

> In your head, in your head   
> Zombie, zombie, zombie   
> Hey, hey   
> What's in your head, in your head   
> Zombie, zombie, zombie   
> Hey, hey, hey   
> Oh, do, do, dou, do, do, dou, do, do   
> Dou, do, do, dou, dou, do, do, dou   
>   
> \(Part of the songtext: The Cranberries - Zombie\)

Everything within `<head>` and `</head>` are part of the header of the HTML document.

### Header information

Through the interface of Joomla!™, called the API \(Application Programming Interface\), we can use the header information:

```markup
<jdoc:include type="head" />
```

This will load the page title, all CSS files and JavaScripts and extensions are loaded \(and more, but we'll not worry about that\). Yes, you read it right. JavaScript ... In head ... Head shot. And every good frontend developer know: JavaScript should be at the end of the index before the closing body-tag `</body>`. But anyway, we do not use this way, hehe.

### Viewport

The mobile view of your site is supported so that view \(viewport\) of your browser shows the correct viewport.

```markup
<!-- mobile viewport -->
<meta name="viewport"
      content="width=device-width,
               initial-scale=1.0,
               maximum-scale=1.0,
               user-scalable=0" />
```

The above code sets the correct width.

### body

All that stands between the `<body>` and `</body>` is shown to the visitors of your site. This is the place for your layout structure. This is where the actual content of your website takes shape. In BL4NK this area relatively empty. For the start there are two includings. One type component to display the articles for example and the debug module. And yes, before the closing body-tag `</body>` we put our awesome uglified and full compressed javascript file to rule all our javascript. This is the best case we can have.

### page class

The body tag gets two classes added so that you later can define your CSS more precisely.

```markup
<body class="<?php echo $active->alias . ' ' . $pageclass; ?>">
```

Let's start from the end: The variable `$pageclass` is declared in the file logic.php \(more on that later\). It is in the backend of Joomla!™, in each menu item to be specified in options and is quite handy for your own layouts. The variable `$active->alias` is the alias of each menu item displayed.

### Debug module

The debug module is necessary for troubleshooting. If you turn the debug mode on in Joomla!™ \(in the global configuration\), this module outputs the database query that many developers - you, amongst others - find helpful. The debug module is the only module included in Blank. Just as any other module the position must be defined in templateDetails.xml. The name debug is compulsory. I usually place it as the last item in the `<positions>` section of templateDetails.xml:

```markup
<positions>
   <position>debug</position>
</positions>
```

Now the position is available, and the module can be used by the index.php. This is done by Joomla!™ API with the jdoc:include command. At the end of index.php, before the closing body tag, you find the following line:

```markup
<jdoc:include type="modules" name="debug" />
```

This line causes the debug mode to be switched on and the output of it to be shown \(when required\) in the browser window. You need to do the same with all your module positions. For example, if you want to create the module positions header, navigation, breadcrumbs, you write in the templateDetails.xml:

```markup
<positions>
  <position>header</position>
  <position>navigation</position>
  <position>breadcrumbs</position>
</positions>
```

And in the index.php on the places where you want them to appear:

```markup
<jdoc:include type="modules" name="header" />
<jdoc:include type="modules" name="navigation" />
<jdoc:include type="modules" name="breadcrumbs" />
```

That finished the module positions. From now on, all modules are assigned the the correct position. In the backend \(Extensions&gt; Modules&gt; Site\) - thanks templateDetails.xml. And in the frontend - thanks to index.php.

### Module Chrome

Module chrome belongs, together with overrides, to Joomla!™'s special features. It makes the system very flexible for web developers. Module chrome and overrides are some of the reasons why Joomla!™ is so powerful. In addition to the type and name the jdoc:include command gives you also the attribute style. This allows to control the output of a module. We have the following values available:

* none
* xhtml
* outline
* rounded
* table
* horz

With these values, you can significantly influence the output. This chrome value \(please do not confuse with the likewise named browser from Google\) lets the system know how the module should be rendered. Joomla!™ also enables you to define your own chrome variables. The above values in detail:

#### none

Command:

```markup
<jdoc:include type="modules" name="menu" style="none" />
```

Output:

```markup
<ul class="menu">
   <li><!-- menu items --></li>
</ul>
```

#### xhtml

Command:

```markup
<jdoc:include type="modules" name="menu" style="xhtml" />
```

Output:

```markup
<div class="moduletable">
   <h3>Main Menu</h3>
   <ul class="menu">
      <li><!-- menu items --></li>
   </ul>
</div>
```

#### outline

Command:

```markup
<jdoc:include type="modules" name="menu" style="outline" />
```

Output:

```markup
<div class="mod-preview">
   <div class="mod-preview-info">left[outline]</div>
   <div class="mod-preview-wrapper">
      <ul class="menu">
         <li><!-- menu items --></li>
      </ul>
   </div>
</div>
```

#### rounded

Command:

```markup
<jdoc:include type="modules" name="menu" style="rounded" />
```

Output:

```markup
<div class="module">
   <div>
      <div>
         <div>
            <h3>Main Menu</h3>
            <ul class="menu">
               <li><!-- menu items --></li>
            </ul>
         </div>
      </div>
   </div>
</div>
```

#### table

Command:

```markup
<jdoc:include type="modules" name="menu" style="table" />
```

Output:

```markup
<table cellpadding="0" cellspacing="0" class="moduletable">
   <tr>
      <th valign="top">Main Menu</th>
   </tr>
   <tr>
      <td>
         <ul class="menu">
            <li><!-- menu items --></li>
         </ul>
      </td>
   </tr>
</table>
```

#### horz

Command:

```markup
<jdoc:include type="modules" name="menu" style="horz" />
```

Output:

```markup
<table cellpadding="0" cellspacing="0" class="moduletable">
   <tr>
      <th valign="top">Main Menu</th>
   </tr>
   <tr>
      <td>
         <ul class="menu">
            <li><!-- menu items --></li>
         </ul>
      </td>
   </tr>
</table>
```

#### custom chrome

As already mentioned, it is possible to define your own output, thus own chrome variables for the style attribute. The BL4NK contains the file modules.php found in the html folder of the template directory. As you may have noticed, in BL4NK there is neither the said folder \(html\), nor the said file \(modules.php\). Have you installed the template, you can safely create the folder and create the file inside this folder. If you stand before the installation, then the reference to the newly created folder belongs to the templateDetails.xml, so that the installation routine of Joomla!™ knows that this folder exists. Otherwise the folder wouldn't be installed. For details see the chapter templateDetails.xml.

If you create the modules.php file in also new created folder called html, the content could look like this:

```php
<?php defined('_JEXEC') or die;

function modChrome_mystyle($module, &$params, &$attribs) { ?>
   <div class="moduletable
      <?php echo htmlspecialchars($params->get('moduleclass_sfx')); ?>">
      <div class="bghelper">
         <h3><?php echo JText::_( $module->title ); ?></h3>
         <div class="modulcontent">
            <?php echo $module->content; ?>
         </div>
      </div>
   </div><?php
}

?>
```

This chrome can be controlled throught the value mystyle. Important in creating your own chrome features is the transfer of $module, &$params and &$attribs to bring the settings, parameters and attributes to each module, e.g. title, content, module class suffix and so on.

Chrome and overrides are the reasons why Joomla!™ is the right system for your web project.

## logic.php

The logic.php file is included in the index.php. While the index.php stands for the HTML output, the logic.php represents the programming logic. During template development, it is not unusual that the file is further programmed.

### defined\( '\_JEXEC' \) or die;

To make sure that this file is called only in Joomla!™, this line is written.

```php
<?php defined( '_JEXEC' ) or die;
```

This code prevents that the file can be accessed from the address bar of your browser.

### Declaring variables

Some variables for the proper use of the template are required. [The basics of PHP variables](http://de2.php.net/manual/en/language.variables.basics.php) can be found in PHP manual \(for beginners: [A simple tutorial in PHP](http://php.net/manual/en/tutorial.php)\).

In a nutshell:

* The first character of each PHP variables is the dollar sign $. This is followed by the variable name.
* Distinction is made between uppercase and lowercase.
* $My\_variable is not the same as $my\_variable or $My\_Variable.
* The dollar sign must be followed by a letter or an underscore \(\_\).
* Spaces are not allowed. $\_my\_variable is okay, $ my\_variable is not.

```php
// variables
$app = JFactory::getApplication();
$doc = JFactory::getDocument();
$menu = $app->getMenu();
$active = $app->getMenu()->getActive();
$params = $app->getParams();
$pageclass = $params->get('pageclass_sfx');
$tpath = $this->baseurl.'/templates/'.$this->template;
```

Most of the variable names are quite self-explanatory. Not so for the contents of the variables, a little explanation is in order. Let's go line by line:

```php
$app = JFactory::getApplication();
```

Here the variable $app is first created, the content in the Joomla!™ framework is called for by the JFactory. The application to which it refers to is Joomla!™ itself, the CMS. The variable $app we will also need for the parameters.

```php
$doc = JFactory::getDocument();
```

Similarly, the variable $doc. Again, we put about the Joomla!™ framework to work with the JFactory class. This variable will take care of the RSS feeds within the page, site information, such as the title and description, references to the JavaScript and CSS files being loaded and will do a lot more. However, that is beyond the scope of this book.

```php
$menu = $app->getMenu();
```

This variable asks for the menu from the $app variable.

```php
$active = $app->getMenu()->getActive();
```

This variable goes a step further: it looks for the active menu item within the $menu. It also checks if this is the Home page or not.

```php
$params = $app->getParams();
```

Using the variable $app we'll query Joomla!™ for the parameters and store that in the variable $params. We will then use to query the page class:

```php
$pageclass = $params->get('pageclass_sfx');
```

A rather aptly named variable, $pageclass. The Page Class Suffix is a parameter in Joomla!™ Menu Items. It is set in the Menu Item: \[Edit\] screen under the "Page Display" section. This will order Joomla!™ to either add a new CSS class or modify the existing CSS class for elements in this specific Menu Item layout.

```php
$tpath = $this->baseurl.'/templates/'.$this->template;
```

That's easy: Variable $tpath contains the relative path to the template directory from the base URL. The $tpath variable is told to look for the active template folder from the base url.

These are all the variables used in Blank.

### generator tag

The generator tag tells the world that we build this site with Joomla!™. Something nobody needs to know, least of all undesirables who want to hack your site. Do we want it? No, we most certainly do not!

```php
$this->setGenerator(null);
```

We are the web developers and we are the ones that need to know what the source code actually is. Nobody else should. Hackers need to know what CMS your using, in order to hack it. Why make it any easier than necessary?

Supposing your want to want to tell the world your website runs on Drupal or WordPress? No problem. Just fill in Drupal or WordPress between the single quotes. Or anything that you like:

```php
$this->setGenerator('Drupal');
```

This will generate `<meta name="generator" content="Drupal" />` in the outputted source code of your website.

### unset

The following lines are all comment out and have no effect right now. Maybe it will be neccessary to comment the lines in to unset some scripts, e.g. jquery. What happened if you comment the following lines in?

```php
// unset
unset($doc->_scripts[$this->baseurl .'/media/jui/js/jquery.min.js']);
unset($doc->_scripts[$this->baseurl .'/media/jui/js/jquery-noconflict.js']);
unset($doc->_scripts[$this->baseurl .'/media/jui/js/jquery-migrate.min.js']);
unset($doc->_scripts[$this->baseurl .'/media/system/js/caption.js']);
if (isset($doc->_script['text/javascript']))
{
    $doc->_script['text/javascript'] = preg_replace('%jQuery\(window\)\.on\(\'load\'\,\s*function\(\)\s*\{\s*new\s*JCaption\(\'img.caption\'\);\s*}\s*\);\s*%', '', $doc->_script['text/javascript']);
    $doc->_script['text/javascript'] = preg_replace("%\s*jQuery\(document\)\.ready\(function\(\)\{\s*jQuery\('\.hasTooltip'\)\.tooltip\(\{\"html\":\s*true,\"container\":\s*\"body\"\}\);\s*\}\);\s*%", '', $doc->_script['text/javascript']);
    if (empty($doc->_script['text/javascript']))
    {
        unset($doc->_script['text/javascript']);
    }
}
```

Well, the first line is a comment. The second line unset the file jquery.min.js from head, the third line jquery-noconflict.js, the fourth \(may the 4th be with you\) line jquery-migrate.min.js and the fifth caption.js. The lines after that unset all direct written javascript in head. With these lines helps you to bring all scripts in only one file.

### Template CSS

To access the one and only template css, you only need this lines:

```php
// css
$doc->addStyleSheet($tpath.'/build/style.css');
```

### Custom CSS

The line to add the custom css is comment out. Comment in, if neccessary.

```php
// $doc->addStyleSheet($tpath.'/css/custom.css');
```

This will load the custom.css in the head for faster style fixings.

## Parameter

The template engine is one of the great strengths of Joomla!™. It is possible to gain more flexibility in your template with parameters. For example, you can set different color variations for your template in the backend. These settings are stored as styles in the database. A style is a single definition of settings for your template. You can define multiple styles and assign one to a menu item.

### Definition

Parameters are defined in the templateDetails.xml. However, BL4NK comes with no parameters. For example, here you see a parameter that inserts a Google font in your template:

```markup
<config>
  <fields name="params">

    <fieldset name="basic">

      <!-- GOOGLE FONT-->
      <field name="googlefont" type="text" default=""
        label="Google Font"
        description="font type input">
      </field>

    </fieldset>

  </fields>
</config>
```

For the parameters to work you need to set them in `<fields name="params"></fields>`, which you can find between `<config>` and `</config>`, in the configuration \(config\) section. You create in the fields tag the space for specifying the parameters. With the fieldset tag you group the parameters. Each parameter is defined within a field tag \(please observe: without s\). To this very day, attributes of type and name are mandatory. All other attributes are optional.

A Google Font is of the type text. You can enter any text. In the label name you set the title for the parameter, visible in the backend. In description you place the text which will be visible when you hover over the title in the backend.

#### type

specifies the HTML element we want. In this case "text". There are many different standard parameter and form field types supported in the Joomla!™ Framework for all extension types \(templates, components, modules and plugins\).

#### name

is unique for each parameter, and is used to address the Parameter in the template.

#### default

specifies the default value of the parameter.

#### description

is the description of the parameter in the backend, appearing as a tooltip.

#### label

is the description your see in the backend.

### Types

The Joomla framework has a number of types of parameters for extensions. Developing templates you need to know: text, radio, filelist, folder list and spacer.

#### list

The parameter type list provides a list of drop-down menu entries. If there is an entry for this parameter in the database, this will be selected as the default.

* type \(mandatory\): list
* name \(mandatory\): unique name of the parameter
* label \(mandatory, translatable\): A descriptive title field
* default \(optional\): the default value of the list
* description \(optional translatable\): The description is as Tooltip appears.
* class \(optional\): the CSS class of the field; if it is omitted, the default entry will be used

The list must have at least one entry, so an option- Show element. The text between `<option>` and `</option>` appear in the list. Mandatory for entry is the value \(the value of the attribute\).

* value \(mandatory\): the value is stored as a parameter

#### text

With this parameter type you can show a line of text. The entered value is stored in the database and displayed by default.

* type \(mandatory\): text
* name \(mandatory\): unique name of the parameter
* label \(mandatory, translatable\): A descriptive title field
* size \(optional\): Number of characters to be stored
* default \(optional, translated\): The default text
* description \(optional translatable\): The description is as Tooltip appears.
* class \(optional\): the CSS class of the field

#### radio

Using the radio parameter you a create radio buttons. The default value is the stored value or, if no stored value is present, the defined default as the default entry.

* type \(mandatory\): radio
* name \(mandatory\): unique name of the parameter
* label \(mandatory, translatable\): A descriptive title field
* default \(optional, translatable\): the default choice of Radio buttons
* description \(optional translatable\): The description is as Tooltip appears.
* class \(optional\): the CSS class of the field

#### filelist

The type filelist parameter is used to list the files from a folder. It carries the declared default value if there is no value in the database. The entries for default usage carries the value of -1 and 0 , if none is to be used are the first two items on the list.

* type \(mandatory\): folder list
* name \(mandatory\): unique name of the parameter
* label \(mandatory, translatable\): A descriptive title field
* directory \(mandatory\): The path to the directory should be listed
* default \(optional\): the default folder
* description \(optional translatable\): The description is as tooltip appears.
* filter \(optional\): regular expression to filter the folder; the folder specified here are included
* exclude \(optional\): regular expression to filter the folder; the folder specified here excludes
* stripext \(optional\): Boolean argument; if true, the file extension hidden
* hide\_default \(optional\): Boolean argument; if true, is the - Use default - entry is not displayed
* hide\_none \(optional\): Boolean argument; if true, is - Do not use - not displayed

#### folderlist

With the parameter folderlist you create a list of folders from a selected folder. The stored value here is the default value. Two entries exist in any folder list. The first is called "use default" and has the value -1. The second is called "do not use" and has the value 0.

* type \(mandatory\): folder list
* name \(mandatory\): unique name of the parameter
* label \(mandatory, translatable\): A descriptive title field
* directory \(mandatory\): The path to the directory should be listed
* default \(optional\): the default folder
* description \(optional translatable\): The description is as Tooltip appears
* filter \(optional\): regular expression to filter the folder; the folder specified here are included
* exclude \(optional\): regular expression to filter the folder; the folder specified here excludes
* hide\_default \(optional\): Boolean argument; if true, is the - Use default - entry is not displayed
* hide\_none \(optional\): Boolean argument; if true, is - Do not use - not displayed

#### spacer

The spacer parameter will place a horizontal line to individual parameters, to separate a heading from a set of parameters.

* type \(mandatory\): spacer
* name \(optional\): serves as a heading
* hr \(optional\): can have the value true to a horizontal Display line, or false to indicate the name.

### Database

The settings of parameters are stored in the database. The format is: table \#\_template\_styles \(\# stands for the prefix of the tables\). If you access with phpMyAdmin your database can you look at the entries in the table\(s\) and manage them accordingly.

### Usage

A parameter makes only sense if it can be used in the template. You must define a parameter in the file templateDetails.xml and store its value in the database. Once you've done both, you can put them to work. An PHP statement is sufficient:

```php
<?php $variable = $this->params->get('parameter-name'); ?>
```

For example, when you add a Google Font as a parameter, you can use that value in your CSS.

```php
<?php
$googlefont = $this->params->get('googlefont');
$doc->addStyleSheet("https://fonts.googleapis.com/css?family=".$googlefont);
?>
```

You define a variable $googlefont and add its value as a parameter in the next line: `$doc->addStyleSheet` looks for the Google API then you load the font in your template. E.g. if you use 'Roboto' as font you can use it like `font-family: 'Roboto', sans-serif;`.

## Error page

When the visitors to your website goes to page that does not exist, they'll get a system error message on screen. The error message from Joomla!™ - to put it mildly - isn't very pretty. Much better to create your own error page. The BL4NK template will do that fine.

### A good structure

The error page should never berate your visitors. After all, it's not their fault if a page doesn't exist or an internal server error occurs. The following requirements should build a a good error page:

* Minimalist design. Express yourself with simple texts and clear images. Write only the bare minimum. Less is more!
* Link to the home page. Describe in no uncertain terms how reach the Home page and place a link to it. An additional link, for example in the logo is helpful. However, it should not be the only point to get back to the home page.- A search. Offer your visitors always a search box. He'll know what he wants to see, but since he followed a trail, the page he's looking for may have changed or was removed. A search box will be appreciated to narrow down what he was looking for.

Do not use technical terms. To my mother, born in 1954, "404 Error" is completely meaningless.

### error.php

Two files are responsible for the error page: error.php and error.css. The header section of the PHP file is almost identical to the index.php and need no further explanation. The body does:

```markup
<body>
  <div align="center">
    <div id="error">
      <h1>
        <?php echo htmlspecialchars($app->getCfg('sitename')); ?>
      </h1>
      <p>
        <?php
          echo $this->error->getCode().' - '.
               $this->error->getMessage();
          if (($this->error->getCode()) == '404') {
            echo '<br />';
            echo JText::_('JERROR_..._NOT_FOUND');
          }
        ?>
      </p>
      <p>
        <?php echo JText::_('JERROR_..._HOME_PAGE'); ?>:
        <a href="<?php echo $this->baseurl; ?>/">
          <?php echo JText::_('JERROR_LAYOUT_HOME_PAGE'); ?>
        </a>.
      </p>
      <?php // render module mod_search
        $module = new stdClass();
        $module->module = 'mod_search';
        echo JModuleHelper::renderModule($module);
      ?>
    </div>
  </div>
</body>
```

\(Note from the author: For better readability the language variables were shortened in some places with three dots ... \)

In the heading \(h1\) the site title of your website is generated. Followed by the output of the error code, and the error message. The control structure \(an “if” statement\) checks whether it this a 404 error and where to place an additional error message, if necessary. The text of this can be found in the language files. After that, the visitor can click on the link to to go to the home page. As a last step, the module mod\_search is placed in the script. So visitors can search on the error page what they were looking for. The jdoc:include command you use in the index.php file to display modules at certain positions does not work here. However, the object JModuleHelper::renderModule will do that instead.

The error.php is in the top section of the file, with the associated error.css linked to it. The error.css file you can find in the CSS folder in your template directory.

```css
/* ERROR
   ========================================================================== */

html,
body {
  height: 100vh;
}

body {
  color: #111;
  font-family: Arial,Sans Serif;
  font-size: 1rem;
  margin: 0;
  padding: 0;
  text-align: center;
}

#error {
  margin: 0 auto;
  padding: 20px;
  max-width: 100%;
}

@media (min-width: 768px) {
  #error {
    padding-top: 32vh;
    max-width: 400px;
  }
}

h1 {
  margin:0 0 20px 0;
}

.search label {
  display:none
}
```

There is plenty of room for your own design, your creativity is not limited. Brows the Internet to find some really great examples of custom error pages. You'll find lots of them.

## Offline page

The offline.php file is always displayed when Joomla!™ is taken offline by the backend. In the configuration you can also leave the offline message, which is then displayed. For the design the offline.css is responsible.

A good opportunity to Joomla!™ set offline are updates. Through the login form you have also the possibility to look at the frontend of your site and test if it works properly.

### offline.php

The head section is similar to the index.php and error.php. In the body you code the part which a visitor see when he enters your website \(in offline mode\).

```markup
<body>
  <div id="frame">
    <?php if ($app->getCfg('offline_image')) : ?>
      <img src="<?php echo $app->getCfg('offline_image'); ?>"
           alt="<?php echo $app->getCfg('sitename'); ?>" />
    <?php endif; ?>
    <h1>
      <?php echo htmlspecialchars($app->getCfg('sitename')); ?>
    </h1>
    <?php
      if ($app->getCfg('display_offline_message', 1) == 1
        && str_replace(' ', '',
        $app->getCfg('offline_message')) != ''):
    ?>
    <p><?php echo $app->getCfg('offline_message'); ?></p>
    <?php
      elseif ($app->getCfg('display_offline_message', 1) == 2
        && str_replace(' ', '',
        JText::_('JOFFLINE_MESSAGE')) != ''):
    ?>
    <p><?php echo JText::_('JOFFLINE_MESSAGE'); ?></p>
    <?php
      endif;
    ?>
    <jdoc:include type="message" />
    <form action="<?php echo JRoute::_('index.php', true); ?>"
      method="post"
      name="login"
      id="form-login">
      <fieldset class="input">
        <p id="form-login-username">
          <input type="text"
            name="username"
            id="username"
            class="inputbox"
            alt="<?php echo JText::_('JGLO...NAME'); ?>"
            size="18"
            placeholder="<?php echo JText::_('JGLO...NAME'); ?>" />
        </p>
        <p id="form-login-password">
          <input type="password"
            name="password"
            id="password"
            class="inputbox"
            alt="<?php echo JText::_('JGLO...WORD'); ?>"
            size="18"
            placeholder="<?php echo JText::_('JGLO...WORD'); ?>" />
        </p>
        <p id="form-login-remember">
          <input type="checkbox"
            name="remember"
            value="yes"
            alt="<?php echo JText::_('JGLOBAL_REMEMBER_ME'); ?>"
            id="remember" />
          <label for="remember">
            <?php echo JText::_('JGLOBAL_REMEMBER_ME'); ?>
          </label>
        </p>
        <p id="form-login-submit">
          <input type="submit"
            name="Submit"
            class="button"
            value="<?php echo JText::_('JLOGIN'); ?>" />
        </p>
      </fieldset>
      <input type="hidden" name="option" value="com_users" />
      <input type="hidden" name="task" value="user.login" />
      <input type="hidden" name="return"
        value="<?php echo base64_encode(JURI::base()); ?>" />
      <?php echo JHTML::_( 'form.token' ); ?>
    </form>
  </div>
</body>
```

Unlike on the error page the jdoc:include does work on the offline page. Therefore it is first item in the script. Following is a query to generate the offline image which is stored in the configuration in the backend of your site \(if you want to work with an image, that is\). This will replace the default offline page by your own, with a place for the output error message that you retrieve from the configuration file of Joomla!™. Then the login with username field and password are added.

The same as for the error page applies to the offline page: be creative as you want to be. Customize the page using the stylesheet offline.css.

```css
/* OFFLINE
   ========================================================================== */

html,
body {
  height: 100vh;
}

body {
  color: #111;
  font-family: Arial,Sans Serif;
  font-size: 1rem;
  margin: 0;
  padding: 0;
  text-align: center;
}

img {
  border: 0 none;
}

#frame {
  margin: 0 auto;
  padding: 20px;
  max-width: 100%;
}

@media (min-width: 768px) {
  #frame {
    padding-top: 32vh;
    max-width: 400px;
  }
}

.inputbox {
  width: 130px;
}

form {
  margin: auto;
}

form p {
  margin: 0;
  padding: 0;
}

form fieldset {
  border: 0 none;
  margin: 0;
  padding: 0.2em;
}

input {
  padding: 5px;
  font-size: 1rem;
}

input.button {
  cursor: pointer;
  width: auto;
}

form p {
  padding: 0.3em 0;
}

label[for="remember"] {
  font-size: .85rem;
}

.alert {
  padding: 15px;
  margin-bottom: 20px;
  border: 1px solid transparent;
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}

.alert h4 {
    margin-top: 0;
    margin-bottom: 10px;
    color: inherit;
    font-family: inherit;
    font-size: 18px;
    font-weight: 500;
    line-height: 1.1;
}

.close {
    float: right;
    font-size: 21px;
    font-weight: 700;
    line-height: 1;
    color: #000;
    text-shadow: 0 1px 0 #fff;
    filter: alpha(opacity=20);
    opacity: .2;
}

.close:focus,
.close:hover {
    color: #000;
    text-decoration: none;
    cursor: pointer;
    filter: alpha(opacity=50);
    opacity: .5;
}
```

## Print page

The component.php allows you to print a printer-friendly version of your web pages. Printer friendly means that you print the component view only. The component is responsible for showing the articles. The whole layout \(modules, menus, etc.\) remains as it is. This can be rather handy; the focus is on the content only.

```markup
<body id="print">
  <div id="overall">
    <jdoc:include type="message" />
    <jdoc:include type="component" />
  </div>
  <?php if ($_GET['print'] == '1') echo '<script type="text/javascript">window.print();</script>'; ?>
</body>
```

By using the component.php it is possible for you to create your own css file, defining how you want to print that page. In the template directory of Blank your find the file print.css ready to go.

```css
/* PRINT
   ========================================================================== */

@import url('normalize.css');
@import url('editor.css');
```

## Overrides

A milestone in Joomla!™ are the overrides. With overrides you can customize an extension for your own needs. Many developers and designers in the past complained about the component com\_content creates HTML tables. This component is responsible for the content. You can change these things now, without touching the core files. Sure, you can also change the core files, thus changing the original. But then you run the risk that the next Joomla!™ update overwrites your file. In that case your changes would be lost and you would have to start all over again. And again and again...

An override works like this: you create an exact copy of the file, put it in your template folder, rewrite it and if the Joomla!™ extension is invoked, your file has priority over the original. Your file is the override of the actual file.

Thanks to the fact that Joomla!™ is based on the architecture Model-View-Controller \(abbreviated MVC\) overrides are possible. Under this architecture, the output of an extension - what the visitor will actually see on screen - is addressed by so-called 'views'. And these 'views' can be overridden. The 'views' have no influence on the working of the extension.

Suppose you want to change the default output of an article. Responsible for this output is the component com\_content. This component directory exists in the of the folder 'article' within the 'tmpl' subfolder. Here you find the "default.php" file that controls the output. The full path in Joomla!™ is:

components/com\_content/views/article/tmpl/default.php

This default.php file you can override in your template within the subfolder 'article' of the folder 'com\_content' within the directory 'html'. That's difficult to read but easy to see in an example. The full path would look like this:

templates/frontend/html/com\_content/article/default.php

Following this principle, you gain the complete control over the output of your website.

From Joomla!™ Version 3, you can easily create override in the backend. Go to Extensions &gt; Template Manager &gt; Templates &gt; ... details and files &gt; Create Overrides. Select there the extension or module which you want to override.

## Images

Images required to each template are stored in the template folder 'images'. You don't need to name your folder 'images', but 'images' or 'img' make a lot more sense than 'apples'. However, the two preview images template\_preview.png and template\_thumbnail.png, are exceptions. They reside in the template's root folder. The first image is the large preview of the second image, the small preview; which is displayed in the backend.

Images are available in different formats and each format has its strengths and is used in various fields.

* Use GIF in web design with few colors
* Use PNG in web design with many colors
* Use PNG in web design with transparency
* Use JPG in web design with photos and landscapes

The reason will be described in the following chapter.

### Formats

There are three formats for your images being:

* GIF - Graphics Interchange Format
* PNG - Portable Network Graphics
* JPEG - Joint Photographic Experts Group

Other formats such as TIFF are not suitable for the Internet. TIFFs store too much information which increases the size of the image and thus increases the load time unnecessarily. It is an art to deal with images as a web designer, because not every situation has a specific preferable format.

#### GIF

Advantage: Small size, transparency Disadvantage: Only 256 colors, no alpha effect

#### PNG

Advantage: Small size, lossless compression, 16,7 million colors, transparency, alpha effect Disadvantage: In PNG-8 no alpha effect

#### JPEG

Advantage: Small size, variable compression, 16.7 million colors Disadvantage: No transparency, no alpha effect

### Size

It's very important for a web designer is to pick the right size for an image. The smaller, the faster it loads. So our motto should be: save your picture size where you can. It's all about pure loading time. Especially when more than 100 images are used, each kilobyte is valuable.

An experiment has shown that one and the same image has significant differences in the different formats, without recognizing a visible difference.

GIF: 20,7 KB PNG: 44,4 KB JPG: 25,9 KB

These values serve as a guide only and may vary from image to image. Therefore, export an image in all three formats and look at the result. The ratio of quality to file size is crucial to achieve the best possible loading time.

### Transparency

Do you want to use transparent images your two choices are GIF or PNG. JPGs don't work with transparency. PNG has a further advantage over GIF: the variable opacity or alpha-effect. With PNGs you can use images that are, for example, 50% transparent. GIF can not do that. It's all \(100%\) or nothing \(0%\) transparency. This property sets clearly PNG over GIF. With PNG you can manage to create designs you can't accomplish with other formats.

## JavaScripts

JavaScript itself is a programming language that runs in the visitor's browser, hence on the client side. This means that the visitor's computer must do the heavy work. You can use JavaScript server-side through the script "node.js". Then it behaves like PHP and is executed on the computer \(server\) in the network. At the price of speed...

You can code JavaScript either directly in the file index.php or include it as a separate file. The program is then executed in the browser run time.

If you want to use additional JavaScript files, for example, the framework jQuery, you can personalize it in its directory \(usually called 'js'\) and link with the following code in the index.php:

```php
$doc->addScript($tpath.'/js/javascript.js');
```

Tip: It is better to place additional files, that are not explicitly required in the header area `<head>`, just before the closing tag of the body `</body>` in index.php. It has been proven that your website's performance increase if all CSS files are loaded in head and all JavaScript files at the end of the body area.

Alternatively, you can also load JavaScript libraries via Google, which carry the advantage of faster page loading for visitors. A script loads faster from a client's browser than from the server. Another advantage is that multiple scripts can be loaded parallel. Some browsers limit the connections per server, and therefore lower the website's performance. The biggest advantage however is the better caching. Assume you have already visited a web site and your browser has loaded jQuery through Google in the computer's cache. This library will not be loaded again when you visit a site that uses the same library from Google. For further informations look at [Google Hosted Libraries - Developer's Guide](https://developers.google.com/speed/libraries/devguide).

Hint: With the inclusion of additional JavaScripts or frameworks, complications can arise because Joomla uses the Bootstrap Framework by default. Some frameworks offer a No-Conflict-Method. You should first think carefully whether the extra effort is justified when you plan to use a JavaScript.

## Language files

BL4NK comes without language files. If you want to use language files, you should create a folder called language in your template folder. The name 'language' in lower case letters is compulsory. You need to create that language folder before \(!\) you install the template.

Language files are created the following way:

* de-DE/de-DE.tpl\_frontend.ini
* en-GB/en-GB.tpl\_frontend.ini

For each language you have to create its own folder. In your template folder it would look like this:

* frontend
  * language
    * de-DE
      * de-DE.tpl\_frontend.ini
    * en-GB
      * en-GB.tpl\_frontend.ini

You have to declare the language folder and the various languages in templateDetails.xml under the files section `</files>`:

```markup
<languages folder="language">
  <language tag="de-DE">de-DE/de-DE.tpl_frontend.ini</language>
  <language tag="en-GB">en-GB/en-GB.tpl_frontend.ini</language>
</languages>
```

Generally, language files work in both the frontend and backend. Tese files, contain the text used by the language variables. The file name is composed of the country code, the extension type, the template name and the file extension together. The country code de-DE stands for the language \(de\) and the country \(DE\). For Switzerland this would be de-CH. For the USA it is \(en\) and \(US\), making it en-US and for the United Kingdom of Great Britain and Northern Ireland en-GB. The template extension for language is tpl. Thus, the default language being British English, we have en-GB.tpl. The next part is your template name, separated by an underscore, e. g.: frontend. The file extension .ini designates an initialisation file, say a setup file.

The language files are important for translations. For example, if you equip your templates with parameters, they receive a description. This description can be translated into other languages linguistic and therefore variables are used. The variables associated with the wording to be used, are found in the language files.

**Example**

In the file templateDetails.xml of BL4NK you can define a parameter to use Google fonts:

TPL\_FRONTEND\_PARAMETER\_GOOGLEFONT\_LABEL

If you open the file "en-GB.tpl\_frontend.ini", you can find the wording for it.

TPL\_FRONTEND\_PARAMETER\_GOOGLEFONT\_LABEL="Google Font"

This text will be displayed instead of the variable. In other words: whenever the variable TPL\_FRONTEND\_PARAMETER\_GOOGLEFONT\_LABEL appears in the template the output of the text in the "Google Font" is displayed.

In other words, if there is a key value pair in the language file "en-GB.tpl\_frontend.ini" you can use the key \(e.g. TPL\_FRONTEND\_PARAMETER\_GOOGLEFONT\_LABEL\) in the templateDetails.xml to display the value \(e.g. Google Font\).

