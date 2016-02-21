# Meteor Boilerplate - Material Design Version

A starting point for MeteorJS applications that use Material Design.

* [Included Packages](#included-packages)
* [Installation](#installation)
* [File Structure and Organization](#file-structure)
* [SEO](#seo)
* [Favicons and Touch Icons](#favicons-and-touch-icons)
* [Seed Data](#seed-data)

## <a name="included-packages"></a> Included Packages

* [Material Design](http://www.google.com/design/spec/material-design/introduction.html)
  * [materialize:materialize](http://materializecss.com/)
  * [useraccounts:materialize](https://github.com/meteor-useraccounts/materialize)
  * [gildaspk:autoform-materialize](https://github.com/djhi/meteor-autoform-materialize/)
* Collections:
  * [dburles:collection-helpers](https://github.com/dburles/meteor-collection-helpers)
  * [reywood:publish-composite](https://github.com/englue/meteor-publish-composite)
  * [aldeed:autoform](https://github.com/aldeed/meteor-autoform)
  * [aldeed:collection2](https://github.com/aldeed/meteor-collection2)
* Router:
  * [kadira:flow-router](https://github.com/kadirahq/flow-router)
  * [zimme:active-route](https://github.com/zimme/meteor-active-route)
* Authentication
  * [Meteor User Accounts](https://github.com/meteor-useraccounts/core)
  * [alanning:roles](https://github.com/alanning/meteor-roles)
* Misc:
  * [Moment.js](http://momentjs.com/)
  * [Underscore.js](http://underscorejs.org/)
  * [Underscore.string](http://epeli.github.io/underscore.string/)
  * [gfk:mailgun-api](https://atmospherejs.com/gfk/mailgun-api)

## <a name="installation"></a>Installation

1. Clone this repo to `<yourapp>`

  `git clone https://github.com/samudranb/meteor-materialize-boilerplate.git <yourapp>`

2. Remove `.git`

  `cd <yourapp> && rm -rf .git`

3. Start coding!

## <a name="file-structure"></a>File Structure and Organization

Following a "module" based approach to organization.
```
my-app
|-- .meteor
|-- client
  |-- css
    |-- main.css
  |-- js
    |-- main.js
  |-- main.html
|-- modules
  |-- module1
    |-- client
      |-- autoform.js
      |-- events.js
      |-- helpers.js
      |-- main.js
      |-- rendered.js
      |-- routes.js
      |-- templates.html
    |-- server
      |-- main.js
      |-- methods.js
      |-- publish.js
      |-- routes.js
    |-- both
      |-- collections.js
  |-- module2
    |-- ...
  |-- ...
|-- lib
  |-- helpers.js
|-- public
  |-- fonts
    |-- ...
  |-- img
    |-- ...
|-- private
|-- server
  |-- ...
```
[Documentation about structuring your app](http://docs.meteor.com/#/full/structuringyourapp)

* Client-only files are stored in the `client` directory
* Server-only files are stored in the `server` directory
* Shared files are stored in the `both` directory
* The `private` and `public` directories are for either private or public assets.

## <a name="seo"></a> SEO

Page titles, meta descriptions and tags are handled by the [kadira:dochead](https://atmospherejs.com/kadira/dochead) package.

### Spiderable - not installed
Look at this for enabling search engine crawlers and other robots

## <a name="favicons-and-touch-icons"></a>Favicons and Touch Icons

Upload your intended image to http://realfavicongenerator.net/ and place the resulting images in `public/images/favicons`

## Seed Data - Not installed

Use the [dburles:factory](https://github.com/percolatestudio/meteor-factory) and [anti:fake](https://github.com/anticoders/meteor-fake/) packages to generate fake collection data for testing your UI. See `server/seeds.js` for an example:

```
Meteor.startup(function() {

  Factory.define('item', Items, {
    name: function() { return Fake.sentence(); },
    rating: function() { return _.random(1, 5); }
  });

  if (Items.find({}).count() === 0) {

    _(10).times(function(n) {
      Factory.create('item');
    });

  }

});

```
