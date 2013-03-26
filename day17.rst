Day 17 - Th, Mar 21st, 2013
===========================

Schedule:

 * Read over :doc:`hw4` and ask questions.
 * Read answers to questions from :doc:`day13` and :doc:`day14`.
 * Work on questions from :doc:`day15`, :doc:`day16`, and today.
 * Minute cards.

Testing WSGI and Web apps, round 1
==================================

Update your cse491-webz branch with the latest master from 
https://github.com/ctb/cse491-webz, and run the tests in
test_app using nose::

   %% nosetests

Now go look at 'test_app.py' -- 

1. What is the call order of functions to get down to the 'index'
   function in app.py in test_index()?

2. What is the call order of functions to get down to the 'recv'
   function in app.py in test_recv()?

3. Why is the '/form' function not called in the tests at all?

4. Try refactoring test_app.py so that common code in test_index and
   test_form_recv is in one function that is then called in those two
   test functions.

Slightly more advanced magic
============================

Look at the 'magic' branch on https://github.com/ctb/cse491-webz, especially
the calls under __main__::

   https://github.com/ctb/cse491-webz/blob/magic/json-rpc-client.py#L52

This is an attempt to clean up the equivalent calls from the main branch::

   https://github.com/ctb/cse491-webz/blob/master/json-rpc-client.py#L30

How does this work??

More specifically,

I. What is the chain of function calls that leads to and from 'call_remote'
   on the magic branch when you ask for 'magic.hello()' the first time?
   And the second time?

II. What does JSON_RPC_Magic do, and why is it separate from or different
    from MagicFunction?

Minute Cards
------------

In the last 5 minutes of class, please fill out this `minute card
survey
<https://docs.google.com/spreadsheet/viewform?formkey=dHFMMmg5djBFMTFQV2paSlNtWG94X0E6MQ#gid=0>`__.
