Day 22 - Tu, April 16, 2013
===========================

Schedule:

 * Minute cards.
 * Database foo; SQLite

Questions/TODO
--------------

Following the code in `this sqlite IPython Notebook <http://nbviewer.ipython.org/urls/raw.github.com/ged-lab/msu-cse491-2013/master/sqlite.ipynb>`__,

1. As a group at each table, discuss where in your code (specific code
   functionality) the database should be created, where the database
   should be opened, where it should be accessed (read only) and where
   the data in the database should be updated or modified.

   Write down your answers for discussion.

2. What would a database schema for your bottle types DB look like?
   Write a small script on the CSE cluster (to call with python2.6)
   that opens a new database and creates that schema.

3. Write an INSERT statement to add a new bottle type.  Be sure to use
   '?' placeholders and variables.  Add it to your script.  Make sure
   the INSERT statement actually adds to the table (by calling SELECT *
   afterwards).

4. Write a SELECT statement to handle the query in _check_bottle_type_exists
   (in your drinkz/db.py).  Add it to your script and print out the results
   (c.fetchall()).

NOTE, you have to use python2.6 on the CSE cluster in order to use sqlite3.

Minute Cards
------------

In the last 5 minutes of class, please fill out this `minute card
survey
<https://docs.google.com/spreadsheet/viewform?formkey=dHFMMmg5djBFMTFQV2paSlNtWG94X0E6MQ#gid=0>`__.
