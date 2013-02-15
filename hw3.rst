Homework #3
===========

Due Feb 20th at 11:59pm.

See :doc:`day10` for HW 3.1, and :doc:`day12` for HW 3.3 and 3.4.  Also
see :doc:`day11` for collaboration instructions.

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

   (15/100 points)

2. I've provided a bunch of tests for cse491-drinkz on the branch
   'hw3-tests' on the ctb github repository,

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

   (15/100 points)

3. Implement the first part of recipes, as in :doc:`story-recipes`.

   a. Make a new file 'recipes.py' that can be imported as 'drinkz.recipes',
      and that defines a class 'Recipe'.

      The constructor for Recipe should take a name (a string) and a list of
      ingredient 2-tuples, (liquor type, amount).  For example, ::

         Recipe('vodka martini', [('vodka', '6 oz'), ('vermouth', '1 oz')])

      should create a recipe object for, well, you know!

   b. Define three new functions in db.py, 'add_recipe(r)',
      'get_recipe(name)', and 'get_all_recipes()'.  Decide if you
      should use a list, a dictionary, or a set to store 'em;
      implement it that way; and justify your decision in
      correctly-spelled and mostly grammatical English in the
      docstring (the """information""" at the top of the file) in
      db.py.

      Hint: don't use a list, Michelle!

   c. Define a method on the Recipe class, 'r.need_ingredients()', that
      returns a list of what is *missing* in order to make this recipe.
      The list of what is missing should be a list of 2-tuples,
      [('vodka', amount_in_ml), ...]; if it's empty, that means that
      you have everything you need.

      See the tests in 'drinkz/test_recipes.py' on branch
      'hw3-recipe-tests' for a few useful details.

   Please be sure to merge ctb branch 'hw3-recipe-tests' and check that
   *all* of your tests pass.

   Strong suggestion -- make a new function, say, 'convert_to_ml',
   that takes a string amount and converts it to ml; then factor out
   common functionality in db.py and recipes.py.  Extra kudos for
   writing tests just for that function, 'cause you know you should.

   Another strong suggestion -- write a new function in db.py, say,
   'check_inventory_for_type', that checks to see if you have a generic
   type (like 'blended scotch') and if so returns a list or set of
   mfg/liquor tuples.  You'll find it handy for (c).

   (50/100 points)

4. Write an HTML output script named 'make-html.py' in the top-level
   directory (above 'drinkz' and 'bin').

   This script should create a directory 'html', and four files
   within it: 'index.html', 'recipes.html', 'inventory.html', and
   'liquor_types.html'.  They should be created by the script *from
   the information in your database* using the db.py functions!

   The index file should link to the other three files.

   The liquor_types file should contain a list, in whatever form you
   want (ul, ol, table, etc.), of all of the liquor types in your
   database.

   The inventory file should contain a list of all of the liquor
   *amounts* in your database.

   The recipes file should contain a list of all of the recipes by
   name, with an entry next to each recipe that indicates whether or
   not you have all of the ingredients for that recipe (just a "yes"
   or a "no" (or a "heck yeah", Wes) is fine).

   Each of the files should link to the other three files with an a
   href tag, i.e. a clickable link.

   Be sure to populate your database with at least two examples of
   recipes, liquor types, and liquor inventory, and make sure that
   your output .  Check out test_recipes for inspiration -- you can
   just copy the data in their for your examples.

   Finally, make the output HTML files available in a directory on the
   CSE cluster under your account, as in :doc:`day12`.

   (20/100 points)

5. Finish up the HW, and tag it as 'hw3' by doing ::

      git tag hw3
      git push origin tag:tag

   Then fill out `this form <https://docs.google.com/forms/d/15eXnX8J3pQAUZcfrioC6fSNrCz-9ioyWRkUhfOFWog0/viewform>`__.

   (As usual, make sure all of your tests pass.)
