### Applying the Supplemental protocol to Rich Link Previews

<p style="margin-top: 1em; font-size: 18pt; font-weight: bold; text-align: center;"><strong>For applications and search engines</strong></p>
<p>Rich link previews are important for driving traffic to a website. For a rich link preview to be effective, the website <em>and</em> the application (e.g. social graph, message app, email program, or search engine) need to ensure that the Open Graph metadata, especially images, is shown in a predictable way.</p>

#### Rich link previews on social graphs and email applications

<p>When a link is shared through a social graph such as <em>Facebook</em> or <em>LinkedIn</em> or in an email message such as <em>Yahoo Mail</em>, the application should display a rectangular image between 400 to 550 pixels wide, similar to Figure 9a for PCs and tablets and between 340 pixels to the screen width, similar to Figure 9b for smartphones.</p>

<figure style="margin-left: 2em">
    <figcaption>Figure 9a &ndash; OG Example &ndash; Social Graph using Landscape Image &ndash; PC displays</figcaption>
    <div id="link-display1" class="preview example-share example-share-pc" title="Example of sharing a link through a social graph on a PC at 500 pixels wide">
        <div class="link-text">
            <span style="position: absolute; top: 10px; left: 5px;">&#9312;</span>
            <img src="content/OG-logo-lg.png" alt="OG Logo">
            <p class="example-title-text"><span style="position: absolute; top: -16px; left: -11px;">&#9313;</span>Lorem ipsum dolor sit a&shy;met, consecteture adipiscing elit, sed</p>
            <p class="example-description-text"><span style="position: absolute; top: -16px; left: -11px;">&#9314;</span>Sed ut perspiciatis unde omnis iste natus error sit voluptatem acc&shy;u&shy;san&shy;tium doloremque lau&shy;dantium, totam rem aperiam, eaque ipsa quae ab&hellip;</p>
            <p class="example-site-name-text"><span style="position: absolute; top: -16px; left: -11px;">&#9315;</span>example.com</p>
        </div>
    </div>
    <div class="preview" style="position: relative; float: left; margin-top: 1.0625rem; margin-bottom: 1rem;">
        <ul>
            <li style="padding-bottom: 14rem;">Landscape og:image</li>
            <li style="padding-bottom: 0.125rem;">Title</li>
            <li style="padding-bottom: 1.625rem;">Description</li>
            <li>Domain name</li>
        </ul>
    </div>
</figure>

<figure style="margin-left: 2em; clear: both;">
    <figcaption>Figure 9b &ndash; OG Example &ndash; Social Graph using Landscape Image &ndash; mobile displays</figcaption>
    <div id="link-display2" class="preview example-share example-share-mobile" title="Example of sharing a link through a social graph on a smartphone at 360 pixels wide">
        <div class="link-text">
            <span style="position: absolute; top: 10px; left: 5px;">&#9312;</span>
            <img src="content/OG-logo-lg.png" alt="OG Logo" width="358">
            <p class="example-title-text"><span style="position: absolute; top: -16px; left: -11px;">&#9313;</span>Lorem ipsum dolor sit a&shy;met, consectetur adipiscing elit, sed do eiusmod tempor</p>
            <p class="example-description-text"><span style="position: absolute; top: -16px; left: -11px;">&#9314;</span>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque lau&shy;dantium, totam rem aperiam, eaque ipsa quae ab illo&hellip;</p>
            <p class="example-site-name-text"><span style="position: absolute; top: -16px; left: -11px;">&#9315;</span>example.com</p>
        </div>
    </div>
    <div class="preview" style="position: relative; float: left; margin-top: 1.0625rem; margin-bottom: 1rem;">
        <ul>
            <li style="padding-bottom: 9.4375rem;">Landscape og:image</li>
            <li style="padding-bottom: 1.625rem;">Title</li>
            <li style="padding-bottom: 2.9375rem;">Description</li>
            <li>Domain name</li>
        </ul>
    </div>
