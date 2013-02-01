Homework #2
===========

Due Feb 6th at 11:59pm.  If you work in a group, please work in a
group distinct from those you work with in the class.

---

0. Clone my cse491-drinkz repository into your own directory tree and
   set up your own github repo as origin, and mine as 'ctb'::

      git clone https://github.com/ctb/cse491-drinkz.git
      git remote rm origin
      git remote add origin https://github.com/YOURUSERNAME/cse491-drinkz.git
      git remote add ctb https://github.com/ctb/cse491-drinkz.git

   (replace YOURUSERNAME with, well, your user name :)

   Next, remove your master branch and replace it with mine::

      git push origin :master  # this deletes your master branch
      git push origin master:master  # this replaces it with mine

   (After all of this, 'git diff origin/master' should return no differences.
   If you're not sure, check with someone!)

1. Using load_bulk_data.load_bottle_types as inspiration, modify the
   bulk loading functions to ignore empty lines (note: 'if not
   line.strip()') and '#'-commented lines.  Write tests for this functionality
   to make sure it works; the tests should check each piece of functionality
   separately.

2. Next, write a generic generator wrapper around the 'csv.reader' that
   eliminates commented lines and whitespace lines.  You should have one
   function that can be used by all the bulk loading functions; for example,

      new_reader = data_reader(fp)

      for mfg, name, typ in new_reader:
         ...

   should now work.  Make sure that all your tests still pass!

3. Implement try/except wrappers around each individual line so that malformed
   lines in the bulk loading functions simply print out an error rather than
   failing.  (See 'test_add_to_inventory_2' in test_drinkz.py for the basic
   formatting of exception handling.)

4. Fix get_liquor_amount to correctly sum different types of liquor in oz
   and ml, and report in ml.  Write tests to make sure it works properly!

5. Add a script in the main directory called 'show-liquor-amounts' that
   reports the amounts of liquor that you have, as well as the types.
   (You can base it off the script 'show-liquor-types'.)  Don't bother
   writing any tests for this one.

6. Add a script under bin/ called load-liquor-inventory that runs the
   bulk loading function on a text file; model it on load-liquor-types.
   Write tests for it, based on the tests for load-liquor-inventory.

7. Push all your homework to your github repo and send me a pull request.
