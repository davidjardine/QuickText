# QuickText and HTML Tags

The majority of HTML tags, and certainly the common ones, work no differently in QuickText than you'd expect if you're familiar with web development. The differences you may notice with QuickText templates have to do with edge-cases or are additional features added on top of the basic display decisions broswers make when rendering HTML.  

This document goes over every valid HTML tag and has a brief summary adapted from the [MDN Web Docs HTML Elements Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements). Then any differences or important notes about their usage in QuickText templates will be explained. 

## Required Tags

HTML has a few mandatory tags that every HTML document has to include, like the html tag itself. I don't want this document to be an intro to HTML, but if you are not familiar with the DOM (document object model) then you can check it out here: [MDN Docs: Using the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Using_the_Document_Object_Model#what_is_a_dom_tree). The tags required in pretty much any functional HTML page and that you'll see in every QuickText template are:

- html
- head
- base
- meta
- link
- body

While most of these are "hidden" tags that don't change anything visually there are many benefits to requiring them in every page. This isn't meant to be a comprehensive HTML tutorial so I've included a link to the MDN Web Docs (and even for people who have worked with HTML for decades I find there is always something new to learn in the technical specification of these tags) that you can check out here: [MDN Docs: Metadata Tags](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements#document_metadata).  

## Sectioning Tags