</figure>

<p style="margin: 0 4em 1em 2em; clear: both;"><em>Note: If the first og:image is square and less than 500px in width, </em>Facebook<em> will display a small rich link preview with up to five rows of title and description text as described <a href="#facebookSmallRichLinkPreview">above</a>. Most, if not all other applications that utilize Open Graph metadata do not have a different display based on the first og:image size.</em></p>

<h4>Rich link previews on message apps</h4>
<p>When a link is shared through a messaging app such as <em>WhatsApp</em> or <em>Messenger</em>, the application can display a rectangular image similar to Figure 10a or square image similar to Figure 10b. As messaging apps use a conversation style layout, the rich link preview width is expected to be less than the width of a smartphone display, in the range of 226 to 268 pixels wide.</p>
<figure style="margin-left: 2em;">
    <figcaption>Figure 10a &ndash; OG Example &ndash; Messaging Apps using Landscape Image</figcaption>
    <div id="link-display3" class="preview example-msg" title="Message example with Landscape Open Graph image displayed at 226 pixels wide">
        <div class="link-area">
            <p class="example-link-text"><span style="position: absolute; top: -2px; left: 5px;">&#9312;</span>https://www.example.com/lorem-ipsum</p>
        </div>
        <div class="link-text">
            <span style="position: absolute; top: -2px; left: 5px;">&#9313;</span>
            <img class="landscape" src="content/OG-logo-lg.png" alt="OG Logo" width="226">
            <p class="example-title-text"><span style="position: absolute; top: -16px; left: -11px;">&#9314;</span>Lorem ipsum dolor sit a&shy;met, consecteture</p>
            <p class="example-description-text"><span style="position: absolute; top: -16px; left: -11px;">&#9315;</span>Sed ut perspiciatis unde om&shy;nis iste natus error sit vol&shy;up&shy;tat&shy;em accusantium dol&shy;or&shy;em&shy;que lau&shy;dantium, totam rem ap&shy;eriam, eaque ipsa quae&hellip;</p>
            <p class="example-site-name-text"><span style="position: absolute; top: -16px; left: -11px;">&#9316;</span>example.com</p>
        </div>
    </div>
    <div class="preview" style="position: relative; float: left; margin-top: 1.0625rem; margin-bottom: 1rem;">
        <ul>
            <li style="padding-bottom: 2.125rem;">URL for the page</li>
            <li style="padding-bottom: 5.8125rem;">Landscape og:image</li>
            <li style="padding-bottom: 1.625rem;">Title</li>
            <li style="padding-bottom: 5.5625rem;">Description</li>
            <li>Domain name</li>
        </ul>
    </div>
</figure>

<figure style="margin-left: 2em; clear: both;">
    <figcaption>Figure 10b &ndash; OG Example &ndash; Messaging Apps using Square Image</figcaption>
    <div id="link-display4" class="preview example-msg">
        <div class="link-area">
            <p class="example-link-text"><span style="position: absolute; top: -2px; left: 5px;">&#9312;</span>https://www.example.com/lorem-ipsum</p>
        </div>
        <div class="link-text" style="background-color: #F7F7F7; padding: 0.5rem 1rem 1rem 1rem;">
            <span style="position: absolute; top: -10px; left: 5px;">&#9313;</span>
            <img class="square" src="content/OG-logo-sm.png" alt="OG Logo">
            <p class="example-title-text"><span style="position: absolute; top: -15px; left: 82px;">&#9314;</span>Ad&shy;ipisc&shy;ing el&shy;it, sed do eius&shy;mod tem&shy;por </p>
            <p class="example-description-text"><span style="position: absolute; top: -16px; left: -11px;">&#9315;</span>Sed ut perspiciatis unde om&shy;nis iste natus error sit vol&shy;up&shy;tat&shy;em accusantium dol&shy;or&shy;em&shy;que lau&shy;dantium, totam rem ap&shy;eriam, eaque ipsa quae&hellip;</p>
            <p class="example-site-name-text"><span style="position: absolute; top: -16px; left: -11px;">&#9316;</span>example.com</p>
        </div>
    </div>
    <div class="preview" style="position: relative; float: left; margin-top: 1.0625rem; margin-bottom: 1rem;">
        <ul>
            <li style="padding-bottom: 2.5rem;">URL for the page</li>
            <li style="padding-bottom: 0rem;">Square og:image</li>
            <li style="padding-bottom: 2.875rem;">Title</li>
            <li style="padding-bottom: 5.5625rem;">Description</li>
            <li>Domain name</li>
        </ul>
    </div>
