Day 15 - Tu, Mar 12th, 2013
===========================

 * Mini lecture
 * Read answers to questions from :doc:`day13` and :doc:`day14`.
 * Work on integrating webz, linkz, 

Answers to questions from Day 13 and Day 14
-------------------------------------------

If you have specific questions to ask about any of this, stop by the
table at the end of the room (the one that Wes usually sits at).

Note, we'll have a quizlet next Tuesday on WSGI and Web stuff to gauge
absorption of the material.  PANIC.

From :doc:`day13`:

1. How does your Web browser know how to contact *your* app.py instead
   of your neighbor's?

   Answer: the hostname and port (http://hostname:port/) are unique
   identifiers to your running application.

2. Where is the logic in app.py for what is returned?

   Answer: See `app.py
   <https://github.com/ctb/cse491-webz/blob/master/app.py>`__, 'if
   path == ' section.  Here, 'path' is everything AFTER the hostname
   and port, above.

3. What role does content type play in what is returned?

   Answer: the browser (on the receiving end, i.e. your computer) uses
   content-type to decide how to interpret was is returned -- HTML,
   an image, etc.

4. What variable type is 'data'?

   Answer: A string (potentially a binary string, but still a string).

5. What role does 'status' play?

   Answer: 'status' is essentially metadata ABOUT the connection,
   and it helps the browser decide what to do with the data it receives.
   For example, '200 OK' means "everything is fine! no worries!"
   while '403 Not Found' means "whatever I'm giving you is basically
   an error message."  There are redirects and other things, too.

6. What happens if 'somefile.html' isn't present?

   Answer: An error!  Because we don't trap exceptions within the SimpleApp
   class, the WSGI server catches them and returns a complaint.

7. How does the Web browser know what is being returned?

   Answer: See #3, above; 'content-type'.

8. Why do we generate a random number at the bottom of the script?

   Answer: that's the port.  If you and another person try to bind the
   same network port, only one of you will get it and the other person
   will get an error.  (Try it!)

9. How is PATH_INFO generated, ultimately?

   Answer: PATH_INFO is whatever's on the URL line after the hostname
   and port (and before any ? -- more on that later)

10. What happens when you 'print' something from within app.py?

    Answer: It goes to the standard output of the process *running* app.py,
    which (if you followed all my instructions above) is
    arctic.cse.msu.edu.

11. When does __call__ in app.py get executed?

    Answer: when the WSGI server receives a request!  Read more about
    that `here <http://www.python.org/dev/peps/pep-0333/>`__ and in
    days to come.

From :doc:`day14`,

1. How many Web requests are made to the server to load '/'?

   Answer: two, technically, although you may see three (see
   favicon.ico, below).  First, a Web request to load the HTML,
   and then a second one to load the image ('<img>' tag).

   Technically, only one "thing" is loaded at a time -- one bundle
   of content-type and data.  Each additional bundle (different content
   type or logical unit of content -- think images, CSS, JavaScript, etc.)
   requires an additional request.

2. When you press 'submit' on the form page, what URL is received by the
   server?

   Answer: whatever is specified in the 'action' tag of the form.

3. What does 'formdata' look like, and what does urlparse do to it?

   Answer: it's a string that looks like 'key=value&key2=value2', and it
   encodes all of the data from the form.  urlparse turns it into a
   dictionary-like data structure.

4. Why does the URL for 'recv' have a '/' before it when the
   form doesn't specify a '/'?

   Answer: the browser treats URLs like file paths, so if you are
   at a form from URL '/some/place', and submit to 'process', it
   will automatically set the URL to '/some/process'.  You can use
   '../' and './' as you would on a file system.

5. What is 'favicon.ico'?

   Answer: it's a convention for the "site icon" -- if the browser
   can load a site's /favicon.ico, then it uses the icon in the
   tool bar.

6. What determines that 'index.html' is served from the CSE Web server
   for URLs ending in '/'?

   Answer: as in 'app.py', whatever Web server is running determines that.
   It's a convention, not a requirement.


In class
--------

Work on one of the following --

1. Integrating 'cse491-linkz' and 'cse491-webz',

      https://github.com/ctb/cse491-linkz
      https://github.com/ctb/cse491-webz

   so that your 'webz' is serving the files created by 'linkz'.

2. Integrate the *dynamic* content generation from 'linkz' -- i.e., the
   functions that produce HTML -- into the 'webz' calls, so that instead
   of the linkz code writing a file that webz serves, the webz code
   calls a function that produces the HTML directly.

3. Design some forms for cse491-drinkz functionality, including --

     * Adding a bottle type
     * Adding to inventory
     * Adding a recipe

   In the latter case, how could you design a form to add multiple
   ingredients etc?  Do you want to use pull down menus or select
   ingredients from a menu? Think about what you would want to see
   as a user.

   **Strong suggestion** -- write Python code to generate the HTML in
   the forms.  That way, if you want to get information from the db
   module, you can do so when generating your repository.  Plus,
   extra abstraction is always good, right?

4. Clean up your github repository. For example,

     * Make sure that 'master' is the default branch when you clone your
       repo.

     * Make sure that your master branch contains everything up through HW 3.

     * Eliminate any unneeded branches and tags (please leave HW 3 alone :)

     * Eliminate and/or add to .gitignore any .pyc files

     * Make sure your code is up to date with HW 3, if it's already been
       graded.

5. Work on code cleanup.  For example,

     * Change unit conversion over to use dictionaries, and have only a
       single function.

     * Eliminate or fix messy or inaccurate comments.

Minute Cards
------------

In the last 5 minutes of class, please fill out this `minute card
survey
<https://docs.google.com/spreadsheet/viewform?formkey=dHFMMmg5djBFMTFQV2paSlNtWG94X0E6MQ#gid=0>`__.
