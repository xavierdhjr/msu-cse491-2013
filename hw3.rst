Homework #3
===========

Due Feb 21st at 11:59pm.

**This homework assignment is not yet complete, but you can go ahead and
start to work on it.**

---

1. In your latest cse491-drinkz, reimplement the data structures to be more
   efficient than lists.

   Specifically, reimplement _bottle_types_db as a Python 'set'
   containing tuples of (mfg, liquor, typ); and reimplement
   _inventory_db as a dictionary, keyed by tuples of (mfg, liquor)
   with the value in the dictionary being the total quantity.

   Note, the function calls in db.py should not change at all, and
   all of the tests should still pass without any change.

   For reference, you might check out the answers to the day 10 exercises here:

       http://msu-web-dev.readthedocs.org/en/latest/day10.html

2. I've provided a bunch of tests for cse491-drinkz on the branch
   'hw3-tests' on my github repository,

       https://github.com/ctb/cse491-drinkz

   They are all in the file 'drinkz/tests_by_ctb.py', with some test
   data.  Please *merge* this commit into *your* master branch, and
   fix your code so that all of the tests pass.  Note that you should,
   in general, *avoid* changing the test code -- the tests should be
   correct ;).

   Note, you can run just the tests in that file by typing::

      nosetests drinkz/tests_by_ctb.py

   A few pointers --

     - change db.get_liquor_amount() to return floating point values indicating
       ml.  (Yes, you'll need to change your own tests in test_drinkz.)

     - make sure 'bin/load-liquor-inventory' is the name of the bulk loading
       script, and that it takes two parameters: a list of bottle types,
       and a list of bottle amounts.

N. Finish up the HW, and tag it as 'hw3' by doing 

      git tag hw3
      git push origin tag:tag

   Then fill out this form: @@.

   (As usual, make sure all of your tests pass.)
