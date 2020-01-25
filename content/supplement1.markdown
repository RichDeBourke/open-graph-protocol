## <a id='supplemental-protocol' href="#supplemental-protocol">Supplemental Protocol for Rich Link Previews</a>

Added January 2020 – Supplemental protocol for using OG metadata in rich link previews including guidelines for displaying/sizing Open Graph images.

### <a id="protocol-rich-link-previews" href="#protocol-rich-link-previews">Open Graph protocol for Rich Link Previews</a>

The Open Graph protocol enables any web page to become a rich object in a social graph. Open Graph metadata can also be used to create rich link previews. Rich link previews (see Figure 1 below) provide more information about a link than an HTML hyperlink (see Figure 2 below).

  Figure 1 – Rich Link Preview

  ![Mockup of what a rich link preview with the URL, an image, and descriptive text](content/OG-rich-link-preview-example.png "Rich Link Preview")

  Figure 2 – HTML link

  ![Example of a typical link with text and a pointing mouse cursor](content/OG-html-hyperlink.png "HTML link")

This supplement defines a standard for websites to configure Open Graph metadata, with two options for Open Graph images, *and* provides guidelines on how applications (e.g. message apps, email programs, and search engines) should utilize the metadata and size/crop Open Graph images in rich link previews and search results.

An Open Graph image in a social graph (such as *Facebook*) is typically sized to around 500 pixels wide on a personal computer and 360 to 375 pixels wide (the width of the screen) on a smartphone.

In a rich link preview, an Open Graph image is scaled to a width as small as 226 pixels when displayed as a landscape image, and cropped and scaled to a width as small as 72 pixels when displayed as a square image.

The scaling and cropping makes it difficult to design *one* image that works effectively in social graphs, message apps, emails, and search engine results. That is why this supplement adds an option to specify two images:


* Option 1 (the original process) – a website provides a *single* Open Graph image that is sized and cropped to work in all applications.

* Option 2 (the added process) – a website provides *two* Open Graph images, one landscape image for use with large display areas (226 pixels or more in width) and a smaller, square image for use with small display areas (120 pixels or less in width and/or height).

    *Note: Sizes for displayed images are described using pixels – referencing CSS pixels and not the device’s display pixels. Physical image sizes for JPEG/PNG files are described using px.*

    *Note: While websites provide landscape images in a range of aspect ratios (e.g. 1.77 to 1, 2 to 1), 1.91 to 1 is the size originally specified by* Facebook, *and for the sake of consistency and as there is no significant technical advantage to using a different aspect ratio, applications should display a landscape image at a 1.91 to 1 aspect ratio.*

<div class="aside" style="padding: 16px; background-color: #e8e8e8; border: 1px solid #c0c0c0; border-radius: 1em;">

    <h4 id="facebookSmallRichLinkPreview"><em>Facebook</em> Small Rich Link Preview</h4>
    <p>If the <em>first</em> OG image listed on a website has a square aspect ratio and is 500px or less in width and height, <em>Facebook</em> displays a <em>small</em> rich link preview (see Figure 3a), rather than a <em>large</em> link preview using a landscape image (see Figure 3b).</p>
    
    <figure style="margin-left: 2em">
        <figcaption>Figure 3a &ndash; Social Graph &ndash; Small, square image</figcaption>
        <img src="content/OG-example-social-graph-square.png" style="margin-top: 0.5rem; width: 395px; border: 1px solid black">
    </figure>
    <figure style="margin-left: 2em">
        <figcaption>Figure 3b &ndash; Social Graph &ndash; Large, landscape image</figcaption>
        <img src="content/OG-example-social-graph-landscape.png" style="margin-top: 0.5rem; width: 395px; border: 1px solid black">
    </figure>
    <p>The advantage of the small rich link preview for a website is <em>Facebook</em> will display more text with the small preview.</p>

    <h5>Small image rich link preview</h5>
    <ul>
        <li>Maximum text display: 5 lines</li>
        <li>Lines for the <code>og:title</code> text will display up to 42 characters per line. 5 lines of title text (no description text) will display 200 to 215 characters.</li>
        <li>Lines for the <code>og:description</code> will display up to 52 characters per line. If there 4 lines of description text (and only 1 line of title text) 190 to 200 characters from the description will be displayed for a total of approximately 230 characters.</li>
    </ul>

    <h5>Large image rich link preview</h5>
    <ul>
        <li>Maximum text display: 2 lines</li>
        <li>If the <code>og:title</code> text &gt; 65 characters, the title text will wrap to the second line and no <code>og:description</code> text will be displayed. Up to 128 characters will be displayed across the two lines.</li>
        <li>If the <code>og:title</code> text is &lt; 65 characters, the title text will be displayed on one line and one line of the <code>og:description</code> text will be displayed. Up to 77 characters from the <code>og:description</code> will be displayed, for a total of approximately 140 characters.</li>
    </ul>

    <p>If more text on <em>Facebook</em> is of higher value compared to a cropped image in message apps, then a website can design their Open Graph strategy around using a small OG image.</p>
    <p style="margin: 0 4em 1em 2em;"><em>Note: Character counts are estimates. The actual number of characters will vary based on the width of the characters in the text and the font style that is used.</em></p>
