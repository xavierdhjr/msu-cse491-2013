Day 8 -- Th, Jan 31, 2013
=========================

Rough schedule for today, summary:

 - reviewing git & taking questions
 - version control principles
 - back to drinkzing
 - use cases!!
 - minute cards

Note: mailing list archive is at http://lists.idyll.org/pipermail/cse491-spring-2013/

Reviewing git and taking questions
----------------------------------

See :doc:`day6`, "Resolving conflicts during merge", and :doc:`day7`.

At this point, I'm assuming wrt git --

 - you know enough git to handle many things
 - you can work through most problems
 - you'll ask questions if you need help

Also see the various e-mails recommending git tutorials - `here
<http://lists.idyll.org/pipermail/cse491-spring-2013/2013-January/000030.html>`__,
`here
<http://lists.idyll.org/pipermail/cse491-spring-2013/2013-January/000031.html>`__,
and `here
<http://lists.idyll.org/pipermail/cse491-spring-2013/2013-January/000028.html>`__.

Some version control principles
-------------------------------

1. Commit often

Divide your work up into small discrete chunks, and every time you
complete a chunk, commit.  This is simply good practice.

In collaborative work, remember: the last person to merge has the most
work to do, so if you're working collaboratively, try to get complete
"chunks" of work (new features) committed at a high level of
granularity, so that other people have to do the work of merging.

2. Only add/commit files that aren't automatically generated.

For example, Python compiles .py files into .pyc files; don't commit
those to your repository!  (Also see .gitignore, in the root
directory; this will tell git which files it should ignore when you do
'git status'.)

3. Don't commit any unnecessary files or changes.

I use 'git status' and 'git diff' liberally to make sure that only
intentional changes get committed.  This should not include "whitespace"
changes, commented out code, etc.

4. Run your tests before committing, and again before pushing.

Never commit/communicate code that you *know* is broken, unless
you have a reason to do so.

New functionality in drinkz
---------------------------

What do the merges you merged last week actually do?

Use cases!!!
------------

Check out the README for drinkz:
 
   https://github.com/ctb/cse491-drinkz/blob/master/README.md

To guide development of new features, software developers often design
what *use cases*.  These are, at a high level, little stories about what
users or customers want to do.  For example,

**Brian** has a liquor cabinet and a bunch of drink recipes that use
various types and amounts of liquor.  He wants the 'drinkz' site to
output a shopping list for him based on a set of drink recipes he
selects.

This use case drives a number of design considerations for the site
database:

 1. The site has to be able to store Brian's drink inventory.
 2. The site has to be able to store Brian's recipe inventory.
 3. The site has to be able to correlate Brian's drink inventory with
    the recipe.

It also drives a number of user interface considerations, but we'll get
to those in the new weeks.

Brainstorming
~~~~~~~~~~~~~

Individually or in a group, brainstorm a bunch of use cases that
center around activies based on one or more liquor cabinets, and one
or more recipes.  Remember that "customers" in this case can also
include business-to-business customers like markets that want to advertise
on your site, offer discounts, etc.  Any way that you can make a buck ;).
(Ignore all privacy and ethical concerns for now.)

Prepare to present three use cases as a table.  They should be different
from the use cases presented by the other tables ;).

Minute Cards
~~~~~~~~~~~~

In the last 5 minutes of class, please fill out this `minute card survey <https://docs.google.com/spreadsheet/viewform?formkey=dHFMMmg5djBFMTFQV2paSlNtWG94X0E6MQ#gid=0>`__.
