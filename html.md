# HTML

[<- Go Back](README.md)

## What is HTML?

[Wikipedia definition:](https://en.wikipedia.org/wiki/HTML)

> `Hypertext Markup Language (HTML)` is the standard **markup language** for creating web pages and web applications.

* Web browsers receive HTML documents from a web server or from local storage and render them into multimedia web pages. 

> **HTML describes the structure of a web page**.

[Markup Language Wikipedia definition:](https://en.wikipedia.org/wiki/Markup_language)

* The current HTML version is [HTML5](https://en.wikipedia.org/wiki/HTML5)

> A markup language is a system for annotating a document in a way that is syntactically distinguishable from the text. Instructions are expressed directly by tags.

Open the [following news](http://winnipegsun.com/entertainment/movies/black-panther-stays-strong-with-108m-in-second-weekend/wcm/80188f8d-d8e3-4f62-95c7-a2231784eb1b) and define the different parts of the document structure.

Looks like this document has the following sections:

* A main title: ’Black Panther’ stays strong with $108M in second weekend
* A picture
* A picture description: This image released by Disney shows a scene from Marvel Studios' "Black Panther." Matt Kennedy / AP
![Black Panther news](resources/html/html_news.png)
* Secondary title: NEW YORK — “Black Panther” has scored one of the best second weekends ever with an estimated $108 million in ticket sales.
* Text:
Studio estimates Sunday say “Black Panther” is still performing as one of the top blockbusters of all time. This weekend’s result makes Ryan Coogler’s Marvel sensation only the fourth film to earn $100 million in its second weekend, along with “Star Wars: The Force Awakens,” “Jurassic World” and “The Avengers.”
Of those, only “The Force Awakens” had a better second weekend.
In two weeks of release, “Black Panther” has grossed $400 million domestically and $704 million worldwide.
Of new releases, faring the best is the Warner Bros. comedy “Game Night,” starring Jason Bateman and Rachel McAdams. It debuted with $16.6 million.
The well-reviewed sci-fi thriller “Annihilation” opened with $11 million.

![Black Panther news](resources/html/html_news_content.png)

* Comments section: 0 Comments
* Share your thoughts

![Black Panther news](resources/html/html_news_comments_title.png)

* Featured Articles title

![Black Panther news](resources/html/html_news_feature_news.png)

* Comments form

![Black Panther news](resources/html/html_news_comments.png)

Finaly, this is how the news HTML code looks like:

![Black Panther news](resources/html/html_news_html.png)

## Tag Structure

* As HTML is a markup language we'll use tags to create HTML elements that will show the user the different document sections and content.
* A tag will have the following parts:
  * The `<` character defines the initial part of our tag
  * Then well add the `tagname` that we want to use
  * At the end we'll use the `>` character
  * We can call this void or empty element as it doesn't have any content
```html
<tagname>
```

* There're other tags that will have content
* To add content we just write it after the `>` character

```html
<tagname>Content of our tag
```

* In this case the first tag is working as an opening one
* We need to close this structure to let the browser know that we finished defining this structure
* Closing tags are pretty similar to the opening ones but with a minor difference
* Add a `/` character after the `<` and then follow with the tagname

```html
<tagname>Content of our tag</tagname>
```

* We can write this in a different format too
* Using [indentation](https://en.wikipedia.org/wiki/Indentation_(typesetting)) is a good practice when we code as it allows us to see complex structures in a simpler way

```html
<tagname>
  Content of our tag
</tagname>
```

* We have 2 different types of tags:
  * Void or empty - just 1 tag
  * With content - need the opening and closing tags

### Tag attribute
* Tag attributes are additional values that configure the tags or adjust their behavior in various ways to meet the criteria the users want
* The attributes will have an attribute name and a value
```html
attribute="value"
```
* Attributes are part of the tag

```html
<tagname attribute="value">

<tagname attribute="value">Content of our tag</tagname>
```

* HTML defines elements attributes
* Some attributes are global
* The **id** attribute allows us to uniquely identify an element in a document
* We can add an id attribute to any HTML element
* There must be only one element for each unique id

```html
<tagname id="first-element">
<tagname id="second-element">Content of our tag</tagname>
```

* The **class** attribute accepts a CSS class name
* We can use the class attribute to identify many elements by the same criteria

```html
<tagname class="red">Text in red</tagname>
<tagname class="red">Text in red</tagname>
<tagname class="red">Text in red</tagname>
<tagname class="red">Text in red</tagname>
<tagname class="red">Text in red</tagname>
```

### Tag with tags!
* Also, we can have tags as content from other tags:

```html
<tagname>
  <tagname>Hi I'm a title</tagname>
  <tagname>
</tagname>
```

* Using tags inside other tags we can create more complex structures
* This looks great but it doesn't make sense as all the tags have the same name

## HTML Tags
* Now that we know how tags works we only need to know the HTML tags names and attributes
* Check the MDN site to se a complete list of [HTML elements reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

## HTML document structure
* The first tag we'll learn is the DOCTYPE tag
* It's an empty tag as it doesn't have content
* By using this tag the browser knows the version of HTML that we are using
* The browser won't render this tag

### HTML5 Doctype
```html
<!DOCTYPE html>
```
### HTML
* The **html** element represents the root (top-level element) of an HTML document, so it is also referred to as the root element. All other elements must be descendants of this element.
* [MDN html doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)

```html
<html></html>
```

### HEAD
* The **head** element provides general information (metadata) about the document, including its title and links to its scripts and style sheets.
* [MDN head doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head)

```html
<head></head>
```

### Title
* The Title element defines the title of the document, shown in a browser's title bar or on the page's tab. It can only contain text, and any tags contained within are ignored.
* It's part of the **head** element
* [MDN title doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)

```html
<head>
  <title>Document title!</title>
</head>
```

### BODY
* The **body** Element represents the content of an HTML document. There can be only one <body> element in a document.
* We can write any content or other HTML elements between the html tags
* [MDN body doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)

```html
<body></body>
```

### Basic HTML file

**Example:**
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Document title</title>
  </head>
  <body>
    Text inside the HTML body tag
  </body>
</html>
```

#### Practice
[Exercise 1](exercises/html/ex_1.md)

### Heading Elements
* HTML has 6 title levels
* The title tag name is the letter **h** and the title number (h1, h2, h3, h4, h5, h6)
* By default the browser will show the h1 much bigger than the h6
* It's a good practice to respect the titles order by Hierarchy
* [MDN heading elements doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)

**Example:**
```html
<h1>Main title</h1>
<h2>Secondary title</h2>
<h3>Other title</h3>
<h4>Other title</h4>
<h5>Other title</h5>
<h6>Other title</h6>
```

### Paragraph
* The **p** tagname represents a paragraph
* This tag accepts content so we'll have an open and close tags
* The paragraph tag is a `block element`
* By default the browser will show block elements one below the other
* The browser will render only a space character even if we write many
* We can use &nbsp; [HTML entity](https://developer.mozilla.org/en-US/docs/Glossary/Entity) to display the space character
* [MDN paragraph doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)

**Example**
```html
<p>Paragraph content.</p>
<p>Paragraph          content.</p>
<p>Text with some &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; spaces</p>
```

#### Practice
[Exercise 2](exercises/html/ex_02.md)

## Containers
### Div
* The  content division element **div** is the generic container
* This tag has no effect on the content or layout until styled using CSS
* It's used to group content so it can be easily styled
* By default this is a `block element` and begin on new lines
* [MDN div doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)

#### Span
* The **span** element is a generic `inline` container for phrasing content, which does not inherently represent anything. 
* It can be used to group elements for styling purposes
* Inline elements can start anywhere in a line

**Example:**
```html
<span>This is a inline element</span>
<span>Next element inline and it's right next the previous one</span> 
<p>This parragraph has a <span>section</span></p>
```

### Inline vs Block elements
* `block-level` elements may contain `inline elements` and other `block-level elements`. 
* Inherent in this structural distinction is the idea that block elements create "larger" structures than inline elements.
* `Inline elements` are those which only occupy the space bounded by the tags defining the element, instead of breaking the flow of the content.
* Generally, inline elements may contain only data and other inline elements. You can't put block elements inside inline elements.
* By default, inline elements do not force a new line to begin in the document flow. Block elements, on the other hand, typically cause a line break to occur (although, as usual, this can be changed using CSS).
* [MDN Block-level_elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements)
* [MDN Inline_elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements)

### Comments
* In most programming languages, there is a mechanism available to write comments in the code
* Comments are ignored by the browser and are invisible to the user
* Their purpose is to allow you to include comments in the code to say how your code works, what the different parts of the code do, etc. 
* We can write inline or multiline comments

**Example:**
```html
<!-- Inline comment -->

<!-- 
  Multiline Comment
  Multiline Comment
  Multiline Comment
  Multiline Comment
  Multiline Comment
  Multiline Comment
-->

<!-- <p>The browser won't render this paragraph</p> -->
```

### Line Break
* The **br** element produces a line break in our text (carriage-return)
* It is useful where the division of lines is significant
* [MDN br doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br)

**Example:**
```html
<p>This text will have a line break<br> and then we keep on writing</p>
<br>
<br>
<p>We can use a line break in any <br> part of our documents body</p>
```

### Horizontal Rule
* The **hr** element represents a thematic break between paragraph-level elements
* It has been presented as a horizontal rule or line
* [MDN hr doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hr)

**Example:**
```html
<h1>Main title</h1>
<h2>Subtitle</h2>
<hr>
<p>Rest of the content</p>
```

#### Practice
[Exercise 3](exercises/html/ex_03.md)

### Text Format
* HTML has some tags to describe how the text should be
* The **strong** element indicates that its contents have strong importance, seriousness, or urgency. 
* Browsers typically render the contents in bold type.
* Remember that we'll use CSS for **bold font weight**

**Example:**
```html
<strong>This is a very important text!!</strong>
```

## Lists
* As web developers we'll use lists for many different things 
* HTML has 3 different list types:
  * Unordered
  * Ordered
  * Description or definition

### Unordered list
* The **ul** element represents an unordered list of items
* By default it will be rendered as a bulleted list
* We'll use this type of list when we don't care about items order
* Each item is a list item or **li** element
* [MDN ul doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)
* [MDN li doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)

**Example:**
```html
<ul>
  <li>First List Item</li>
  <li>Second List Item</li>
  <li>Third List Item</li>
</ul>
```

### Ordered list
* The **ol** element represents an ordered list of items
* By default it will be rendered as a numbered list
* We'll use this type of list when we care about the items order
* This type of list also accepts **li** elements as children
* [MDN ol doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)

**Example:**
```html
<ol>
  <li>Order Item</li>
  <li>Order Item</li>
  <li>Order Item</li>
</ol>
```

### Description or definition list
* The **dl** element represents a description list
* The element encloses a list of groups of terms (**dt** element) and descriptions (**dd** elements) 
* Common uses for this element are to implement a glossary or to display metadata (a list of key-value pairs)
* [MDN dl doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl)
* [MDN dt doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dt)
* [MDN dd doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dd)

**Example:**
```html
<dl>
  <dt>Term</dt>
  <dd>Definition</dd>
</dl>
```

### Nested list
* List can be nested inside list items
* We can use any list type
* Very helpful and used to create sites menus adding CSS

![mindblown](resources/html/mindblown.gif)

**Example:**
```html
<ul>
  <li>Unordered list item</li>
  <li>
    <ol>
      <li>Ordered list item</li>
      <li>Ordered list item</li>
      <li>Ordered list item</li>
    </ol>
  </li>
</ul>
```
#### Practice
[Exercise 4](exercises/html/ex_04.md)

## Hyperlink
* The **a** element (or anchor element) creates a hyperlink to other web pages, files, locations within the same page, email addresses, or any other URL.
* This element has a **href** attribute that contains a URL or a URL fragment that the hyperlink points to
* Between the opening and the closing tag we can add the link content that the user will click on
* As content we can put other HTML elements like an image tag
[](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)

**Example:**
```html
<a href="other_file.html">Click me I'm a link!!</a>
<a href="my_dog.jpg">Link to my dog picture</a>
<a href="video.avi">Link to my video</a>
```

### External links
* In some cases we need to link our HTML documents with external files or other resources
* We can do this by using the external URL's as **href** values

**Example:**
```html
<a href="http://google.com">Go to google.com</a>
```

### Target attribute
* The **a** has a target attribute that specifies where to display the linked URL.
* The following keywords have special meanings:
  * **_self**: Load the URL into the same browsing context as the current one. This is the default behavior.
  * **_blank**: Load the URL into a new browsing context. This is usually a tab, but users can configure browsers to use new windows instead.
  * **_parent**: Load the URL into the parent browsing context of the current one. If there is no parent, this behaves the same way as _self.
  * **_top**: Load the URL into the top-level browsing context (that is, the "highest" browsing context that is an ancestor of the current one, and has no parent). If there is no parent, this behaves the same way as _self.
* For now we'll use only **_blank** as it's the one we use the most

**Example:**
```html
<a href="http://www.comit.org" target="_blank">ComIT</a>
<a href="http://www.comunidadit.org" target="_blank">Comunidad IT</a>
```

### Absolute & relative URLs
* We can define `absolute or relative` Urls
* Let's check this [MDN URL guide](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL) to understand better what's and absolute URL

**Example:**
```html
<a href="http://yahoo.com">Abrir Yahoo</a>
<a href="c:\Users\my_name\my_cv.pdf">Look at my CV</a>
```

* Links can have a relative URL or path
* In this type of URLs we need to know the relationship between files
* To access to the root of our site we can use the following relative path
* Absolute and relatives URLs and Paths will work with any element that need an URL or path to work (imgs, video, audio and more)

**Example:**
```html
<a href="/">Go Home</a>
```

```
/ (root of our folder)
|
|-- index.html
|-- about.html

```

* If we have to files that are siblings or in the same path level we can use the filename as link

**Example:**
```html
To link index.html with about.html
<a href="about.html">About</a>

To link about.html with index.html
<a href="index.html">Go Home</a>

As index is the main file in our site we could use the root
<a href="/">Go Home</a>
```

```
/ (root of our folder)
|-- about/
|   |--- about.html
|
|-- index.html
```

* To link a file that it's inside a folder we'll use the **foldername/filename**

**Example:**
```html
To link index.html with the about.html
<a href="about/about.html">About</a>
```

* Also we can link files from inside a folder to another that's outside
* We will add as many **../** as folders we need to exit

**Example:**
```html
To link about.html to index.html first we need to exit the about folder
<a href="../index.html">Go home</a>
```

```
/ (root of our folder)
|-- about/
|   |-- other_folder/
|     |--- about.html
|
|-- index.html
```

**Example:**
```html
With this folder structure:
To link from index.html to about.html we'll use both folder names
<a href="about/other_folder/about.html">About</a>

To link about.html to index.html we need to exit 2 folders (../../filename)
<a href="../../index.html">Go home</a>
```

* [absolute vs relative pathslinks](https://www.coffeecup.com/help/articles/absolute-vs-relative-pathslinks)
* [What are hyperlinks](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_hyperlinks)
* [Creating hyperlinks](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks)
* [Dealing with files](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files)

## Mailto
* We can use links to configure to send an email
* The browser will try to open the default email app if we set the **href** value to **mailto:account@domain.com**

```html
<a href="mailto:pablo@comit.org">Contact me</a>
```

### Anchor
* We can use links to navigate to anchor points and into a selected document part
* If the URL has an anchor the browser will lookup for that document section
* To accomplish this task we need to combine the **a** element and **href**, **name** attributes
* The **#** works as anchor symbol (remember the URLs MDN guide)

**Example**
```html
First we'll create a link with the anchor href
<a href="#news">News Section</a>

Then we need to create the anchor by using the name attribute
<a name="news"></a>

We created an empty link with the news attribute. As they are on the same document the browser will try to
 navigate to the news anchor.

To be able to see this magic working we need to create long documents

Also we can navigate to a different document section:
<a href="news.html#nhl">NHL news section</a>
```

#### Practice
[Exercise 5](exercises/html/ex_05.md)

[Exercise 6](exercises/html/ex_06.md)

## Images
* The **img** element embeds an image into the document
* It's only a one tag element as it doesn't allow content (other elements or text)
* The **src** attribute accepts an image filename / path
* The **img** is an inline element
* By default the placeholder will have the image size
* We must use optimized images to avoid big files
* The browser knows how to render different image types: [jpg](https://es.wikipedia.org/wiki/Joint_Photographic_Experts_Group), [png](https://es.wikipedia.org/wiki/Portable_Network_Graphics) & [gif](https://es.wikipedia.org/wiki/Graphics_Interchange_Format)
* [Image optimization - Google Developers](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization)
* [MDN img doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)

**Example**
```html
<img src="mypicture.jpg">
```

* We can use absolute or relative paths/urls as **src** value

**Example**
```html
Relative example:
<img src="img/mypicture.jpg">

Go one folder level back, then enter the img folder and get mypicture file
<img src="../img/mypicture.jpg">

Absolute URL:
<img src="http://images6.fanpop.com/image/photos/39500000/il-570xN-917420114-2kdu-rick-and-morty-39567961-300-370.jpg" >
```

* The **img** has a **height** and **width** attribute
* This attributes accepts the intrinsic width & height of the image in pixels
* HTML5 doesn't accept other types of values
* Keep in mind the image ratio when using this attributes

```html
<img src="mypicture.jpg" height="300" width="300">
```
* The **alt** attribute defines the alternative text describing the image. 
* Users will see this text displayed if the image URL is wrong, the image is not in one of the supported formats, or if the image is not yet downloaded.
* Also, screen readers will use this attribute to describe the image
* Adding this attribute to our images is a good practice

**Example**
```html
<img src="coding.jpg" alt="Developers working on a new project">
```

* We can also add a global attribute to our images to describe it better
* The title contains a text representing advisory information related to the element it belongs to. 
* Such information can typically, but not necessarily, be presented to the user as a tooltip.

**Example**
```html
<img src="coding.jpg" alt="Developers working on a new project" title="Nerds" >
```
* [Image alt vs title - Using alt title attributes in image tags](https://www.wpromote.com/blog/image-alt-vs-title-using-alt-title-attributes-in-image-tags)

### Figure & Figure caption
* the **figure** element represents self-contained content, frequently with a caption (**figcaption**), and is typically referenced as a single unit.
* As **figure** content we'll add an image (**img**) and a caption (**figcaption**) elements
* Older browser won't know how to show this element but they will render the image
* [MDN figure doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure)
* [Test your browser](https://html5test.com)

**Example**
```html
<figure>
  <img src="coding.jpg" alt="Developers working on a new project" title="Nerds" >
  <figcaption>Developers working on a new project</figcaption>
</figure>
```

#### Practice
[Exercise 7](exercises/html/ex_07.md)

## Table
* The **table** element represents tabular data — that is, information presented in a two-dimensional table comprised of rows and columns of cells containing data
* Our table will have rows (table rows or **tr**) and columns (table data or **td**) 
* [MDN table doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
* [MDN tr doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr)
* [MDN td doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td)

**Example**
```html
<table>
  <tr>
    <td>1</td>
    <td>2</td>
  </tr>
  <tr>
    <td>3 </td>
    <td>4</td>
  </tr>
</table>
```

* In this example will see a table with 1 and 2 on the first row and 3 and 4 in the second one
* If we need to have an empty cell we still need to add it as part of the table

**Example**
```html
<table>
  <tr>
    <td>1</td>
    <td>2</td>
  </tr>
  <tr>
    <td>3 </td>
    <td></td>
  </tr>
</table>
```

#### Practice
[Exercise 8](exercises/html/ex_08.md)

* Also we can use a **th** to define a cell as header
* [MDN th doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th)

**Example**
```html
<table>
  <tr>
    <th>Name</th>
    <th>Last Name</th>
  </tr>
  <tr>
    <td>Dale</td>
    <td>Hawerchuk</td>
  </tr>
</table>
```

* We can use the following elements to define table sections: **thead, tbody & tfoot**
* The **thead** element defines a set of rows defining the head of the columns of the table
* The **tbody** encapsulates a set of table row (**tr** elements, indicating that they comprise the body of the table)
* The **tfoot** element defines a set of rows summarizing the columns of the table
* A well structured table has all 3 sections
* This is also useful for the screen readers
* We can combine the **thead** and **th** element

**Example**
```html
<table>
  <thead>
    <tr>
      <th>Header 1 - 1</th>
      <th>Header 1 - 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Body 1 - 1</td>
      <td>Body 1 - 2</td>
    </tr>
    <tr>
      <td>Body 2 - 1</td>
      <td>Body 2 - 2</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Foot 1 - 1</td>
      <td>Foot 1 - 2</td>
    </tr>
  </tfoot>
</table>
```

#### Practice
[Exercise 9](exercises/html/ex_09.md)

### Make the tables happier!
* The table element has some attributes that will allow us to add color and other visual effects
* This attributes belong to previous HTML versions but we can still use them
* Remember that we only should use HTML to structure our documents and add CSS to change the way things look
* The **border** attribute defines, in pixels, the size of the frame surrounding the table. If set to 0, the frame attribute is set to void
* The **bgcolor** attribute defines the background color of a table. It consists of a 6-digit hexadecimal code as defined in sRGB and is prefixed by '#'
* We can use any [web color](https://en.wikipedia.org/wiki/Web_colors) as **bgcolor**
* Each cell can have a different **bgcolor** value

**Example**
```html
<table border="1" bgcolor="gray">
  <thead>
    <tr>
      <th>Header content 1</th>
      <th>Header content 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td bgcolor="white">Content with white background</td>
      <td>Body content</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Footer section 1</td>
      <td>Footer section 2</td>
    </tr>
  </tfoot>
</table>
```

* We can use the **width** attribute to set the table width
* The cells also have a with attribute and the table will try to keep the same size for the rest of the cells in the same column
* The **cellpadding** attribute defines the space between the content of a cell and its border, displayed or not
* The **cellspacing** attribute defines the size of the space between two cells in a percentage value or pixels

**Example**
```html
<table width="800" cellpadding="10" cellspacing="10">
  <thead>
    <tr>
      <th width="100">Header 1</th>
      <th>Header 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Content 1</td>
      <td>Content 2</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Footer 1</td>
      <td>Footer 2</td>
    </tr>
  </tfoot>
</table>
```

* To provide additional control over how cells fit into (or span across) columns, both **th** and **td** support the **colspan** attribute, which lets you specify how many columns wide the cell should be, with the default being 1. 
* Similarly, you can use the **rowspan** attribute on cells to indicate they should span more than one table row.

**Example**
```html
  <table border="1">
    <tr>
      <td rowspan="2">1 Column</td>
      <td>middle value</td>
      <td>middle value</td>
      <td rowspan="2">1 Column</td>
    </tr>
    <tr>
      <td>middle value</td>
      <td>middle value</td>
    </tr>
    <tr>
      <td colspan="4">Just 1 column for 4 spaces</td>
    </tr>
  </table>
```

#### Practice
[Exercise 10](exercises/html/ex_10.md)

## Favicon
* Favicon is an icon that we can show on our browser window (tabs)
* Most browsers will support .ico, .gif or .png but using the ICO format will ensure it works as far back as Internet Explorer 6
* There are lots of other icon types to consider these days as well and you can read more about it on the [MDN site](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML)

```html
  <head>
    <title>My site with a great Favicon!</title>
    <link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
  </head>
```

#### Practice
[Personal Site](exercises/html/personal_site.md)


##  Forms
* The **form** element represents a document section that contains interactive controls for submitting information to a web server
* We can find them everywhere and in different styles too!

**Search engines:**

Google:
![Google](resources/html/google.png)

Twitter:
![Twitter search](resources/html/buscar1.png)

Youtube:
![Youtube search](resources/html/youtube_search.png)

**Comments / Posts:**

Twitter post:
![Twitter post](resources/html/twit.png)

Medium: 
![Medium post](resources/html/medium_comment.png)

Facebook: 
![Medium post](resources/html/facebook_post.png)

**Log in / sign up**

Facebook:
![Facebook post](resources/html/facebook_signup.png)

* The form element has 3 important attributes:
  * action: the URI of a program that processes the form information
  * method: the HTTP method that the browser uses to submit the form: get or post 
    * get: corresponds to the HTTP GET method; form data are appended to the action attribute URI with a '?' as separator, and the resulting URI is sent to the server
    * post: corresponds to the HTTP POST method ; form data are included in the body of the form and sent to the server
  * enctype: when the value of the method attribute is post, enctype is the MIME type of content that is used to submit the form to the server. Possible values:
    * Default: 'application/x-www-form-urlencoded'
    * To send file content: 'multipart/form-data'
    * Just text: 'text/plain'
* [MDN form doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

```html
<form action="create_user.php" method="get" enctype="application/x-www-form-urlencoded" >
  My Form
</form>
```

* A form can have many different input types elements
* We can submit the form using a button to execute the form action and send the form data
* Many programing languages can process form data server side like C#, Java, JavaScript, PHP, Ruby and others
* Each input will have a `name` attribute so we can identify it
* The user will get a response after submitting and processing the data server side

### Inputs
* The **input** element is used to create interactive controls for web-based forms in order to accept data from the user
* How it works varies considerably depending on the value of its `type attribute`
* If this attributes is not specified, the `default` type adopted is `text`
* The available types are as follows: button, checkbox, color, date, datetime-local, email, file, hidden, image, month, number, password, range, reset, search, submit, tel, text, time, url, week
* [MDN input doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)

**Example:**
```html
<form>
  <input type="input-type" name="variable-name" >
</form>
```

#### Text
* Create basic single-line text fields (name, lastname, username, address)
* Use the type value of `text` to define this type of input
* You must remember to include name attribute on the **input** element, otherwise the text field's value won't be included with the submitted data
* [MDN input type text doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text)

**Example:**
```html
<form>
  <input type="text" name="username" >
</form>
```

* The `value` attribute contains the value of the text input
* The user will see any predefined value
* To clear the input the user will have to manually delete the input content

**Example:**
```html
<input type="text" name="username" value="harryp" >
```

* The `placeholder` attribute is typically rendered in a lighter color than the element's foreground color, and automatically vanishes when the user begins to enter text into the field

**Example:**
```html
<input type="text" name="username" placeholder="Please input a username" >
```

* The **size** attribute specified the number of characters the text input can display at a time
* This affects the width of the element, letting you specify the width in terms of characters rather than pixels
* As it's only a visual effect we can update it with CSS

**Example:**
```html
<input type="text" name="username" value="harryp" size="20" >
```

* You can specify a minimum length (in characters) for the entered value using the `minlength` attribute
* Similarly, use `maxlength` to set the maximum length of the entered value, in characters

**Example:**
```html
<input type="text" name="username" value="harryp" minlength="3" maxlength="20">
```

* If you try to submit the form with less than 4 characters, you'll be given an appropriate error message (which differs between browsers). 
* If you try to enter more than 8 characters, the browser won't let you.
* If you specify a `minlength` but do not specify `required`, the input is considered valid, since the user is not required to specify a value

#### Password
* The input type passowrd provide a way for the user to securely enter a password 
* The element is presented as a one-line plain text editor control in which the text is obscured so that it cannot be read, usually by replacing each character with a symbol such as the asterisk ("*") or a dot ("•")
* Set the type attribute to password
* We can use the **name**, **value**, **size**, **minlength** & **maxlength** attributes
* Remember that this hidden text is just a visual effect
* Use HTTPS to send client data to the server
* [MDN input type password doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/password)

**Example:**
```html
<form>
  <input type="password" name="pass" >
</form>
```

#### Submit button
* The input type `submit` is just a button that submits the form
* This type of element's value attribute contains the button's label
* If you don't specify a value, the button will have a default label, chosen by the user agent
* [MDN input submit doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/submit)

**Example:**
```html
<form>
  <input type="submit" value="Submit this form">
</form>
```

#### Practice
[Exercise 11](exercises/html/ex_11.md)

### Labels
* The **label** element represents a caption for an item in a user interface
* A **label** can be associated with a control either by placing the control element inside the **label** element, or by using the for attribute
* Such a control is called the labeled control of the label element
* One input can be associated with multiple labels
* [MDN label doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)

**Example:**
```html
<form>
  <label>Name:</label>
  <input type="text" name="name" />
  <label>Surname:</label>
  <input type="text" name="surname" />
</form>
```

* Also we could use it this way:

**Example:**
```html
<form>
  <label>
    Name:
    <input type="text" name="name" />
  </label>
  <label>
    Surname:
    <input type="text" name="surname" />
  </label>
</form>
```

* The label element has a **for** attribute
* Once we set the **for** attribute, the user will be able to click on the **label** element to get focus in the set for value
* The id of a labelable form-related element in the same document as the label element.
* The first such element in the document with an ID matching the value of the for attribute is the labeled control for this label element

**Example:**
```html
<form>
  <label for="nameid">Name:</label>
  <input type="text" name="name" id="nameid" />
  <label for="surnameid">Surname:</label>
  <input type="text" name="surname" id="surnameid" />
</form>
```

### Fieldset
* The **fieldset** element is used to group several controls as well as labels within a web form
* [MDN fieldset doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset)

**Example**
```html
<form>
  <fieldset>
    <label>Name:</label>
    <input type="text" name="name" />
    <label>Surname:</label>
    <input type="text" name="surname" />
  </fieldset>
</form>
```

* The **legend** element represents a caption for the content of its parent **fieldset**

**Example**
```html
<form>
  <fieldset>
    <legend>User Form</legend>
    <label>Name:</label>
    <input type="text" name="name" />
    <label>Surname:</label>
    <input type="text" name="surname" />
  </fieldset>
</form>
```

#### Radio buttons
* The `input type radio` elements are generally used in radio groups—collections of radio buttons describing a set of related options
* Only one radio button in a given group can be selected at the same time
* Radio buttons are typically rendered as small circles, which are filled or highlighted when selected
* To define a radio group each of the radio buttons in the group must have same name attribute
* The user will see a legend next to each radio button by using a label element or just plain text
* [MDN input type radio doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio)

**Example**
```html
<form>
  Are you a Jets Fan?
  <input type="radio" name="jetsfan" value="true"> Oh Yeahhhhhh, Go Jets!!!
  <input type="radio" name="jetsfan" value="false"> No
</form>
```

* Use the `checked` attribute with a `checked` value to select the default selected value
* In HTML5 when the attribute name and value is the same we can just add the attribute `checked`

**Example**
```html
<form>
  Are you a Jets Fan?
  <input type="radio" name="jetsfan" value="true" checked="checked"> Oh Yeahhhhhh, Go Jets!!!
  <input type="radio" name="jetsfan" value="false"> No
  <!-- <input type="radio" name="jetsfan" value="true" checked> Oh Yeahhhhhh, Go Jets!!! -->
</form>
```

#### Checkboxes
* The input elements of `type checkbox` are rendered by default as square boxes that are checked (ticked) when activated
* They allow you to select single values for submission in a form (or not).
* Radio buttons are similar to checkboxes, but with an important distinction:
> radio buttons are grouped into a set in which only one radio button can be selected at a time, whereas checkboxes allow you to turn single values on and off. Where multiple controls exist, radio buttons allow one to be selected out of them all, whereas checkboxes allow multiple values to be selected.
* To select multiple values we need to use the same name input
* Use the value attribute to set each input selected value
* The checked attribute and value works the same way as radio buttons
* [MDN input type checkbox doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)

**Example**
```html
<form>
  Select your favourite Harry Potter wizards
  <input type="checkbox" name="wizards" value="harry potter" checked="checked" > Harry Potter
  <input type="checkbox" name="wizards" value="hermione granger" checked> Hermione Granger
  <input type="checkbox" name="wizards" value="ron weasley"> Ron Weasley
  <input type="checkbox" name="wizards" value="aberforth dumbledore"> Aberforth Dumbledore
</form>
```

### Hidden
* The input elements of `type hidden` let web developers include data that cannot be seen or modified by users when a form is submitted
* A good example: the ID of the content that is currently being ordered or edited, or a unique security token 
* Hidden inputs are completely invisible in the rendered page, and there is no way to make it visible in the page's content
* A user will be able to see them on the source code

**Example:**
```html
<form>
  <input type="hidden" name="product-id" value="1" >
</form>
```

#### Image buttons
* The input elements of `type image` are used to create graphical submit buttons
* We can use a button image instead of the default submit one
* To define the image we use the **src** attribute (as the image element)
* [MDN input type image doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/image)

**Example:**
```html
<form>
  <input type="image" src="create_user_button.png" >
</form>
```

* To change the image size we can use the **height** & **width** attributes
* We'll use CSS to change the way elements have to look (friendly reminder)

#### Practice
[Exercise 12](exercises/html/ex_12.md)

### Text area
* The **textarea** element represents a multi-line plain-text editing control
* This element has an opening and close tag
* [MDN input textarea doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)

**Example**
```html
<textarea name="about">Rick Sanchez it's a great scientific..</textarea>
```

* Use the **placeholder** attribute to let the user know what to input

**Example**
```html
<textarea name="about" placeholder="Please let us know about yourself"></textarea>
```

* The **cols** attribute sets the textarea amount of columns
* The **rows** attribute sets the textarea amount of lines

**Example**
```html
<textarea name="about" cols="10" rows="2" >Initial textarea text!</textarea>
```

### Select
* The **select** element represents a control that provides a menu of options
* The **option** element is used to define an item contained in a **select** element
* As such, **option** can represent menu items in popups and other lists of items in an HTML document
* [MDN input select doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)
* [MDN input option doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)

**Example**
```html
<form>
  <select name="options">
    <option>First Item</option>
    <option>Second Item</option>
  </select>
</form>
```

* The **option** element uses a **value** attribute to define the value the user selects
* Also we can show the user a different text as an **option** content

**Example**
```html
<form>
  <select name="countries">
    <option value="">Please select a Country</option>
    <option value="arg">Argentina</option>
    <option value="bra">Brasil</option>
    <option value="chl">Chile</option>
    <option value="can">Canada</option>
  </select>
</form>
```

* We can use the **selected** attribute to select the default selected value
* This attribute uses the **selected** value and is the same attribute name we can just use the attribute name without a value (example: selected="selected")
* By default the first option is going to be selected

**Example**
```html
<form>
  <select name="countries">
    <option value="">Please select a Country</option>
    <option value="arg">Argentina</option>
    <option value="bra">Brasil</option>
    <option value="chl">Chile</option>
    <option value="can" selected="selected">Canada</option>
  </select>
</form>

OR

<form>
  <select name="countries">
    <option value="">Please select a Country</option>
    <option value="arg">Argentina</option>
    <option value="bra">Brasil</option>
    <option value="chl">Chile</option>
    <option value="can" selected>Canada</option>
  </select>
</form>
```

* The **multiple** attribute will allow the user to select multiple options
* The **size** attribute configures the number o items we'll show at the same time
* To select many items we'll use the control key

**Example**
```html
<form>
  <select name="countries" multiple="multiple" size="4">
    <option value="">Please select a Country</option>
    <option value="arg">Argentina</option>
    <option value="bra">Brasil</option>
    <option value="chl">Chile</option>
    <option value="can" selected>Canada</option>
  </select>
</form>
```

### Buttons
* The **button** element represents a clickable button, which can be used in forms, or anywhere in a document that needs simple, standard button functionality
* To set the button content we need to use an opening and close tags
* Add the **value** attribute if you need to submit this element value
* [MDN button doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)

**Example**
```html
<form>
  <button value="create" name="create-user">+ User</button>
</form>
```

* We can add any html content like an image

**Example**
```html
<form>
  <button>
    <img src="plus-icon.png" alt="plus icon" />
    User
  </button>
</form>
```

#### File 
* The **file** input type is a control that lets the user select a file
* Use the accept attribute to define the types of files that the control can select
* As we're going to be submitting more than just text we need to change the form enctype to enctype="multipart/form-data" and use the post method
* By default we can only select one file
* Use the **multiple** attribute indicates whether the user can enter more than one value (only HTML5 and all browsers might not support it)
* [MDN input type file doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file)

**Example**
```html
<form action="upload.php" method="post" enctype="multipart/form-data">
  <input type="file" name="filename" />
  <input type="file" name="filename" multiple="multiple" />
  <input type="file" name="filename" multiple />
</form>
```

#### Practice
[Exercise 13](exercises/html/ex_13.md)

#### New HTML5 input types
* HTML5 adds some new specific inputs
* If the browser doesn't support them it will show an input type text element
* [HTML5 forms input types](http://html5doctor.com/html5-forms-input-types/)
* [See them in action](https://robertnyman.com/html5/forms/input-types.html)

##### Date
* The input `type date` is a control for entering a date (year, month, and day, with no time)
* We can set a initial value using the **value** attribute
* [MDN input type date doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date)

**Example**
```html
<form>
  <input type="date" name="birthday" />
  <input id="date" type="date" value="1980-04-02">
</form>
```

##### Email
* The input `type email` is a field for editing an e-mail address
* [MDN input type email doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email)

**Example**
```html
<form>
  <input type="email" name="email" />
</form>
```

##### URL
* The input `type url` is a field for entering a URL
* [MDN input type url doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/url)

**Example**
```html
<form>
  <input type="url" name="personalsite" />
</form>
```

##### Search
* The input `type search` is a single-line text field for entering search strings
* Line-breaks are automatically removed from the input value

**Example**
```html
<form>
  <input type="search" name="query" />
</form>
```

#### Practice
[Exercise 14](exercises/html/ex_14.md)


### Form validation
* To make sure that the data users fill out in forms is in the correct format we need to process the form inputs
* We can validate on client and server side
* We'll use some HTML elements attribute to validate our forms on the client side
* If we validate on the client side we avoid sending wrong data to the server so we have many requests
* HTML5 added element validations
* Also we can use JavaScript to validate our inputs too

#### Required
* The **required** attribute specifies that the user must fill in a value before submitting a form
* As it's a boolean attribute we can just write the attribute name without any value (required="required" or just required)
* The form won't submit until all required inputs are completed

**Example**
```html
<form>
  <input type="text" name="name" required />
  <input type="text" name="name" required="required" />
</form>
```

#### Regex
* A regular expressions is a pattern used to match character combinations in strings
* We can use them in many different languages
* The attribute **pattern** allows us to enter a valid regex as value
* This regular expression will be executed with the input value to see if it match
* The pattern must match the entire value
* This attribute applies when the value of the type attribute is text, search, tel, url, email, or password, otherwise it is ignored
* The regular expression language is the same as JavaScript RegExp algorithm
* The pattern is not surrounded by forward slashes
* It's a good practice to add the **title** attribute to explain the allowed values
* Add the placeholder if you use this attribute or it might not show the title content
* [Wikipeda - Regular_expression](https://en.wikipedia.org/wiki/Regular_expression)
* [Nice regex tutorial](https://regexone.com)

**Example**
```html
<form>
  <input type="text" name="name" pattern="^[a-zA-Z]+$" placeholder="name" title="Input only letters" /> 
  <input type="text" name="age" pattern="\d+" placeholder="age" title="Input only numbers" />
  <input type="submit" value="Submit">
</form>
```

* Use [caniuse.com](http://caniuse.com/#search=required) to find out if a feature is compatible with the browser you're targeting
* To know more about this subject you can read the [MDN form validation guide](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms/Form_validation)

## HTML5 new sections
*  HTML5 specification brings several new elements to web developers allowing them to describe the structure of a web document with standard semantics
* All content lying inside the **body** element is part of a section
* Sections in HTML5 can be nested
* Each section can have its own heading hierarchy. Therefore, even a nested section can have an **h1**
* HTML5 adds the following features:
  * Semantics: allowing you to describe more precisely what your content is
  * Connectivity: allowing you to communicate with the server in new and innovative ways
  * Offline and storage: allowing webpages to store data on the client-side locally and operate offline more efficiently
  * Multimedia: making video and audio first-class citizens in the Open Web
  * 2D/3D graphics  and effects: allowing a much more diverse range of presentation options
  * Performance and integration: providing greater speed optimization and better usage of computer hardware
  * Device access: allowing for the usage of various input and output devices
  * Styling: letting authors write more sophisticated themes
* [MDN HTML5 guide](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)

* In the semantics section we find new outlining and sectioning elements like **section**, **article**, **nav**, **header**, **footer** and **aside**. 

* The **header** element represents introductory content, typically a group of introductory or navigational aids
* It may contain some heading elements but also other elements like a logo, a search form, an author name, and so on
* The **nav** element represents a section of a page whose purpose is to provide navigation links, either within the current document or to other documents
* The **aside** element represents a portion of a document whose content is only indirectly related to the document's main content
* The **section** element represents a standalone section — which doesn't have a more specific semantic element to represent it — contained within an HTML document
* The **footer** element represents a footer for its nearest sectioning content or sectioning root element
* A footer typically contains information about the author of the section, copyright data or links to related documents

**Example**
```html
<body>
  <header>
    <h1>Title of our document</h1>
  </header>
  <nav>
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="bio.html">Bio</a></li>
    </ul>
  </nav>
  <aside>
    <p>Aside Content</p>
  </aside>
  <section>
    <h1>Section Main Title</h1>
    <p>Section Content</p>
  </section>
  <footer>
    <p>Site Footer</p>
  </footer>
</body>
```

* The *article element represents a self-contained composition in a document, page, application, or site, which is intended to be independently distributable or reusable. Examples include: a forum post, a magazine or newspaper article, or a blog entry
* The **address** element indicates that the enclosed HTML provides contact information for a person or people, or for an organization
* The HTML **time** element represents one of the following: a time on a 24-hour clock or a precise date in the Gregorian calendar

**Example**
```html
<body>
  <article>
    <p>Author Name</p>
    <time>02/02/2017</time>
    <address>
      136 Market Av.
    </address>
  </article>
</body>
```

## Iframe
* The **iframe** element represents a nested browsing context, effectively embedding another HTML page into the current page
* The **src** attribute accepts the URL of the page to embed as value
* Use the **height** & **width** attributes to set the iframe size
* The **seamless** is a boolean attribute indicates that the browser should render the inline frame in a way that makes it appear to be part of the containing document
* The **frameborder** attribute tells the browser to draw a border between this frame. If we set the value to 0 tells the browser not to draw a border between this frame
* [MDN iframe doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)

**Example**
```html
<body>
  <iframe src="other_document.html" height="200" width="200" seamless frameborder="0"></iframe>
</body>
```

#### Practice
[Exercise 15](exercises/html/ex_15.md)

## Video
* The **video** element embeds a media player which supports video playback into the document
* This element contains one or more video sources
* To specify a video source, use either the **src** attribute or the **source** element (the browser will choose the most suitable one)
* Different browsers might support different media types
  * H264: Internet Explorer & Safari
  * WebM: Android, Chrome, Firefox and Opera
* For a list of supported formats you can see the [MDN supported media formats guide](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats)
* Each browser will show the player in a different way
* Also we can still use flash plugin to reach more users
* This are some of the attributes that we can use to configure the video element
  * **src:** set this value with the video filename or path
  * **width:** & **height:** to set the video player size
  * **poster:** we can set a picture file or path that will show while the video is downloaded
* [MDN video doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

**Example**
```html
<body>
  <video src="myvideo.mp4" poster="myvideo.jpg" width="600" height="400">
    <p>Video description</p>
  </video>
</body>
```

* The video element has many attributes that works as a boolean value to turn on/off the different features
  * **controls:** if this attribute is present, the browser will offer controls to allow the user to control video playback, including volume, seeking, and pause/resume playback
  * **autoplay:** if specified, the video automatically begins to play back as soon as it can do so without stopping to finish loading the data
  * **loop:** upon reaching the end of the video the player automatically seek back to the start
  * **preload:** This enumerated attribute is intended to provide a hint to the browser about what the author thinks will lead to the best user experience.
    * It may have one of the following values:
      * **none:** indicates that the video should not be preloaded
      * **auto:** indicates that the whole video file could be downloaded, even if the user is not expected to use it
      * **metadata:** indicates that only video metadata (e.g. length) is fetched
      * **An empty string**: synonym of the auto values

**Example**
```html
<body>
  <video 
    src="myvideo.mp4" 
    poster="myvideo.jpg"
    width="600" 
    height="400"
    controls
  >
    <p>Video Descritpion</p>
  </video>
</body>
```

## Audio
* The **audio** element is used to embed sound content in documents
* It may contain one or more audio sources, represented using the src attribute or the **source** element: the browser will choose the most suitable one 
* It can also be the destination for streamed media, using a MediaStream
* This element works in a similar way as the **video** one
* The **audio** element supports the same attribute video does: **src**, **controls**, **autoplay**, **preload** & **loop**
* Some browsers have better support for some media types:
  * **MP3:** Safari 5+, Chrome 6+ e IE9
  * **Ogg Vorbis:** Firefox 3.6, Chome 6, Opera 1.5 e IE9
* Also if the browser doesn't support this tag it will render the element content (like the paragraph in the example)
* [MDN audio doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
* [MDN media stream doc](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream)

**Example**
```html
<body>
  <audio src="ejemplo-audio.ogg" autoplay controls>
    <p>Audio description.</p>
  </audio>
</body>
```

### Source
* The **source** element specifies multiple media resources for the **picture**, **audio** and **video** elements
* It is an empty element
* It is commonly used to serve the same media content in multiple formats supported by different browsers 
* If we use this element we don't have to use the **src** attribute
* This element supports the following attributes:
  * **src:** required for **audio** and **video**, address of the media resource
    * The value of this attribute is ignored when the **source** element is placed inside a **picture** element
  * **type:** the MIME-type of the resource, optionally with a codecs parameter
    * See [RFC 4281 guide](https://tools.ietf.org/html/rfc4281) for information about how to specify codecs
* [MDN source doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source)
* [MDN picture doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture)

**Example**
```html
<body>
  <video poster="myvideo.jpg" controls>
    <source src="myvideoo.mp4" type="video/mp4">
    <source src="myvideo.webm" type="video/webm"> 
    <source src="myvideo.ogv" type="video/ogg"> 
    <source src="myvideo.3gp" type="video/3gp">
    <p>Vide description</p>
  </video>
  <audio autoplay controls>
    <source src="myaudio.mp3" />
    <source src="myaudio.ogg" />
    <p>Audio description.</p>
  </audio>
</body>
```

## Metadata
* The **meta** element represents metadata that cannot be represented by other HTML meta-related elements
* This element will work as **head** element content only
* The user won't see this element content
* This are some of the attributes that we can configure:
  * **author:** author which defines the name of the document's author
  * **charset:** this attribute declares the page's character encoding
  * **description:** contains a short and accurate summary of the content of the page
  * **keywords:** contains words relevant to the page's content separated by commas
  * **viewport:** gives hints about the size of the initial size of the viewport
    * Used by mobile devices only
    * Read the viewport MDN guide section to find out more about the different values this attribute supports
* Read the [MDN meta doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) too know more about the different attributes that we can use

**Example**
```html
<head>
  <meta charset="UTF-8">
  <meta name="description" content="My Site description">
  <meta name="author" content="John Doe">
  <meta name="keywords" content="HTML,CSS,XML,JavaScript">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

* Read the [Wikiped character encoding doc](https://en.wikipedia.org/wiki/Character_encoding) to know more about how encoding works
* [Wikipedia UTF-8 doc](https://en.wikipedia.org/wiki/UTF-8)

## HTML Entity
* An HTML entity is a piece of text ("string") that begins with an ampersand (&) and ends with a semicolon (;)
* Entities are frequently used to display reserved characters (which would otherwise be interpreted as HTML code), and invisible characters (like non-breaking spaces) 
* You can also use them in place of other characters that are difficult to type with a standard keyboard
[MDN entity doc](https://developer.mozilla.org/en-US/docs/Glossary/Entity)
* [List of HTML entities](https://www.freeformatter.com/html-entities.html)

**Example**
```html
<body>
  <p>&lt; less than</p>
  <p>&gt; greater than</p>
  <p>&amp; ampersand</p>
  <p>&copy; Copyright</p>
  <p>&reg; Registered Trademark</p>
  <p>&trade; Trademark</p>
</body>
```

#### Practice
[Exercise 16](exercises/html/ex_16.md)

[Exercise 17](exercises/html/ex_17.md)

## Extra:
[HTML5 Specs](https://dev.w3.org/html5/spec-preview/Overview.html)

## Congratulations, you made it, now you know HTML!!
![Super Hero HTML5](resources/html/html_superhero.jpg)
