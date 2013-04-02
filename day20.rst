Day 20 - Th, April 2, 2013
===========================

Schedule:

 * Moar discussion of HTTP
 * Work on questions from :doc:`day19` and today.
 * Minute cards.

Note: no class on Thursday.

TCP/IP Networking
-----------------

You can use this for a reference --

http://www.tutorialspoint.com/python/python_networking.htm

Take a look at the stuff under network/ in the latest cse491-webz --

     https://github.com/ctb/cse491-webz.git

This is a very simple client/server back-and-forth for TCP/IP.

Questions --

1. How can one side of a connection know how much data remains to be
   read from the other side of the connection?

2. Run the server, connect to it with the client, and then use CTRL-C
   to kill it.  What signal does the client get?

3. Modify the client to send a file to the server upon connection.
   Make sure that both sides "clean up", that is, exit properly.

   Note::

      data = open(filename).read()

   to read bytes in from a file, and ::

      fp = open(filename, 'w')
      fp.write(data)
      fp.close()

   to save data to a file.

4. Modify the server to send a file to the client as soon as the
   client connects.  Make sure that both sides "clean up".

5. Modify the client to send a file containing text that the server then

     (a) uppercases

     (b) replaces all As with ZZs

   Note, ::

      s = t.replace('A', 'ZZ')

   will do the latter.

Templating with Jinja2, round 2
-------------------------------

Look at the Jinja2 stuff from :doc:`day19`, and grab the latest
cse491-webz.  Try rendering 'test4.html' and 'test5.html'; look at
templates/test4.html and templates/test5.html.  What's going on?

Things to try --

 - modify 'is_tuesday' in render.py to be True.  What happens in test4.html?

 - What does the |e do (see {{ name|e }}) in test5.html?  Try removing it,
   and load stuff in a browser.

 - Revisit test3.html.  Do you understand what's going on here?

Minute Cards
------------

In the last 5 minutes of class, please fill out this `minute card
survey
<https://docs.google.com/spreadsheet/viewform?formkey=dHFMMmg5djBFMTFQV2paSlNtWG94X0E6MQ#gid=0>`__.
