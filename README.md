# mason-ry [![unlicense](https://img.shields.io/badge/un-license-green.svg?style=flat)](http://unlicense.org)

A [Polymer 1.0]-based web component that wraps [Masonry], a grid layout library.

[Polymer 1.0]: https://www.polymer-project.org/1.0/
[Masonry]: http://masonry.desandro.com

## Installation

Use [bower]:

```shell
$ bower install --save mason-ry
```

[bower]: http://bower.io

## Usage

Here's a responsive example (elements have a percentage width on narrow screens, fixed width on wide screens):

```html
<link rel="import" href="../bower_components/iron-media-query/iron-media-query.html">
<link rel="import" href="../bower_components/mason-ry/mason-ry.html">

<dom-module id="demo-masonry">
  <style>
    article, .sizer {
      width: 50%;
      margin: 0 0 1rem;
      padding: 0;
    }
    @media screen and (min-width: 500px) {
      article, .sizer { width: 260px; }
    }
  </style>

  <template>

    <iron-media-query query="(min-width: 500px)" query-matches="{{isFitWidth}}"></iron-media-query>

    <mason-ry id="articles" is-fit-width="[[isFitWidth]]" percent-position="[[!isFitWidth]]"
      column-width=".sizer" item-selector="article" transition-duration="0.1s">

      <div class="sizer"></div>
      <template is="dom-repeat" items="[[news.articles]]">
        <article>
          <img src="[[item.image]]" alt="[[item.alt]]" />
          <figcaption>[[item.title]]</figcaption>
        </article>
      </template>
    </mason-ry>

  </template>
</dom-module>

<script> 'use strict';
	Polymer({
		is: 'demo-masonry'
    /* Not pictured: the data */
  });
</script>
```

## Contributing

Please feel free to submit pull requests!
Bugfixes and simple non-breaking improvements will be accepted without any questions :-)

By participating in this project you agree to follow the [Contributor Code of Conduct](http://contributor-covenant.org/version/1/1/0/).

## License

This is free and unencumbered software released into the public domain.  
For more information, please refer to the `UNLICENSE` file or [unlicense.org](http://unlicense.org).
