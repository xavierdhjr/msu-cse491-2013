Refactoring Example
===================

Consider the following code::

   def get_liquor_amount(mfg, liquor):
       "Retrieve the total amount of any given liquor currently in inventory."
       amounts = []
       for (m, l, amount) in _inventory_db:
           if mfg == m and liquor == l:
               amounts.append(amount)
   
       total = 0.0
       for amount in amounts:
           # amount is going to be in format "number units"
           num, units = amount.split()
           num = float(num)
           units = units.lower()
   
           if units == 'ml':
               total += num
           elif units == 'oz':
               total += 29.5735 * num
           elif units == 'gallon':
               total += 3785.41 * num
           else:
               raise Exception("unknown unit %s" % units)

       return total

Note that this function has two actual pieces of functionality in it.
First, it converts units to ml; and second, it sums all of the amounts
from a given type of mfg/liquor.  The first piece of functionality is
useful all on its own, but right now it's tied into the
get_liquor_amount function; to make it reusable, let's break it out
into a function of its own.

This can be done in three steps.  First, define a new function and
cut/paste/reindent code::

   def convert_to_ml(amount):
      # amount is going to be in format "number units"
      num, units = amount.split()
      num = float(num)
      units = units.lower()
   
      if units == 'ml':
         total += num
      elif units == 'oz':
         total += 29.5735 * num
      elif units == 'gallon':
         total += 3785.41 * num
      else:
         raise Exception("unknown unit %s" % units)

   def get_liquor_amount(mfg, liquor):
       "Retrieve the total amount of any given liquor currently in inventory."
       amounts = []
       for (m, l, amount) in _inventory_db:
           if mfg == m and liquor == l:
               amounts.append(amount)
   
       total = 0.0
       for amount in amounts:
           ## XXX THIS CODE WAS CUT AND MOVED XXX

       return total

Second, replace the cut code with a call to the new function::

   def get_liquor_amount(mfg, liquor):
       "Retrieve the total amount of any given liquor currently in inventory."
       amounts = []
       for (m, l, amount) in _inventory_db:
           if mfg == m and liquor == l:
               amounts.append(amount)
   
       total = 0.0
       for amount in amounts:
           amount = convert_to_ml(amount)  # <-- this line
           total += amount

       return total

And third, simplify the function, now that you have taken out a big,
ugly chunk of code. ::

   def get_liquor_amount(mfg, liquor):
       "Retrieve the total amount of any given liquor currently in inventory."
       amounts = []

       total = 0.0 # <-- this line moved

       for (m, l, amount) in _inventory_db:
           if mfg == m and liquor == l:
               total += convert_to_ml(amount)  # <-- this line moved
   
       return total

Note that at no time did you *change* functionality, you merely *added*
some.  Your tests should pass unchanged BEFORE and AFTER refactoring.
