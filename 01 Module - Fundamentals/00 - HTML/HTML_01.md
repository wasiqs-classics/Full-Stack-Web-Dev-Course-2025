# HTML Tutorial: Part 1

## 1. HTML Fundamentals

### What is HTML?

HTML (HyperText Markup Language) is the standard markup language used to create web pages. It provides the structure for web content by using a system of elements and tags that define how content appears on a page.

Think of HTML as the skeleton of a webpage - it gives structure to content but doesn't handle styling (that's what CSS does) or interactive functionality (which JavaScript provides).

### How HTML Works

HTML uses "markup" to annotate text, images, and other content for display in a web browser. HTML markup consists of special elements like `<p>` for paragraphs, `<img>` for images, and many others. Each element consists of tags, typically an opening tag and a closing tag, with content in between.

Let's start with the basic structure of an HTML document:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First HTML Page</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>This is my first HTML page.</p>
</body>
</html>

```

Let's break down each part:

### Document Type Declaration

`<!DOCTYPE html>` - This is the document type declaration (not an HTML tag). It tells the browser which version of HTML the page is using. The declaration shown is for HTML5, the latest version.

### The HTML Element

`<html lang="en">` - This is the root element that contains all other HTML elements. The `lang` attribute specifies the language of the document (English in this case), which helps with accessibility and search engines.

### The Head Section

The `<head>` element contains metadata about the document - information that isn't directly displayed on the page:

```html
<meta charset="UTF-8">
```
This specifies the character encoding for the document (UTF-8 covers almost all characters and symbols).

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
This is crucial for responsive design, making your page look good on all devices. It sets the viewport width to the device width and establishes the initial zoom level.

```html
<title>My First HTML Page</title>
```
This defines the title of the document, which appears in the browser tab and in search results.

### The Body Section

The `<body>` element contains all the content that is visible to users when they visit your page, such as text, images, links, tables, etc.

## Semantic HTML Elements

Semantic elements clearly describe their meaning to both the browser and the developer. They provide structural meaning to your content, making your HTML more readable and better for accessibility and SEO.

Let's create an example that uses the main semantic elements:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Semantic HTML Example</title>
</head>
<body>
    <!-- Header typically contains introductory content, navigation, logo, etc. -->
    <header>
        <h1>My Travel Blog</h1>
        <!-- Nav element defines a set of navigation links -->
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#destinations">Destinations</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Main element contains the main content of the document -->
    <main>
        <!-- Section element represents a standalone section -->
        <section id="featured">
            <h2>Featured Destination</h2>
            <!-- Article element represents a self-contained composition -->
            <article>
                <h3>Beautiful Kyoto, Japan</h3>
                <p>Kyoto, once the capital of Japan, is a city on the island of Honshu.</p>
                <!-- Figure element is used for self-contained content like images, diagrams, etc. -->
                <figure>
                    <img src="kyoto.jpg" alt="Scenic temple in Kyoto surrounded by maple trees">
                    <figcaption>Kiyomizu-dera Temple during autumn</figcaption>
                </figure>
            </article>
        </section>

        <section id="recent-posts">
            <h2>Recent Posts</h2>
            <article>
                <h3>A Weekend in Paris</h3>
                <p>Exploring the city of lights in just 48 hours...</p>
            </article>
            <article>
                <h3>Hiking the Inca Trail</h3>
                <p>My journey to Machu Picchu and the challenges along the way...</p>
            </article>
        </section>

        <!-- Aside element represents content tangentially related to the content around it -->
        <aside>
            <h2>About the Author</h2>
            <p>Jane is a travel enthusiast who has visited over 30 countries.</p>
        </aside>
    </main>

    <!-- Footer typically contains authorship information, copyright, contact info, etc. -->
    <footer>
        <p>&copy; 2025 Travel Blog. All rights reserved.</p>
        <address>
            Contact: <a href="mailto:info@travelblog.example">info@travelblog.example</a>
        </address>
    </footer>
</body>
</html>

```

Let's examine these semantic elements in detail:

- `<header>`: Contains introductory content, typically a logo, heading, and navigation menu.
- `<nav>`: Defines a navigation menu.
- `<main>`: Contains the main content of a document. There should be only one `<main>` element per page.
- `<section>`: Represents a standalone section of content.
- `<article>`: Represents a self-contained composition that could be distributed independently (like a blog post).
- `<aside>`: Contains content tangentially related to the content around it (like a sidebar).
- `<figure>` and `<figcaption>`: Used to encapsulate media with a caption.
- `<footer>`: Contains footer information for its nearest sectioning content or sectioning root element.
- `<address>`: Provides contact information for the nearest article or body element.

