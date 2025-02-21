# ember-data-url-templates

[![Build Status](https://travis-ci.org/amiel/ember-data-url-templates.svg)](https://travis-ci.org/amiel/ember-data-url-templates)
[![Ember Observer Score](http://emberobserver.com/badges/ember-data-url-templates.svg)](http://emberobserver.com/addons/ember-data-url-templates)
[![Dependency Status](https://david-dm.org/amiel/ember-data-url-templates.svg)](https://david-dm.org/amiel/ember-data-url-templates)
[![devDependency Status](https://david-dm.org/amiel/ember-data-url-templates/dev-status.svg)](https://david-dm.org/amiel/ember-data-url-templates?type=dev)


Compatibility
------------------------------------------------------------------------------

* Ember.js v3.24 or above
* Ember CLI v3.24 or above
* Node.js v12 or above


Installation
------------------------------------------------------------------------------

ember-data-url-templates is under early development. Feedback is welcome, and of course,
so are pull requests.

Url templates are compiled with [geraintluff/uri-templates](https://github.com/geraintluff/uri-templates),
which fully implements [RFC 6570](http://tools.ietf.org/html/rfc6570).

## Usage

See the [Contributing](CONTRIBUTING.md) guide for details.


export default DS.RESTAdapter.extend(UrlTemplates, {
  urlTemplate: '{+host}/comments{/id}',
  queryUrlTemplate: '{+host}/comments{?query*}',
  createRecordUrlTemplate: '{+host}/users/{userId}/comments',

  session: Ember.inject.service(),

  urlSegments: {
    userId() {
      return this.get('session.userId');
    }
  }
});
```

## Contributing

### Installation

* `git clone` this repository
* `npm install`
* `bower install`

### Running Tests

* `ember test` or
* `ember test --server`

## TODO

Here is a short list of things I'd like to support:

* Use a template provided by the API (like `links`)
