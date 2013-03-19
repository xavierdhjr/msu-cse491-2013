Day 16 - Tu, Mar 19th, 2013
===========================

 * Read answers to questions from :doc:`day13` and :doc:`day14`.
 * Work on questions from :doc:`day15` and today.

In class
--------

Work on the in-class exercises from :doc:`day15`, or work on the following --

JSON-RPC
~~~~~~~~

Set up your virtualenv and install simplejson::

  %% source env491/bin/activate.csh
  %% pip install simplejson

Next, update your existing cse491-webz directory, or clone a new one
(c.f. https://github.com/ctb/cse491-webz).

Open up two login windows to CSE.

In one, run 'app.py'::

  %% source ~/env491/bin/activate.csh
  %% python app.py

In the other, run the 'json-rpc-client.py' file with the URL of your server::

  %% python json-rpc-client.py http://arctic.cse.msu.edu:8231/

but replacing the last URL with your actual URL.

What is going on here??

Note, you can do this FROM anywhere to the CSE server... including your
laptop, if you install simplejson there.

Questions
~~~~~~~~~

1. In the 'dispatch' machinery in app.py, why are the values also strings?
   Couldn't I just have used functions directly?

2. Why does the start_response make a copy of html_headers, e.g. why 'list()'? ::

       start_response('200 OK', list(html_headers))

3. What URL on the server is called for the 'hello' function?

4. What server-side function is called when the JSON-RPC client asks
   for 'hello'?  More generally, how does the JSON-RPC server-side
   machinery know what function to call?

5. What is the JSON format, and why do we need to use it?

Minute Cards
------------

In the last 5 minutes of class, please fill out this `minute card
survey
<https://docs.google.com/spreadsheet/viewform?formkey=dHFMMmg5djBFMTFQV2paSlNtWG94X0E6MQ#gid=0>`__.