### HTML Comments

Comments in HTML are not displayed in the browser but can help document your code:

```html
<!-- This is a comment. It won't be visible in the browser. -->
```

Comments are useful for leaving notes to yourself or other developers about the code.

## 2. Content Tags

### Text Formatting

HTML provides various elements for text formatting. Here are the most important ones:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Text Formatting in HTML</title>
</head>
<body>
    <h1>This is a Level 1 Heading</h1>
    <h2>This is a Level 2 Heading</h2>
    <h3>This is a Level 3 Heading</h3>
    <h4>This is a Level 4 Heading</h4>
    <h5>This is a Level 5 Heading</h5>
    <h6>This is a Level 6 Heading</h6>

    <p>This is a paragraph of text. HTML paragraphs are defined with the p tag.</p>
    
    <p>This paragraph contains <strong>strongly emphasized text</strong> and <em>emphasized text</em>.</p>
    
    <p>You can create a line break<br>like this.</p>
    
    <p>HTML also supports <mark>highlighted text</mark>, <small>smaller text</small>, <del>deleted text</del>, and <ins>inserted text</ins>.</p>
    
    <p>For technical content, you might use <code>code snippets</code>, <kbd>keyboard input</kbd>, <samp>sample output</samp>, or <var>variables</var>.</p>
    
    <blockquote>
        This is a blockquote. It's often used to quote content from another source.
        <cite>- Source Title</cite>
    </blockquote>
    
    <p>When you need to group inline elements, you can use a <span style="color: blue;">span element</span>.</p>
    
    <div>
        The div element is a block-level container that can group larger sections of content.
    </div>
</body>
</html>

```

Let's explore these text elements:

- Headings (`<h1>` through `<h6>`): Used for titles and subtitles, with `<h1>` being the most important and `<h6>` the least. They create a hierarchical structure for your content.

- Paragraph (`<p>`): Used for blocks of text.

- Text emphasis:
  - `<strong>`: Indicates text with strong importance (typically bold)
  - `<em>`: Emphasizes text (typically italic)
  - `<mark>`: Highlights text (like a highlighter pen)
  - `<small>`: Represents smaller text
  - `<del>`: Represents deleted text (typically with strikethrough)
  - `<ins>`: Represents inserted text (typically underlined)

- Technical text:
  - `<code>`: For code snippets
  - `<kbd>`: For keyboard input
  - `<samp>`: For sample output
  - `<var>`: For variables

- `<blockquote>`: For quoting blocks of content from another source
- `<cite>`: For referencing a creative work, author, or resource

- `<span>`: An inline container for text
- `<div>`: A block-level container for larger chunks of content

### Lists

HTML supports several types of lists:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Lists</title>
</head>
<body>
    <h2>Unordered List</h2>
    <ul>
        <li>Item 1</li>
        <li>Item 2</li>
        <li>Item 3
            <ul>
                <li>Nested item 3.1</li>
                <li>Nested item 3.2</li>
            </ul>
        </li>
    </ul>

    <h2>Ordered List</h2>
    <ol>
        <li>First step</li>
        <li>Second step</li>
        <li>Third step
            <ol type="a">
                <li>Substep a</li>
                <li>Substep b</li>
            </ol>
        </li>
    </ol>

    <h2>Description List</h2>
    <dl>
        <dt>HTML</dt>
        <dd>HyperText Markup Language - the standard markup language for creating web pages.</dd>
        
        <dt>CSS</dt>
        <dd>Cascading Style Sheets - a style sheet language used for describing the presentation of a document written in HTML.</dd>
        
        <dt>JavaScript</dt>
        <dd>A programming language that enables interactive web pages and is an essential part of web applications.</dd>
    </dl>
</body>
</html>

```

The three main types of lists are:

1. **Unordered Lists** (`<ul>`): For lists where the order of items doesn't matter. Items are typically displayed with bullet points.

2. **Ordered Lists** (`<ol>`): For lists where the order matters. Items are displayed with numbers or letters by default. You can change the numbering style with the `type` attribute:
   - `type="1"`: Default, numbered (1, 2, 3)
   - `type="A"`: Uppercase letters (A, B, C)
   - `type="a"`: Lowercase letters (a, b, c)
   - `type="I"`: Uppercase Roman numerals (I, II, III)
   - `type="i"`: Lowercase Roman numerals (i, ii, iii)

3. **Description Lists** (`<dl>`): For name-value pairs. Each term (`<dt>`) can have one or more descriptions (`<dd>`).