</div>

### <a id="applying-protocol-to-webpages" href="#applying-protocol-to-webpages">Applying the Supplemental protocol to Webpages</a>

#### Metadata tags

The OG metadata on a webpage is used to create rich objects in social graphs and rich link previews in message apps, email programs, and search engines.

  *Note: If a webpage does not provide OG metadata tags, applications will utilize other information on the page to create a preview.*

#### Metadata for rich link previews

    <meta property="og:site_name" content="Open Graph">
    <meta property="og:title" content="Open Graph protocol">
    <meta property="og:description" content="The Open Graph protocol enables
        any web page to become a rich object in a social graph.">`
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://ogp.me/">
    <meta property="og:image" content="https://ogp.me/OG-logo-lg.png">
    <meta property="og:image:type" content="image/png">
    <meta property="og:image:width" content="1200">
    <meta property="og:image:height" content="630">
    <meta property="og:image:alt" content="The Open Graph logo – a global
        network symbol with connection points on the left and right.">
    ⋮
    <meta property="og:image" content="https://ogp.me/OG-logo-sm.png">
    <meta property="og:image:type" content="image/png">
    <meta property="og:image:width" content="240">
    <meta property="og:image:height" content="240">
    <meta property="og:image:alt" content="The Open Graph logo – a global
        network symbol with connection points on the left and right.">

<table style="width: 80%; margin-left: 1em; margin-bottom: 1em;">
    <col style="width:30%">
    <col style="width:70%">
    <thead>
        <tr>
            <th>
                Tag
            </th>
            <th>
                Description
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <code>og:site_name</code>
            </td>
            <td>
                Site name &ndash; same for every page on the site.<br>
                Suggested <em>maximum</em> number of characters is 35.<br>
                See the <a href="#optional">Optional Metadata</a> section for more information.
            </td>
        </tr>
        <tr>
            <td>
                <code>og:title</code>
            </td>
            <td>
                Page title &ndash; briefly describe the page content &ndash; avoid branding and the domain name.<br>
                Suggested <em>maximum</em> number of characters is 40.<sup>1</sup><br>
                See the <a href="#metadata">Basic Metadata</a> section for more information.
            </td>
        </tr>
        <tr>
            <td>
                <code>og:description</code>
            </td>
            <td>
                Description of the page content &ndash; information about the page content (some branding can be included).<br>
                Suggested <em>maximum</em> number of characters is 130.<sup>1</sup><br>
                See the <a href="#optional">Optional Metadata</a> section for more information.
            </td>
        </tr>
        <tr>
            <td>
                <code>og:type</code>
            </td>
            <td>
                Type of object such as website, article, video, or music.<br>
                See the <a href="#types">Object Types</a> section for more information.
            </td>
        </tr>
        <tr>
            <td>
                <code>og:url</code>
            </td>
            <td>
                Canonical URL of the page.<br>
                See the <a href="#metadata">Basic Metadata</a> section for more information.
            </td>
        </tr>
        <tr>
            <td colspan="2">
                <p style="text-align: center; padding-top: 1em;"><em>og:image data &ndash; repeat for each OG image that is being provided:</em>
            </td>
        </tr>
        <tr>
            <td>
                <code>og:image</code>
            </td>
            <td>
                Full URL for the image file.<sup>2</sup><br>
                See the <a href="#metadata">Basic Metadata</a> section for more information.
            </td>
        </tr>
        <tr>
            <td>
                <code>og:image:type</code>
            </td>
            <td>
                Image type (image/jpeg or image/png).<br>
                See the <a href="#structured">Structured Properties</a> section for more information.
            </td>
        </tr>
        <tr>
            <td>
                <code>og:image:width</code>
            </td>
            <td>
                Image width in px.<br>
                See the <a href="#structured">Structured Properties</a> section for more information.
            </td>
        </tr>
        <tr>
            <td>
                <code>og:image:height</code>
            </td>
            <td>
                Image height in px.<br>
                See the <a href="#structured">Structured Properties</a> section for more information.
            </td>
        </tr>
        <tr>
            <td>
                <code>og:image:alt</code>
            </td>
            <td>
                Description of the image (not a caption) for use by accessibility technologies.<br>
                Suggested max length is 100 characters.<br>
                See the <a href="#structured">Structured Properties</a> section for more information.
            </td>
        </tr>
    </tbody>
