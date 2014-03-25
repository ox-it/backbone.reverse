backbone.reverse
================

Reverse URL resolution with Backbone routers. This plugin currently only
handles the *most simple* usecases. Inspired by the Django framework.

Usage from JavaScript
---------------------

Firstly create your Router with the ReversibleRouter from backbone.reverse.js

With the following routes:

    {
        'places/:id': 'detail',
        'categories*category_name': 'categories',
    }

Examples:

    Backbone.history.reverse('detail', {id: 'oxpoints:53255'}));
    > '#places/oxpoints:53255

    Backbone.history.reverse('categories', {category_name: '/university/colleges'}));
    > '#categories/university/colleges'

Usage from Handlebars
---------------------

See `helpers/reverse.js` for the Handlebars helper.

Due to the restrictions of Handlebars we don't have a very nice syntax for
calling Backbone.history.reverse instead calls look like the following.

    {{ reverse <name of route function> <key1> <val1> <key2> <val2> }}

With a sequence of key val argument pairs which form the paramater Object.
