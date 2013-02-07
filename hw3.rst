Homework #3
===========

Due Feb 21st at 11:59pm.  If you work in a group, please work in a
group distinct from those you work with in the class.

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