</table>

<!-- From WebAIM - Alternative text should be succinct, yet descriptive of the content and function of an image. Lengthy alternative text (more than around 100 characters) often indicates that extraneous content or content that is not available to sighted users is being presented.-->
<p style="margin: 0 4em 1em 2em;"><em>Note:<sup>1</sup> The title and description share the same general text area. Applications may limit the </em>total<em> amount of text, but should give priority to displaying the title at the expense of the description. Applications may truncate the title and description using an ellipsis.</em></p>

<p style="margin: 0 4em 1em 2em;"><em>Note:<sup>2</sup> While the Open Graph protocol defines an </em><code>og:image:secure_url</code><em> property, the property is not needed. If a site uses SSL, the </em><code>og:image</code><em> URL should use </em><code>https</code><em> protocol.</em></p>

#### Hyphenation of metadata text

Titles and descriptions should include soft hyphens (&amp;shy;) in words that could potentially break across lines.

#### Image Format/Size

Images formats are limited to JPEG and PNG. File size should be no larger than 300KB. *While some applications support other file types and larger file sizes, JPEG/PNG files up to 300KB are currently acceptable to all applications. Web designers should verify the size of their OG image files before publishing.*

#### Image Option 1 &ndash; Single image

<p>Webpage specifies a <em>single</em> Open Graph image for use as a landscape image <em>and</em> as a square image. The image is cropped as needed.</p>
<p>Websites can provide an image in any orientation (landscape, square, or portrait.<sup>3</sup>). The image will be scaled and cropped as needed by each application.</p>
<p style="margin: 0 4em 1em 2em;"><em>Note:<sup>3</sup> A portrait oriented image will be cropped in all applications before being used.</em></p>

##### Image Option 1 &ndash; Landscape Image with template

<p>The website supplies one image that has a landscape aspect ratio. Recommended image size is 1200px by 630px with primary content in the gray area as shown in Figure 4.</p>
<figure style="margin-left: 2em">
    <figcaption>Figure 4 &ndash; Option 1 Landscape</figcaption>
    <img src="content/OG-template-single-image-landscape-full.png" style="margin-top: 0.5rem; width: 226px; border: 1px solid black" title="Landscape Open Graph template displayed at 226 pixels wide">
    <img src="content/OG-template-single-image-landscape-cropped.png" style="margin-top: 0.5rem; width: 72px; border: 1px solid black; margin-left: 1rem" title="Landscape Open Graph template cropped to a square and displayed at 72 pixels wide">
</figure>
<p>The content should be visually effective when the image is scaled to between 500 pixels down to 226 pixels wide <em>and</em> when cropped to a square and scaled to between 120 pixels down to 72 pixels wide.</p>
<p><a href="content/OG-template-single-image-landscape.png" download>Downloadable landscape template file</a></p>

##### Image Option 1 &ndash; Square Image with template

