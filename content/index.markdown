## <a id="intro" href="#intro">Introduction</a>

The [Open Graph protocol](https://ogp.me/) enables any web page to become a
rich object in a social graph. For instance, this is used on Facebook to allow
any web page to have the same functionality as any other object on Facebook.

While many different technologies and schemas exist and could be combined
together, there isn't a single technology that provides enough information to
richly represent any web page within the social graph. The Open Graph protocol
builds on these existing technologies and gives developers one thing to
implement. Developer simplicity is a key goal of the Open Graph protocol, which
has informed many of
[the technical design decisions](
https://www.scribd.com/doc/30715288/The-Open-Graph-Protocol-Design-Decisions).


---
## <a id="metadata" href="#metadata">Basic Metadata</a>

To turn your web pages into graph objects, you need to add basic metadata to
your page. We've based the initial version of the protocol on
[RDFa](https://en.wikipedia.org/wiki/RDFa) which means that you'll place
additional `<meta>` tags in the `<head>` of your web page. The four required
properties for every page are:

 * `og:title` &ndash; The title of your object as it should appear within the graph,
   e.g., "The Rock".
 * `og:type` &ndash; The [type](#types) of your object, e.g., "video.movie".  Depending on
   the type you specify, other properties may also be required.
 * `og:image` &ndash; An image URL, which should represent your object within the
   graph.
 * `og:url` &ndash; The canonical URL of your object that will be used as its
   permanent ID in the graph, e.g., "https://www.imdb.com/title/tt0117500/".

As an example, the following is the Open Graph protocol markup for [The Rock on
IMDB](https://www.imdb.com/title/tt0117500/):

    <html prefix="og: http://ogp.me/ns#">
    <head>
    <title>The Rock (1996)</title>
    <meta property="og:title" content="The Rock">
    <meta property="og:type" content="video.movie">
    <meta property="og:url" content="https://www.imdb.com/title/tt0117500/">
    <meta property="og:image" content="https://ia.media-imdb.com/images/rock.jpg">
    ...
    </head>
    ...
    </html>


### <a id="optional" href="#optional">Optional Metadata</a>

The following properties are optional for any object and are generally
recommended:

 * `og:audio` &ndash; A URL to an audio file to accompany this object.
 * `og:description` &ndash; A one to two sentence description of your object.
 * `og:determiner` &ndash; The word that appears before this object's title
   in a sentence. An [enum](#enum) of (a, an, the, "", auto). If `auto` is 
   chosen, the consumer of your data should choose between "a" or "an".
   Default is "" (blank).
 * `og:locale` &ndash; The locale these tags are marked up in.
   Of the format `language_TERRITORY`. Default is `en_US`.
 * `og:locale:alternate` &ndash; An [array](#array) of other locales this page is 
   available in.
 * `og:site_name` &ndash; If your object is part of a larger web site, the name
   that should be displayed for the overall site. e.g., "IMDb".
 * `og:video` &ndash; A URL to a video file that complements this object.

For example (line-break solely for display purposes):

    <meta property="og:audio" content="https://example.com/bond/theme.mp3">
    <meta property="og:description" 
      content="Sean Connery found fame and fortune as the
               suave, sophisticated British agent, James Bond.">
    <meta property="og:determiner" content="the">
    <meta property="og:locale" content="en_GB">
    <meta property="og:locale:alternate" content="fr_FR">
    <meta property="og:locale:alternate" content="es_ES">
    <meta property="og:site_name" content="IMDb">
    <meta property="og:video" content="https://example.com/bond/trailer.swf">

The RDF schema (in [Turtle](https://en.wikipedia.org/wiki/Turtle_(syntax))) 
can be found at [ogp.me/ns](http://ogp.me/ns/ogp.me.ttl).

---
## <a id="structured" href="#structured">Structured Properties</a>

Some properties can have extra metadata attached to them.
These are specified in the same way as other metadata with `property` and
`content`, but the `property` will have extra `:`.

The `og:image` property has some optional structured properties:

 * `og:image:url` &ndash; Identical to `og:image`.
 * `og:image:secure_url` &ndash; An alternate URL to use if the webpage requires
    HTTPS.
 * `og:image:type` &ndash; A [MIME type](
    https://en.wikipedia.org/wiki/Internet_media_type) for this image.
 * `og:image:width` &ndash; The number of pixels wide.
 * `og:image:height` &ndash; The number of pixels high.
 * `og:image:alt` &ndash; A description of what is in the image (not a caption). If the page specifies an og:image it should specify `og:image:alt`.

A full image example:

    <meta property="og:image" content="https://example.com/ogp.jpg">
    <meta property="og:image:secure_url" content="https://secure.example.com/ogp.jpg">
    <meta property="og:image:type" content="image/jpeg">
    <meta property="og:image:width" content="400">
    <meta property="og:image:height" content="300">
    <meta property="og:image:alt" content="A shiny red apple with a bite taken out">

The `og:video` tag has the identical tags as `og:image`. Here is an example:

    <meta property="og:video" content="https://example.com/movie.swf">
    <meta property="og:video:secure_url" content="https://secure.example.com/movie.swf">
    <meta property="og:video:type" content="application/x-shockwave-flash">
    <meta property="og:video:width" content="400">
    <meta property="og:video:height" content="300">

The `og:audio` tag only has the first 3 properties available
(since size doesn't make sense for sound):

    <meta property="og:audio" content="https://example.com/sound.mp3">
    <meta property="og:audio:secure_url" content="https://secure.example.com/sound.mp3">
    <meta property="og:audio:type" content="audio/mpeg">

---
## <a id="array" href="#array">Arrays</a>

If a tag can have multiple values, just put multiple versions of the same
`<meta>` tag on your page. The first tag (from top to bottom) is given
preference during conflicts.

    <meta property="og:image" content="https://example.com/rock.jpg">
    <meta property="og:image" content="https://example.com/rock2.jpg">

Put structured properties after you declare their root tag. Whenever
another root element is parsed, that structured property
is considered to be done and another one is started.

For example:

    <meta property="og:image" content="https://example.com/rock.jpg">
    <meta property="og:image:width" content="300">
    <meta property="og:image:height" content="300">
    <meta property="og:image" content="https://example.com/rock2.jpg">
    <meta property="og:image" content="https://example.com/rock3.jpg">
    <meta property="og:image:height" content="1000">

means there are 3 images on this page, the first image is `300x300`, the middle
one has unspecified dimensions, and the last one is `1000`px tall.

---
## <a id="types" href="#types">Object Types</a>

In order for your object to be represented within the graph, you need to
specify its type. This is done using the `og:type` property:

    <meta property="og:type" content="website">

When the community agrees on the schema for a type, it is added to the list
of global types. All other objects in the type system are
[CURIEs](https://en.wikipedia.org/wiki/CURIE) of the form

    <head prefix="my_namespace: http://example.com/ns#">
    <meta property="og:type" content="my_namespace:my_type">

The global types are grouped into verticals. Each vertical has its
own namespace. The `og:type` values for a namespace are always prefixed with
the namespace and then a period.
This is to reduce confusion with user-defined namespaced types, which always
have colons in them.



### <a id="type_music" href="#type_music">Music</a>

* Namespace URI: [`http://ogp.me/ns/music#`](http://ogp.me/ns/music)

`og:type` values:

<a id="type_music.song" href="#type_music.song">`music.song`</a>

* `music:duration` &ndash; [integer](#integer) &gt;=1 &ndash; The song's length in seconds.
* `music:album` &ndash; [music.album](#type_music.album) [array](#array) -
  The album this song is from.
* `music:album:disc` &ndash; [integer](#integer) &gt;=1 &ndash;
  Which disc of the album this song is on.
* `music:album:track` &ndash; [integer](#integer) &gt;=1 &ndash;
  Which track this song is.
* `music:musician` &ndash; [profile](#type_profile) [array](#array) &ndash;
  The musician that made this song.

<a id="type_music.album" href="#type_music.album">`music.album`</a>

* `music:song` &ndash; [music.song](#type_music.song) &ndash; The song on this album.
* `music:song:disc` &ndash; [integer](#integer) &gt;=1 &ndash;
  The same as `music:album:disc` but in reverse.
* `music:song:track` &ndash; [integer](#integer) &gt;=1 &ndash;
  The same as `music:album:track` but in reverse.
* `music:musician` &ndash; [profile](#type_profile) &ndash;
  The musician that made this song.
* `music:release_date` &ndash; [datetime](#datetime) &ndash; 
  The date the album was released.

<a id="type_music.playlist" href="#type_music.playlist">`music.playlist`</a>

* `music:song` &ndash; Identical to the ones on [music.album](#type_music.album)
* `music:song:disc`
* `music:song:track`
* `music:creator` &ndash; [profile](#type_profile) &ndash; The creator of this playlist.

<a id="type_music.radio_station" href="#type_music.radio_station">`music.radio_station`</a>

* `music:creator` &ndash; [profile](#type_profile) &ndash; The creator of this station.



### <a id="type_video" href="#type_video">Video</a>

* Namespace URI: [`http://ogp.me/ns/video#`](http://ogp.me/ns/video)

`og:type` values:

<a id="type_video.movie" href="#type_video.movie">`video.movie`</a>

* `video:actor` &ndash; [profile](#type_profile) [array](#array) &ndash;
  Actors in the movie.
* `video:actor:role` &ndash; [string](#string) &ndash; The role they played.
* `video:director` &ndash; [profile](#type_profile) [array](#array) &ndash;
  Directors of the movie.
* `video:writer` &ndash; [profile](#type_profile) [array](#array) &ndash;
  Writers of the movie.
* `video:duration` &ndash; [integer](#integer) &gt;=1 &ndash; 
  The movie's length in seconds.
* `video:release_date` &ndash; [datetime](#datetime) &ndash; 
  The date the movie was released.
* `video:tag` &ndash; [string](#string) [array](#array) &ndash;
  Tag words associated with this movie.

<a id="type_video.episode" href="#type_video.episode">`video.episode`</a>

* `video:actor` &ndash; Identical to [video.movie](#type_video.movie)
* `video:actor:role`
* `video:director`
* `video:writer`
* `video:duration`
* `video:release_date`
* `video:tag`
* `video:series` &ndash; [video.tv_show](#type_video.tv_show) &ndash;
  Which series this episode belongs to.

<a id="type_video.tv_show" href="#type_video.tv_show">`video.tv_show`</a>

A multi-episode TV show.
The metadata is identical to [video.movie](#type_video.movie).

<a id="type_video.other" href="#type_video.other">`video.other`</a>

A video that doesn't belong in any other category.
The metadata is identical to [video.movie](#type_video.movie).



### <a id="no_vertical" href="#no_vertical">No Vertical</a>

These are globally defined objects that just don't fit into a vertical but
yet are broadly used and agreed upon.

`og:type` values:

<a id="type_article" href="#type_article">`article`</a> &ndash; Namespace URI: [`http://ogp.me/ns/article#`](http://ogp.me/ns/article)

* `article:published_time` &ndash; [datetime](#datetime) &ndash; 
  When the article was first published.
* `article:modified_time` &ndash; [datetime](#datetime) &ndash; 
  When the article was last changed.
* `article:expiration_time` &ndash; [datetime](#datetime) &ndash; 
  When the article is out of date after.
* `article:author` &ndash; [profile](#type_profile) [array](#array) &ndash;
  Writers of the article.
* `article:section` &ndash; [string](#string) &ndash; A high-level section name. E.g. Technology
* `article:tag` &ndash; [string](#string) [array](#array) &ndash;
  Tag words associated with this article.

<a id="type_book" href="#type_book">`book`</a> &ndash; Namespace URI: [`http://ogp.me/ns/book#`](http://ogp.me/ns/book)

* `book:author` &ndash; [profile](#type_profile) [array](#array) &ndash; Who wrote this book.
* `book:isbn` &ndash; [string](#string) &ndash;
  The [ISBN](https://en.wikipedia.org/wiki/International_Standard_Book_Number)
* `book:release_date` &ndash; [datetime](#datetime) &ndash; The date the book was released.
* `book:tag` &ndash; [string](#string) [array](#array) &ndash;
  Tag words associated with this book.

<a id="type_profile" href="#type_profile">`profile`</a> &ndash; Namespace URI: [`http://ogp.me/ns/profile#`](http://ogp.me/ns/profile)

* `profile:first_name` &ndash; [string](#string) &ndash; A name normally given to an individual by a parent or self-chosen.
* `profile:last_name` &ndash; [string](#string) &ndash; A name inherited from a family or marriage and by which the individual is commonly known.
* `profile:username` &ndash; [string](#string) &ndash; A short unique string to identify them.
* `profile:gender` &ndash; [enum](#enum)(male, female) &ndash; Their gender.

<a id="type_website" href="#type_website">`website`</a> &ndash; Namespace URI: [`http://ogp.me/ns/website#`](http://ogp.me/ns/website)

No additional properties other than the basic ones.
Any non-marked up webpage should be treated as `og:type` website.


---
## <a id="data_types" href="#data_types">Types</a>

The following types are used when defining attributes in Open Graph protocol.


<table style="width: 80%;">
  <col style="width:30%">
  <col style="width:40%">
  <col style="width:30%">
<thead>
<tr>
  <th>
    Tag
  </th>
  <th>
    Description
  </th>
  <th>
    Literals
  </th>
</tr>
</thead>
<tbody>
<tr>
  <td><a id="bool" href="#bool">Boolean</a></td>
  <td>A Boolean represents a true or false value</td>
  <td>true, false, 1, 0</td>
</tr>

<tr>
  <td><a id="datetime" href="#datetime">DateTime</a></td>
  <td>A DateTime represents a temporal value composed of a date
    (year, month, day) and an optional time component (hours, minutes)</td>
  <td><a href="https://en.wikipedia.org/wiki/ISO_8601">ISO 8601</a></td>
</tr>

<tr>
  <td><a id="enum" href="#enum">Enum</a></td>
  <td>A type consisting of bounded set of constant string values 
  (enumeration members).
  <td>A string value that is a member of the enumeration</td>
</tr>

<tr>
  <td><a id="float" href="#float">Float</a></td>
  <td>A 64-bit signed floating point number</td>
  <td>All literals that conform to the following formats:<br><br>
1.234<br>
-1.234<br>
1.2e3<br>
-1.2e3<br>
7E-10<br>
</td>
</tr>

<tr>
  <td><a id="integer" href="#integer">Integer</a></td>
  <td>A 32-bit signed integer. In many languages integers over 32-bits become 
    floats, so we limit Open Graph protocol for easy multi-language use.</td>
  <td>All literals that conform to the following formats:<br><br>
1234<br>
-123<br>
</td>
</tr>

<tr>
  <td><a id="string" href="#string">String</a></td>
  <td>A sequence of Unicode characters</td>
  <td>All literals composed of Unicode characters with no escape characters</td>
</tr>

<tr>
  <td><a id="url" href="#url">URL</a></td>
  <td>A sequence of Unicode characters that identify an Internet resource.
  <td>All valid URLs that utilize the http:// or https:// protocols</td>
</tr>
</tbody>
</table>

---