</figure>

<h4 style="clear: both;">Title/Description Text Area</h4>
<p>The title and description texts should share the same area. Applications can limit the total amount of text that is displayed, with priority being given to displaying the title text (assumption is the title has a higher value than the description in conveying the content of the website) as shown in Figure 11. Text should be truncated with an ellipsis.</p>
<p>Applications should display rich link previews with a combined minimum of 150 characters.</p>

<figure style="margin-left: 2em;">
<figcaption>Figure 11 &ndash; Examples of title and description text</figcaption>
<div class="preview example-title-desc" title="Sample short title with description text displayed at 226 pixels wide">
<div class="title-desc-text">
  <p class="example-title-text">Incididunt ut labore et</p>
  <p class="example-description-text">Sed ut perspiciatis unde om&shy;nis iste natus error sit vol&shy;up&shy;tat&shy;em accusantium dol&shy;or&shy;em&shy;que lau&shy;dantium, totam rem ap&shy;eriam, eaque ipsa quae ab illo inventore veritatis et&hellip;</p>
  <p class="example-site-name-text">example.com</p>
</div>
</div>
<div class="preview example-title-desc" title="Sample medium title with description text displayed at 226 pixels wide">
<div class="title-desc-text">
  <p class="example-title-text">Dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut</p>
  <p class="example-description-text">Sed ut perspiciatis unde om&shy;nis iste natus error sit vol&shy;up&shy;tat&shy;em accusantium&hellip;</p>
  <p class="example-site-name-text">example.com</p>
</div>
</div>
<div class="preview example-title-desc" title="Sample long title with no description text displayed at 226 pixels wide">
<div class="title-desc-text">
  <p class="example-title-text">Voluptate velit esse cil&shy;lum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mol&shy;lit anim id est laborum&hellip;</p>
  <p class="example-site-name-text">example.com</p>
</div>
</div>
</figure>

<h4 style="clear: both;">Rich link previews on search results</h4>
<p>If a search engine includes an image as part of the search results, a square aspect ratio Open Graph image should be displayed, as shown in Figure 12. The search engine should use the <em>last</em> Open Graph image, cropped to a square, if necessary. Minimum size for the image is 72 pixels. The other content in the search results is based on the search engine&rsquo;s normal practices.</p>
<figure style="margin-left: 2em">
    <figcaption>Figure 12 &ndash; OG Example &ndash; Search Results</figcaption>
    <img src="content/OG-example-search-results.png" alt="Example of mobile search results" style="margin-top: 0.5rem; width: 360px; border: 1px solid black">
</figure>

<h4 id="usingogmetadata">Using the OG Metadata</h4>
<table style="width: 80%; margin-left: 1em; margin-bottom: 1em;">
<col style="width:30%">
<col style="width:35%">
<col style="width:35%">
<thead>
<tr>
<th>
    Tag
</th>
<th>
    Description
</th>
<th>
    Alt Tag Source
</th>
</tr>
</thead>
<tbody>
<tr>
<td>
    <code>og:title</code>
</td>
<td>
    Page title
</td>
<td>
    Page title tag<br>
    Twitter title tag<br>
