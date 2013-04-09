Homework #5
===========

Due Friday, Apr 12th at 5pm.  Note, no class on Thursday; no office
hours on Tuesday.  I'd suggest starting it BEFORE class on Tuesday so
that you can ask questions in class.

0. To hand in your homework, tag the latest master as 'hw5' and fill
   out `this form
   <https://docs.google.com/forms/d/1wZfTmUMr43OmvbLWCiu1XzgA1Ot7C6foLOc22LMBtJk/viewform>`__.
   If I don't see your code on github, I will not grade this homework
   and you will get a 0.  So, verify by going to github and finding
   the tag and checking it, and then doing a clean clone and test run
   of that specific tag.  Ask for help if you have trouble doing this.
   I mean it. I am serious. Don't screw around.  Double-check your
   push.  If you can't find it on github, I probably can't either.

1. Finish implementing `recipes
   <http://msu-web-dev.readthedocs.org/en/latest/story-recipes.html>`__.
   (40/100)

   Specifically,

     (a) Implement feature #3
     (b) Implement bulk loading of recipes from the command line.
     (c) Write HTML forms to enter liquor types, liquor inventories,
         and recipes.
     (d) Write JSON-RPC functions for the same.
     (e) Write tests against everything but the HTML forms.

   Describe how to bulk-load recipes in RECIPES.txt in your top-level
   directory.

   Use Jinja2 templating so that your functions use template rendering
   to dynamically construct strings that are returned via the WSGI
   server (10 of the 35).

2. Write up a feature implementation. (20/100)

   Look through the use cases `here
   <http://msu-web-dev.readthedocs.org/en/latest/day9.html>`__ and
   `here <http://msu-web-dev.readthedocs.org/en/latest/story-recipes.html>`__
   and choose one to write up.  You will be asked to implement this
   (or another one) for HW #6.

   Your feature should have --

      (a) a data component
      (b) an internal API for storing/retrieving/querying the relevant data
      (c) a Web interface for display and modifying the relevant data
      (d) a JSON-RPC set of functions

   So, write up a paragraph or three as in `the recipes use case
   <http://msu-web-dev.readthedocs.org/en/latest/story-recipes.html>`__
   and put it in a text file called FEATURE.txt in the home directory
   of your drinkz repository.

   If you work collaboratively, please write up multiple stories (i.e.
   you're welcome to brainstorm, but if two people are brainstorming,
   make up two features).

3. If your last name starts with a letter whose ord in Python is odd,
   do this (40/100):

   Write an WSGI server that speaks HTTP well enough to receive a GET,
   call a WSGI app (as in http://www.python.org/dev/peps/pep-0333/), and
   return the status and HTML.  Use only the 'socket' networking library;
   you should be speaking low-level TCP/IP, nothing else.

   A strong suggestion is to first write an HTTP server that returns
   just a static string (see 'get-page' from HW 4), and then slowly
   modify that to return the results of calling your WSGI app.

   See server.py from :doc:`day20` for basics of TCP/IP networking
   and binding a socket.

   Describe how to run your server in SERVER.txt.

4. If your last name starts with a letter whose ord in Python is even,
   do this (40/100):

   Develop a simple WSGI app (e.g. see cse491-webz/app.py) that can be
   attached to a WSGI server (as in
   http://www.python.org/dev/peps/pep-0333/) and a set of client tests
   that use the 'socket' library to connect to the WSGI server and
   run the functions in the WSGI app, and test that you get back the
   right thing from the server.

   Your client & app should exercise:

     * a straight up GET
     * a form submission GET
     * image retrieval

   Describe how to run your client tests (they can be run using nose
   if you want, or just as a separate script) in CLIENT.txt.

Hint::

   >>> print ord('a')

Also, ask questions :)
