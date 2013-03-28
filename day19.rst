Day 19 - Th, Mar 28th, 2013
===========================

Schedule:

 * Discussion of HTTP
 * Ask homework-related questions & clarifications.
 * Work on questions from :doc:`day18` and today.
 * Minute cards.

More about HTTP
---------------

Read `this document <http://www.jmarshall.com/easy/http/>`__ and connect
it to what I show you in class today & your 'GET' work.  Ask questions!

Topics I'll try to cover today:

 - connecting to port 80 of 'lyorn.idyll.org' and 'www.google.com'
 - structure of HTTP requests and responses
 - "metadata" other than received and submitted content
 - URLs at google.com

Using JSON-RPC in anger
-----------------------

Take a look in the 'twitter/' subdirectory of ::

   https://github.com/ctb/cse491-webz

These scripts turn an address INTO a geolocation (latitude &
longitude) using the Google Maps API, and turn a geolocation back into
an address (using the Twitter geolocation API, from `v1 of the API
<https://dev.twitter.com/docs/api/1>`__).

Your mission --

1. Hook the scripts or code up so that you can take an address and see
   what happens when you geolocate it via Google Maps and decode it
   via Twitter.

2. Look through the `latest Twitter API (v1.1)
   <https://dev.twitter.com/docs/api/1.1>`__ and work on gaining
   authenticated access to the API for your own Twitter account.
   Note, excessive googling for answers may be needed!

   Bonus: sign up for a Twitter account if you don't have one ;).

Templating with Jinja2
----------------------

As you have probably already seen, there's lots of repetition in your
various HTML files.  This will get worse and worse as you add stylesheets,
JavaScript, etc.  Plus, you run the very real risk of lots of duplicate
code, some of which will be right and some of which will be wrong.

The correct solution for this is *templating*.  We'll be using `jinja2
<http://jinja.pocoo.org/docs/>`__ templating, which is similar in
concept to many other templating systems.

The basic idea is that you have a template "source file" that you then
"render", providing variables to fill in for whatever needs to be
customized for that page.

Trying it out
~~~~~~~~~~~~~

Grab the latest::

   https://github.com/ctb/cse491-webz

Enable your virtualenv::

   source env491/bin/activate.csh

And install jinja2::

   pip install jinja2

Now, go into cse491-webz/jinja2/, and try running::

   python render.py test1.html

and ::

   python render.py test2.html

and ::

   python render.py test3.html

Look at the files in 'templates/'.  What's going on here?

Minute Cards
------------

In the last 5 minutes of class, please fill out this `minute card
survey
<https://docs.google.com/spreadsheet/viewform?formkey=dHFMMmg5djBFMTFQV2paSlNtWG94X0E6MQ#gid=0>`__.