HTML has several tags that are known as "sectioning tags" or "semantic tags" which are a mid-level tag in the DOM tree hierarchy that are meant to help the developer and site visitors (or at least their browser) to better follow the flow of the page content. This is a quick list of the semantic or section tags and brief descriptions, summarized from [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements#content_sectioning).  

**nav**  
Represents a section of a page whose purpose is to provide navigation links, either within the current document or to other documents.  

**footer**  
Represents a footer for its nearest ancestor sectioning content or sectioning root element. Typically contains information about the author of the section, copyright data, or links to related documents.  

**main**  
Represents the primary content of the document. The main content area consists of content that is directly related to or expands upon the central topic of the page.  

**article**  
A self-contained piece of content which is intended to be independently distributable (i.e via RSS feeds). Examples: forum post, newspaper article, a blog entry, a product card, a user-submitted comment, etc.  

**aside**  
Represents a portion of a document whose content is only indirectly related to the document's main content. Frequently presented as sidebars or call-out boxes.  

**header**  
Represents introductory content, typically a group of introductory or navigational aids. It may contain some heading elements but also a logo, a search form, an author name, and other elements.  

**h1, h2, h3, h4, h5, h6**  
Represent six levels of section headings. h1 is the highest section level and h6 is the lowest.  

**hgroup**  
Represents a heading grouped with any secondary content, such as subheadings, an alternative title, or a tagline.  

**address**  
Indicates that the enclosed HTML provides contact information for a person or people, or for an organization.  

**search**  
Represents a part that contains a set of form controls or other content related to performing a search or filtering operation.  

**details**  
Creates a disclosure widget in which information is visible only when the widget is toggled into an "open" state. A summary or label must be provided using the summary element.

**summary**  
Specifies a summary, caption, or legend for a details element's disclosure box. Clicking the summary element toggles the state of the parent details element open and closed.

**section**  
Represents a generic standalone section of a document, which doesn't have a more specific semantic element to represent it. 

**dialog**  
Represents a dialog, pop-up, or other interactive component.

With QuickText, the only **major** change (and it is actually quite minor in the grand scheme of things) is that address is not used as a sectioning tag, but as an inline tag to apply the same styles to any contact information written within paragraphs.  

### QuickText Section Tags

Looking only in the body tag (since no content should ever be outside the body tag) all QuickText DOMs will have **header**, **main** , and **footer** tags (in that order) as the three sections within the body where content can be placed.  

In the vast majority of sites the main menu is in the top of the screen, so the **nav** tag usually goes within the header. There can be multiple navigation menus so there may be additional places where the nav tag appears in the DOM.  

Same goes for the **search** tag, if the site implements some sort of internal searching feature it will usually be in the header (note: if the search bar is an external search it probably should not be in the header tag).  

Both **hgroup** and the **h2** to **h6** tags can appear pretty much anywhere in the DOM, but the **h1** will always be at the top of the main tag, and it will be the only h1 tag in the document. This is an accessibility feature to ensure that the main title that most accurately describes the entire page is easily found by screen-readers and other devices.  

The **article** , **aside** , **details** , **summary** , and **section** tags will always be within the main tag.  

The **article** tag may be the only direct child tag of main with the rest of the content on the page being contained within the article tag, but this depends on the type of page.  

The **dialog** tag is the only one that can be outside the main tag because it always exists outside the regular flow of the document anyway.  

## Content Tags

Many beginner web developers learn to accomplish complicated layouts and designs using DIV and SPAN tags because they can be used to represent anything. This unfortunately is also exactly why they are horrible for accessibility and are rarely used in QuickText templates. When they ARE used (there are definitely valid uses for them that don't compromise accessibility) they should be used sparingly and almost never nested within each other, as shown below.  

DIV SOUP EXAMPLE HERE  

The example excludes the classes, ids, and styles that would typically be in the div tags for the sake of keeping the code easy to read.  

**div**
A generic block-level container with no effect on the content or layout until styled in some way using CSS. Only used in QuickText when no appropriate alternative exists.  

**span**
A generic inline-level container with no effect on the content and does not represent anything in particular. Only used in QuickText when no other semantic element is appropriate.  

### TEXT CONTENT

**p**    
Represents a paragraph and typically consists of only text but can contain other elements, including multimedia, that are associated with that paragraph.  

**a**  
Uses the href attribute to create a hyperlink to web pages, files, email addresses, locations within the current page, or anything else a URL can address.  

**q**  
A short inline quotation. QuickText encloses the text in double quotation marks.  

**blockquote**  
An extended block-level quotation. QuickText applies an indent to visually separate it from the surrounding text. 

**cite**
Used at the end of a q or blockquote tag to provide citation data. QuickText will display it in your chosen reference style, defaulting to IEEE footnote citations if no preference is given. 

**time**  
Represents a specific period in time. QuickText templates include the datetime attribute to translate dates into machine-readable format.

**abbr**  
Represents an abbreviation or acronym.  

**mark**  
Represents text which is marked or highlighted for reference or notation purposes due to the marked passage's relevance in the enclosing context.  

**sub**  
Specifies inline text which should be displayed as subscript for solely typographical reasons. Subscripts are typically rendered with a lowered baseline using smaller text.

**sup**  
Specifies inline text which is to be displayed as superscript for solely typographical reasons. Superscripts are usually rendered with a raised baseline using smaller text.

**pre**  
Represents preformatted text which is to be presented exactly as written in the HTML file. Whitespace inside this element is displayed.  

**code**  
Displays its contents styled in a fashion intended to indicate that the text is a short fragment of computer code. QuickText displays the text in the system's default monospace font.

**samp**  
Used to enclose inline text which represents sample (or quoted) output from a computer program. QuickText displays the text in the system's default monospace font.

**data**  
Links a given piece of content with a machine-readable translation.

**dfn**  
Used to indicate the term being defined within the context of a definition phrase or sentence. The ancestor p element, the dt/dd pairing, or the nearest section ancestor of the dfn element, is considered to be the definition of the term.

**s**  
Renders text with a strikethrough, or a line through it. For document edits use the del and ins elements, as appropriate.  

**del**  
Represents a range of text that has been deleted from a document.

**ins**  
Represents a range of text that has been added to a document.

#### TEXT EMPHASIS
In HTML these tags are still supported to convey meaning beyond the text, but should never be used purely for styling text. For example, if you just want to bold something so it looks nice you would not use the b tag, but if you wanted to specifically draw attention to the word you can use the b tag.  

**b**  
Formerly known as the Boldface element, it is used to draw the reader's attention to the element's contents, which are not otherwise granted special importance.  

**i**  
Represents a range of text that is set off from the normal text for some reason, such as idiomatic text, technical terms, and taxonomical designations, among others.  

**u**  
Represents a span of inline text which should be rendered in a way that indicates that it has a non-textual annotation.    

**em**  
Marks text that has stress emphasis. The em element can be nested, with each nesting level indicating a greater degree of emphasis.  

**strong**  
Indicates that its contents have strong importance, seriousness, or urgency.  

**small**  
Represents side-comments and small print, like copyright and legal text, independent of its styled presentation.  

### LAYOUT

**hr**  
Represents a thematic break between paragraph-level elements: for example, a change of scene in a story, or a shift of topic within a section.

**br**  
Produces a line break in text (carriage-return). It is useful for writing a poem or an address, where the division of lines is significant. NEVER to be used to create extra spacing between two block-level elements, use CSS for that.

### LISTS

**ul**  
Represents an unordered list of items, typically rendered as a bulleted list.  

**menu**  
An alternative to ul with no differences. Just use the ul tag.  

**ol**  
Represents an ordered list of items — by default rendered as a numbered list.  

**li**  
Represents an item in a list. It must be contained in a parent element: an ordered list (ol), an unordered list (ul), or a menu (menu).  

**dl**  
Represents a description list. The element encloses a list of groups of terms (specified using the dt element) and descriptions (provided by dd elements). Common uses for this element are to implement a glossary or to display metadata (a list of key-value pairs).  

**dt**  
Specifies a term in a description or definition list, and as such must be used inside a dl element. It is usually followed by a dd element; however, multiple dt elements in a row indicate several terms that are all defined by the immediate next dd element.  

**dd**  
Provides the description, definition, or value for the preceding term (dt) in a description list (dl).  

### MULTIMEDIA

**figcaption**  
Represents a caption or legend describing the rest of the contents of its parent figure element.  

**figure**  
Represents self-contained content, potentially with an optional caption, which is specified using the figcaption element. The figure, its caption, and its contents are referenced as a single unit.  

**area**  
Defines an area inside an image map that has predefined clickable areas. An image map allows geometric areas on an image to be associated with hyperlink.  

**audio**  
Used to embed sound content in documents. It may contain one or more audio sources, represented using the src attribute or the source element: the browser will choose the most suitable one. It can also be the destination for streamed media, using a MediaStream.  

**img**  
Embeds an image into the document.  

**map**  
Used with area elements to define an image map (a clickable link area).  

**track**  
Used as a child of the media elements, audio and video. It lets you specify timed text tracks (or time-based data), for example to automatically handle subtitles. The tracks are formatted in WebVTT format (.vtt files)—Web Video Text Tracks.  

**video**  
Embeds a media player which supports video playback into the document. You can also use video for audio content, but the audio element may provide a more appropriate user experience.  

**picture**  
Contains zero or more source elements and one img element to offer alternative versions of an image for different display/device scenarios.  

**source**  
Specifies multiple media resources for the picture, the audio element, or the video element. It is a void element, meaning that it has no content and does not have a closing tag.  

**svg**  
Container defining a new coordinate system and viewport. It is used as the outermost element of SVG documents, but it can also be used to embed an SVG fragment inside an SVG or HTML document.  


### TABLES

**table**  
Represents tabular data—that is, information presented in a two-dimensional table comprised of rows and columns of cells containing data.  

**caption**  
Specifies the caption (or title) of a table.  

**thead**  
Encapsulates a set of table rows (tr elements), indicating that they comprise the head of a table with information about the table's columns, usually in the form of column headers (th elements).  

**tbody**  
Encapsulates a set of table rows (tr elements), indicating that they comprise the body of a table's (main) data.  

**tfoot**  
Encapsulates a set of table rows (tr elements), indicating that they comprise the foot of a table with information about the table's columns. This is usually a summary of the columns, e.g., a sum of the given numbers in a column.  

**tr**  
Defines a row of cells in a table. The row's cells can then be established using a mix of td (data cell) and th (header cell) elements.  

**th**  
A child of the tr element, it defines a cell as the header of a group of table cells.  

**td**  
A child of the tr element, it defines a cell of a table that contains data.  

**col**  
Defines one or more columns in a column group represented by its implicit or explicit parent colgroup element. The col element is only valid as a child of a colgroup element that has no span attribute defined.  

**colgroup**  
Defines a group of columns within a table.  

### FORM ELEMENTS

**form**  
Represents a document section containing interactive controls for submitting information.  

**input**  
Used to create interactive controls for web-based forms to accept data from the user with a wide variety of types of input data and control widgets.  

**label**  
Represents a caption for an item in a user interface.  

**fieldset**  
Used to group several controls as well as labels (label) within a web form.  

**legend**  
Represents a caption for the content of its parent fieldset.  

**select**  
Represents a control that provides a menu of options.  

**optgroup**  
Creates a grouping of options within a select element.  

**option**  
Used to define an item contained in a select or a datalist element. As such, option can represent menu items in popups and other lists of items in an HTML document.  

**datalist**  
Contains a set of option elements that represent the permissible or recommended options available to choose from within other controls.  

**button**  
An interactive element activated using a user's input device in order to trigger an action.  

**meter**  
Represents either a scalar value within a known range or a fractional value.  

**output**  
Container element into which a site or app can inject the results of a calculation or the outcome of a user action.  

**progress**  
Displays an indicator showing the completion progress of a task, typically displayed as a progress bar.  

**selectedcontent**  
Displays the content of the currently selected option inside a closed select element.  

**textarea**  
Represents a multi-line plain-text editing control, useful when you want to allow users to enter a sizeable amount of free-form text, for example, a comment on a review or feedback form.  


## OTHER

**bdi**  
Tells the browser's bidirectional algorithm to treat the text it contains in isolation from its surrounding text. It's particularly useful when a website dynamically inserts some text and doesn't know the directionality of the text being inserted.  

**bdo**  
Overrides the current directionality of text, so that the text within is rendered in a different direction.  

**kbd**  
Represents a span of inline text denoting textual user input from a keyboard, voice input, or any other text entry device. By convention, the user agent defaults to rendering the contents of a kbd element using its default monospace font, although this is not mandated by the HTML standard.  

**rp**  
Used to provide fall-back parentheses for browsers that do not support the display of ruby annotations using the ruby element. One rp element should enclose each of the opening and closing parentheses that wrap the rt element that contains the annotation's text.  

**rt**  
Specifies the ruby text component of a ruby annotation, which is used to provide pronunciation, translation, or transliteration information for East Asian typography. The rt element must always be contained within a ruby element.  

**ruby**  
Represents small annotations that are rendered above, below, or next to base text, usually used for showing the pronunciation of East Asian characters. It can also be used for annotating other kinds of text, but this usage is less common.  

**math**  
The top-level element in MathML. Every valid MathML instance must be wrapped in it. In addition, you must not nest a second math element in another, but you can have an arbitrary number of other child elements in it.  

**var**  
Represents the name of a variable in a mathematical expression or a programming context. It's typically presented using an italicized version of the current typeface, although that behavior is browser-dependent.  

**canvas**  
Container element to use with either the canvas scripting API or the WebGL API to draw graphics and animations.  

**noscript**  
Defines a section of HTML to be inserted if a script type on the page is unsupported or if scripting is currently turned off in the browser.  

**script**  
Used to embed executable code or data; this is typically used to embed or refer to JavaScript or other languages such as WebGL's GLSL shader programming language and JSON.  

**wbr**  
Represents a word break opportunity—a position within text where the browser may optionally break a line, though its line-breaking rules would not otherwise create a break at that location.  

**embed**  
Embeds external content at the specified point in the document. This content is provided by an external application or other source of interactive content such as a browser plug-in.  

**fencedframe**  
Represents a nested browsing context, like iframe but with more native privacy features built in.  

**iframe**  
Represents a nested browsing context, embedding another HTML page into the current one.  

**object**  
Represents an external resource, which can be treated as an image, a nested browsing context, or a resource to be handled by a plugin.  

**slot**  
Part of the Web Components technology suite, this element is a placeholder inside a web component that you can fill with your own markup, which lets you create separate DOM trees and present them together.  

**template**  
A mechanism for holding HTML that is not to be rendered immediately when a page is loaded but may be instantiated subsequently during runtime using JavaScript.  