Lists can be nested within each other for more complex structures.

### Links and Anchors

The `<a>` (anchor) element creates hyperlinks:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Links</title>
</head>
<body>
    <h1>HTML Links Examples</h1>
    
    <h2>External Links</h2>
    <p>
        <a href="https://www.example.com">Regular link to example.com</a>
    </p>
    <p>
        <a href="https://www.example.com" target="_blank" rel="noopener noreferrer">
            Link that opens in a new tab
        </a>
    </p>
    
    <h2>Internal Links (Page Navigation)</h2>
    <nav>
        <ul>
            <li><a href="#section1">Jump to Section 1</a></li>
            <li><a href="#section2">Jump to Section 2</a></li>
            <li><a href="#section3">Jump to Section 3</a></li>
        </ul>
    </nav>
    
    <section id="section1">
        <h2>Section 1</h2>
        <p>This is the content of section 1. The ID attribute makes this section a target for internal links.</p>
    </section>
    
    <section id="section2">
        <h2>Section 2</h2>
        <p>This is the content of section 2. You can navigate directly to this section using the anchor links above.</p>
    </section>
    
    <section id="section3">
        <h2>Section 3</h2>
        <p>This is the content of section 3.</p>
    </section>
    
    <h2>Other Link Types</h2>
    <p>
        <a href="mailto:example@example.com">Send an email</a>
    </p>
    <p>
        <a href="tel:+1234567890">Call +1 (234) 567-890</a>
    </p>
    <p>
        <a href="./documents/sample.pdf" download>Download PDF file</a>
    </p>
    
    <h2>Image as a Link</h2>
    <a href="https://www.example.com">
        <img src="example-button.jpg" alt="Visit Example.com">
    </a>
</body>
</html>

```

Key points about links:

- The `href` attribute specifies the destination of the link.
- External links point to other websites (use the full URL).
- Internal links can point to other pages on your site (relative path) or to specific elements within the same page (using the `#id` syntax).
- The `target="_blank"` attribute opens the link in a new tab or window.
- The `rel="noopener noreferrer"` attribute is a security measure for external links opened in new tabs.
- Special link types include:
  - `mailto:` for email links
  - `tel:` for telephone links
  - `download` attribute for downloadable resources

### Media Elements

HTML5 provides native support for various media types:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Media Elements</title>
</head>
<body>
    <h1>HTML Media Elements</h1>
    
    <h2>Images</h2>
    <!-- Basic image -->
    <img src="sample-image.jpg" alt="Description of the image">
    
    <!-- Image with width and height attributes -->
    <img src="sample-logo.png" alt="Company Logo" width="200" height="100">
    
    <!-- Responsive image (will scale with its container) -->
    <img src="responsive-image.jpg" alt="Responsive Image" style="max-width: 100%; height: auto;">
    
    <!-- Image with figure and caption -->
    <figure>
        <img src="landscape.jpg" alt="Mountain landscape">
        <figcaption>Beautiful mountain vista at sunset</figcaption>
    </figure>
    
    <h2>Audio</h2>
    <!-- Basic audio player with controls -->
    <audio controls>
        <source src="sample-audio.mp3" type="audio/mpeg">
        <source src="sample-audio.ogg" type="audio/ogg">
        Your browser does not support the audio element.
    </audio>
    
    <!-- Audio with additional attributes -->
    <audio controls autoplay muted loop>
        <source src="background-music.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    
    <h2>Video</h2>
    <!-- Basic video player with controls -->
    <video controls width="640" height="360">
        <source src="sample-video.mp4" type="video/mp4">
        <source src="sample-video.webm" type="video/webm">
        Your browser does not support the video element.
    </video>
    
    <!-- Video with poster image and additional attributes -->
    <video controls width="640" height="360" poster="video-thumbnail.jpg" preload="metadata">
        <source src="movie.mp4" type="video/mp4">
        <track src="subtitles_en.vtt" kind="subtitles" srclang="en" label="English">
        <track src="subtitles_es.vtt" kind="subtitles" srclang="es" label="Spanish">
        Your browser does not support the video element.
    </video>
</body>
</html>

