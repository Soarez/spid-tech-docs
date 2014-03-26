# Endpoints

<h2 id="pagination">Pagination</h2>

Pagination is supported in many SPiD endpoints.

<h2 id="filters">Filters</h2>

<h2 id="locale">Locales</h2>

SPiD supports localized content for some endpoints. Whenever that is the case,
the available locales are:

* `nb_NO` - For Norwegian Bokmål
* `sv_SE` - For Swedish
* `en_US` - For American English (default)

Although rare, you may run into content that has not been localized. In these
cases, you will get English content back.

<h2 id="formats">Response formats</h2>

Most SPiD endpoints can respond with various response formats. The format used
is determined by the `format` query parameter supported by all endpoints. Refer
to individual endpoint API docs for information on what formats are supported in
each case.

<h3 id="format-json">JSON</h3>

[JSON](http://json.org/) is the most commonly supported response type used in
SPiD. It is also the default format used by most endpoints. To force the use of
JSON, send the following query parameter:

```text
format=json
```

<h3 id="format-jsonp">JSONP</h3>

[JSONP](http://en.wikipedia.org/wiki/JSONP) is supported by all endpoints that
support JSON. JSONP ("JSON with padding") is JSON wrapped in a function call,
served as JavaScript. Because JavaScript can be served from mixed sources on a
web page, JSONP circumvents certain security restrictions and complexity
associated with other forms of
[cross-origin resource sharing](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing),
at the expense of a potentially higher risk.

To force the use of JSONP, send the following query parameter:

```text
format=jsonp
```

The response will be executable JavaScript:

```js
callback({ ... });
```

<h3 id="format-xml">XML</h3>

A few SPiD endpoints support XML responses. To force its use, provide the
following query parameter:

```text
format=xml
```

<h2 id="params">Parameters</h2>

Some query parameters support multiple values. Whenever this is the case, you
have a few options for providing these values.

You can send a single value:

```text
key=single-value
```

...you can provide multiple values in a comma-separated list:

```text
key=one-value,other-value
```

...and you can provide multiple values in array-like notation, supported by some
server-side environments (PHP, Rails, others):

```text
key[]=one-value&key[]=other-value
```