</td>
</tr>
<tr>
<td>
    <code>og:description</code>
</td>
<td>
    Page description
</td>
<td>
    Page description tag<br>
    Twitter description tag
</td>
</tr>
<tr>
<tr>
<td>
    <code>og:locale</code>
</td>
<td>
    Locale for the tags
</td>
<td>
    HTML tag&rsquo;s lang attribute
</td>
</tr>
<tr>
<td colspan="3">
    <p style="text-align: center; padding-top: 1em;"><em>og:image data &ndash; repeated for each OG image that is provided:</em>
</td>
</tr>
<tr>
<td>
    <code>og:image</code>
</td>
<td>
    Page image
</td>
<td>
    og:image:secure_url<br>
    Twitter image
</td>
</tr>
<tr>
<td>
    <code>og:image:alt</code>
</td>
<td>
    For users who are using assistive technology.
</td>
<td>
    &nbsp;
</td>
</tr>
<tr>
<td colspan="3">
    <p style="text-align: center; padding-top: 1em;"><em>The fields below are not needed for creating previews:</em>
</td>
</tr>
<tr>
<td>
    <code>og:site_name</code>
</td>
<td>
    Site name
</td>
<td>
    Domain name
</td>
</tr>
<tr>
<td>
    <code>og:type</code>
</td>
<td colspan="2">
    Type of Open Graph object, such as website, article, video.movie, or music.song.
</td>
</tr>
<tr>
<td>
    <code>og:url</code>
</td>
<td colspan="2">
    Canonical URL &ndash; while websites are asked to provide the canonical URL for the webpage being shared, applications should utilize the URL provided with the rich link preview request, rather than the canonical URL.<sup>4</sup>
</td>
</tr>
<tr>
<td>
    <code>og:locale:alternate</code>
</td>
<td colspan="2">
    While a webpage may have alternate language versions available, rich link previews should be generated using the language version of the original link.
</td>
</tr>
<tr>
<td>
    <code>og:image:type</code>
</td>
<td colspan="2" rowspan="3">
    Applications should determine the image type and size (width &amp; height) independently of what the metadata specifies.
</td>
</tr>
<tr>
<td>
    <code>og:image:width</code>
</td>
</tr>
<tr>
<td>
    <code>og:image:height</code>
</td>
</tr>
</tbody>
</table>
<p style="margin-left: 2rem;"><em>Note:<sup>4</sup> This supplement does not provide any recommendations for protecting against malicious links. That is left to the discretion of the applications.</em></p>
<p style="margin-left: 2rem;"><em>Note: If the page does not provide title, description, and/or image information, including any of the alternate sources, the associated section should not be included in the rich link preview.</em></p>

<h4>Hyphenation of metadata text</h4>
<p>Applications should support the use of soft hyphens (&amp;shy;) for the title and description to enable text to break across lines.</p>

<h4>Selecting the Open Graph image</h4>
<p>If the display area for the image is 226 pixels or wider, the application should use the first listed OG image in a landscape aspect ratio. If the display area is less than 226 pixels wide or 120 pixels or less in height, than the application should use the last listed OG image in a square aspect ratio. If there is only one OG image listed, then the last image <em>is</em> the first image.</p>

<h4>Sizing/Cropping the Image</h4>
<p>Applications should crop all images to insure the image will cover the required area in the correct aspect ratio.</p>

<h5>Cropping for a Landscape format</h5>
<p>If the OG image supplied by the website has a width to height ratio of less than 1.91 to 1, then, per Figure 13:</p>
<ol>
    <li>Scale the image to the desired width</li>
    <li>Crop the image to a height to match the 1.91:1 ratio, rounding to 1 pixel</li>
    <li>The image should be cropped equally from the top and bottom (&plusmn; 1 pixel) if cropping is required</li>
</ol>
<figure style="margin-left: 2em">
    <figcaption>Figure 13 &ndash; Landscape scaling / cropping from a taller image</figcaption>
    <img src="content/OG-landscape-image-cropping-from-taller.png" style="margin-top: 0.5rem">