<p>The website supplies one image that has a square aspect ratio. Recommended image size is 900px by 900px with primary content in the gray area as shown in Figure 5.</p>
<figure style="margin-left: 2em">
    <figcaption>Figure 5 &ndash; Option 1 Square</figcaption>
    <img src="content/OG-template-single-image-square-full.png" style="margin-top: 0.5rem; width: 226px; border: 1px solid black" title="Square Open Graph template displayed at 226 pixels wide">
    <img src="content/OG-template-single-image-square-cropped.png" style="margin-top: 0.5rem; width: 226px; border: 1px solid black; margin-left: 1rem" title="Square Open Graph template cropped to a square and displayed at 226 pixels wide">
    <img src="content/OG-template-single-image-square-full.png" style="margin-top: 0.5rem; width: 72px; border: 1px solid black; margin-left: 1rem" title="Square Open Graph template displayed at 72 pixels wide">
</figure>
<p>The image content should be visually effective when cropped to a rectangle and scaled to between 500 pixels down to 226 pixels <em>as well as</em> when scaled to between 120 pixels down to 72 pixels.</p>
<p><a href="content/OG-template-single-image-square.png" download>Downloadable square template file</a></p>

##### Image Option 1 &ndash; Portrait Image

<p>The website supplies one image that has a portrait aspect ratio. Suggested image width is 630px with primary content in the gray area as shown in Figure 6.</p>
<figure style="margin-left: 2em">
    <figcaption>Figure 6 &ndash; Option 1 Portrait</figcaption>
    <img src="content/OG-template-single-image-portrait.png" style="margin-top: 0.5rem; width: 226px; border: 1px solid black" title="Portrait Open Graph sample image displayed at 226 pixels wide">
    <img src="content/OG-template-single-image-portrait-cropped-rectangle.png" style="margin-top: 0.5rem; width: 226px; border: 1px solid black; margin-left: 1rem" title="Portrait Open Graph sample image cropped to a rectangle and displayed at 226 pixels wide">
    <img src="content/OG-template-single-image-portrait-cropped-square.png" style="margin-top: 0.5rem; width: 72px; border: 1px solid black; margin-left: 1rem" title="Portrait Open Graph sample image cropped to a square and displayed at 72 pixels wide">
</figure>
<p>The content should be visually effective when the image is cropped to a horizontal rectangle and scaled to between 500 pixels down to 226 pixels wide <em>and</em> when cropped to a square and scaled to between 120 pixels down to 72 pixels wide.</p>

<h4>Image Option 2 &ndash; Two images</h4>
<p>Webpage specifies two (or more) Open Graph images.</p>
<p>The first image should be a landscape 1.91:1 aspect ratio image and the last image should be a square 1:1 aspect ratio image (more than two images can be listed &ndash; the <em>last</em> listed image is the image that will be used for small, square displays). If there is only one OG image listed, then the last image <em>is</em> the first image.</p>
<p style="margin: 0 4em 1em 2em;"><em>Note: The order of the images (first &amp; last) is important. Websites should not depend on applications selecting an image based on the image size.</em></p>

##### Image Option 2 &ndash; Landscape Image with template

<p>The website supplies two images, the first that has a landscape aspect ratio. Recommended image size is 1200px by 630px with primary content in the gray area as shown in Figure 7.</p>
<figure style="margin-left: 2em">
    <figcaption>Figure 7 &ndash; Option 2 Landscape</figcaption>
    <img src="content/OG-template-two-image-landscape-full.png" style="margin-top: 0.5rem; width: 226px; border: 1px solid black" title="Landscape Open Graph template displayed at 226 pixels wide">
</figure>
<p>The content should be visually effective when the image is scaled to 500 pixels down to 226 pixels wide.</p>
<p><a href="content/OG-template-two-image-landscape.png" download>Downloadable landscape template file</a></p>

##### Image Option 2 &ndash; Square Image with template

<p>The website supplies two images, the second that has a square aspect ratio. Recommended image size is 240px by 240px with primary content in the gray area as shown in Figure 8.</p>
<figure style="margin-left: 2em">
    <figcaption>Figure 8 &ndash; Option 2 Square</figcaption>
    <img src="content/OG-template-two-image-square-full.png" style="margin-top: 0.5rem; width: 72px; border: 1px solid black" title="Square Open Graph template displayed at 72 pixels wide">
</figure>
<p>The content should be visually effective when the image is scaled to 120 pixels down to 72 pixels.</p>
<p><a href="content/OG-template-two-image-square.png" download>Downloadable square template file</a></p>

