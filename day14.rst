Day 14 -- Th, Feb 21st, 2013
============================

 - Group in pairs
 - Complete in-class exercise about WSGI
 - Minute cards

Pairs
-----

Please distribute yourself as on Tuesday into the Day 13 groups (see :doc:`day13`).

WSGI, Web servers, and extra features
-------------------------------------

Grab the latest additions to cse491-webz::

   % cd cse491-webz
   % git pull https://github.com/ctb/cse491-webz.git master

This may require resetting your repository first -- if you want to just revert
to the last commit, do ::

   % git checkout -f master

NOTE, this will eliminate any changes you have made.  Make sure you want
to do that :)

Now run app.py, and play with the new features (image display and forms).
Then contemplate the following questions, in addition to the questions
from Day 13 (see :doc:`day13`):

1. How many Web requests are made to the server in order to load the
   main (/) page, and why?

2. When you press 'submit' on the form page, what URL is received by the
   server?

3. What does 'formdata' look like, and what does urlparse do to it?

4. If you look at the URL for 'recv', why does it have a '/' before it when
   the form doesn't specify a '/'? Where does the '/' come from?

5. What is 'favicon.ico'

6. From earlier work, you know that 'index.html' is served from the CSE
   Web server when http://www.cse.msu.edu/~username/ is requested.  What
   determines that?

Next steps
----------

Please try to merge 'cse491-linkz' and 'cse491-webz' so that webz is
serving the static files that were produced by cse491-linkz.

Note that you can merge two DIFFERENT repositories with 'git pull', too...

Minute Cards
------------

In the last 5 minutes of class, please fill out this `minute card
survey
<https://docs.google.com/spreadsheet/viewform?formkey=dHFMMmg5djBFMTFQV2paSlNtWG94X0E6MQ#gid=0>`__.