</figure>
<p>If the image supplied by the website has a width to height ratio greater than 1.91 to 1, then, per Figure 14:</p>
<ol>
    <li>Scale the image to the desired height</li>
    <li>Crop the image to a width to match the 1.91:1 ratio</li>
    <li>The image should be cropped equally from the left and right (&plusmn; 1 pixel)</li>
</ol>
<figure style="margin-left: 2em">
    <figcaption>Figure 14 &ndash; Landscape scaling / cropping from a wider image</figcaption>
    <img src="content/OG-landscape-image-cropping-from-wider.png" style="margin-top: 0.5rem">
</figure>

<h5>Cropping for a Square format</h5>
<p>If the OG image supplied by the website has a width to height ratio of less than 1 to 1, then, per Figure 15:</p>
<ol>
    <li>Scale the image to the desired width</li>
    <li>Crop the image to a height to match the 1:1 ratio, rounding to 1 pixel</li>
    <li>The image should be cropped equally from the top and bottom (&plusmn; 1 pixel) if cropping is required</li>
</ol>
<figure style="margin-left: 2em">
    <figcaption>Figure 15 &ndash; Square scaling / cropping from a taller image</figcaption>
    <img src="content/OG-square-image-cropping-from-taller.png" style="margin-top: 0.5rem">
</figure>
<p>If the image supplied by the website has a width to height ratio greater than 1 to 1, then, per Figure 16:</p>
<ol>
    <li>Scale the image to the desired height</li>
    <li>Crop the image to a width to match the 1:1 ratio</li>
    <li>The image should be cropped equally from the left and right (&plusmn; 1 pixel)</li>
</ol>
<figure style="margin-left: 2em">
    <figcaption>Figure 16 &ndash; Square scaling / cropping from a wider image</figcaption>
    <img src="content/OG-square-image-cropping-from-wider.png" style="margin-top: 0.5rem">
</figure>

<h3>Developer Support</h3>
<p>Applications (e.g. social graphs, message apps, email programs, and search engines) should provide technical information that describes how OG metadata is processed for rich link previews, with examples. This information should be easy to find using a search engine<sup>5</sup> and not require registration to access. This will help website owners get the most benefit when users share a link.</p>
<p>The technical information should include:</p>
<ul>
    <li>If an image is displayed and if so, using what aspect ratio (1.91 to 1 or 1 to 1)</li>
    <li>Image formats that are supported</li>
    <li>Maximum image size that is supported</li>
    <li>How much tag information is displayed (what are the character / row limits)</li>
    <li>How developers can test rich link previews<sup>6</sup></li>
    <li>Whether data is cached or not, and if the data is cached:
        <ul>
            <li>How long is the data cached for</li>
            <li>How can the cache be cleared (trigger a rescrape)<sup>7</sup></li>
        </ul>
    </li>
</ul>

<p style="margin: 0 4em 1em 2em;"><em>Note:<sup>5</sup> A Google search for </em><span style="font-family: monospace; font-size: 12pt; color: #060;"><em>site:developer.</em>message-app<em>.com "rich link preview"</em></span><em> should list the page with the information.</em></p>
<p style="margin: 0 4em 1em 2em;"><em>Note:<sup>6</sup> A test method should be web based and not require registration in order to use.</em></p>
<p style="margin: 0 4em 1em 2em;"><em>Note:<sup>7</sup> Applications can require registration as a user or developer to be able to trigger a rescrape.</em></p>

<h3>Accessibility</h3>
<p>Applications (e.g. social graphs, message apps, email programs, and search engines) should support accessibility including:</p>
<ul>
    <li>Same amount of text should be displayed if the user has selected a larger default font size</li>
    <li>Images should remain the standard size (larger font sizes should not shrink the image area)</li>
</ul>
---