```

#### Images (`<img>`)

Key attributes for images:
- `src`: Specifies the path to the image (required)
- `alt`: Provides alternative text for the image (required for accessibility)
- `width` and `height`: Specify the dimensions of the image
- `loading="lazy"`: Enables lazy loading for better performance (images load only when they come into view)

#### Audio (`<audio>`)

The `<audio>` element allows you to embed sound content:
- `controls`: Displays audio playback controls
- `autoplay`: Starts playing the audio automatically (use with caution)
- `loop`: Makes the audio repeat when finished
- `muted`: Mutes the audio initially
- `preload`: Suggests how the browser should load the audio (options: "auto", "metadata", "none")

Multiple `<source>` elements can provide different audio formats for browser compatibility.

#### Video (`<video>`)

The `<video>` element embeds video content:
- Similar attributes to audio: `controls`, `autoplay`, `loop`, `muted`, `preload`
- `width` and `height`: Set the dimensions
- `poster`: Specifies an image to display before the video plays
- `<track>`: Adds text tracks like subtitles and captions

### Special Characters and Entities

HTML uses special entities for characters that have special meaning in HTML syntax or for characters that are difficult to type directly:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Entities</title>
</head>
<body>
    <h1>HTML Special Characters and Entities</h1>
    
    <h2>Reserved Characters</h2>
    <ul>
        <li>Less than: &lt; (written as &amp;lt;)</li>
        <li>Greater than: &gt; (written as &amp;gt;)</li>
        <li>Ampersand: &amp; (written as &amp;amp;)</li>
        <li>Quotation mark: &quot; (written as &amp;quot;)</li>
        <li>Apostrophe: &apos; (written as &amp;apos;)</li>
    </ul>
    
    <h2>Commonly Used Symbols</h2>
    <ul>
        <li>Copyright: &copy; (written as &amp;copy;)</li>
        <li>Registered trademark: &reg; (written as &amp;reg;)</li>
        <li>Trademark: &trade; (written as &amp;trade;)</li>
        <li>Euro: &euro; (written as &amp;euro;)</li>
        <li>Pound: &pound; (written as &amp;pound;)</li>
        <li>Yen: &yen; (written as &amp;yen;)</li>
        <li>Multiplication: &times; (written as &amp;times;)</li>
        <li>Division: &divide; (written as &amp;divide;)</li>
    </ul>
    
    <h2>Space Characters</h2>
    <p>
        Non-breaking space: "word&nbsp;word" (written as &amp;nbsp;)<br>
        En space: "word&ensp;word" (written as &amp;ensp;)<br>
        Em space: "word&emsp;word" (written as &amp;emsp;)<br>
        Thin space: "word&thinsp;word" (written as &amp;thinsp;)
    </p>
    
    <h2>Arrows and Special Symbols</h2>
    <ul>
        <li>Left arrow: &larr; (written as &amp;larr;)</li>
        <li>Right arrow: &rarr; (written as &amp;rarr;)</li>
        <li>Up arrow: &uarr; (written as &amp;uarr;)</li>
        <li>Down arrow: &darr; (written as &amp;darr;)</li>
        <li>Double arrow: &harr; (written as &amp;harr;)</li>
        <li>Degree symbol: 98.6&deg;F (written as &amp;deg;)</li>
        <li>Bullet: &bull; (written as &amp;bull;)</li>
        <li>Ellipsis: &hellip; (written as &amp;hellip;)</li>
    </ul>
</body>
</html>

```

HTML entities serve several important purposes:

1. They allow you to display characters that are reserved in HTML syntax (like `<`, `>`, and `&`).
2. They provide a way to insert characters that aren't easily typed on a keyboard.
3. They ensure consistent rendering across different browsers and character encodings.

Entities can be written in two ways:
- Named entities: `&name;` (like `&lt;` for < or `&copy;` for ©)
- Numeric entities: `&#number;` (like `&#60;` for <)

A few common entities to remember:
- `&lt;` for 
- `&gt;` for >
- `&amp;` for &
- `&quot;` for "
- `&nbsp;` for a non-breaking space
- `&copy;` for ©
- `&reg;` for ®

## Key Takeaways from Part 1

1. **HTML Structure**: Every HTML document needs a proper structure with `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>` tags.

2. **Semantic HTML**: Using semantic elements like `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, and `<footer>` improves accessibility, SEO, and code readability.

3. **Text Formatting**: HTML provides various elements for text formatting, from headings and paragraphs to inline emphasis and technical text markers.

4. **Lists**: Use `<ul>` for unordered lists, `<ol>` for ordered lists, and `<dl>` for description lists.

5. **Links**: The `<a>` element creates hyperlinks to external sites, internal pages, specific sections, emails, phone numbers, and more.

6. **Media**: HTML5 includes native support for embedding images (`<img>`), audio (`<audio>`), and video (`<video>`).

7. **Entities**: HTML entities allow you to display special characters and symbols.

In Part 2, we'll explore forms, tables, and more advanced HTML features. Let's proceed!