Day 23 - Th, April 18, 2013
===========================

Schedule:

 * Minute cards.
 * 
 * More database: joins, transactions, multithreading, synch, etc.

Questions/TODO
--------------

(This is an example of using the `jQuery JavaScript library <http://jquery.com/>`__ with `AJAX <https://en.wikipedia.org/wiki/Ajax_(programming)>`__ and
`JSON-RPC <http://en.wikipedia.org/wiki/JSON-RPC>`__)

Grab the latest version of https://github.com/ctb/cse491-webz; for example,
on the CSE cluster, you could do::

   mkdir day23
   cd day23
   python2.7 -m virtualenv env
   source env/bin/activate.csh
   pip install simplejson

to get the environment running, and then ::

   git clone https://github.com/ctb/cse491-webz.git
   cd cse491-webz
   python app.py
   
Now, go to the URL of the Web server, and take a look at the
'/content' URL, which is loading from 'somefile.html'.  (You can look
at the `source of 'somefile.html' on github <https://github.com/ctb/cse491-webz/blob/master/somefile.html>`__, if you want.)

On the '/content' page, you'll see three input box regions

The value in the first is set dynamically by JavaScript using the jQuery
library.

The value in the second is output in an alert box upon change.

The two values in the third are summed and displayed on the page.

TODO:

1. At your table, talk through the code for the first and second input
   boxes.  What's going on?  (One thing you can do to find out is edit
   the HTML to remove the first <script>, which loads jQuery; this
   will disable all the JavaScript.)

2. For the third input box ("retrieve from server"), write down a
   flowchart on your whiteboard that details, in order, what happens
   in terms of network traffic and function calls in Python (on the
   server side) and JavaScript (on the client side).  Your flowchart
   should include

3. For the last text box ("retrieve from server"), why does an alert box
   pop up after you enter the first value?

SQL Multiple tables, and Transactions
-------------------------------------

`Tables <http://nbviewer.ipython.org/urls/raw.github.com/ged-lab/msu-cse491-2013/master/sqlite3-tables.ipynb>`__.

`Transactions <http://nbviewer.ipython.org/urls/raw.github.com/ged-lab/msu-cse491-2013/master/sqlite-transactions.ipynb>`__.

Minute Cards
------------

In the last 5 minutes of class, please fill out this `minute card
survey
<https://docs.google.com/spreadsheet/viewform?formkey=dHFMMmg5djBFMTFQV2paSlNtWG94X0E6MQ#gid=0>`__.
