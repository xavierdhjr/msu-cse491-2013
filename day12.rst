Day 12 -- Th, Feb 14th, 2013
============================

Rough schedule for today, summary:

 - review classes in Python, below
 - read about refactoring, below
 - read and work through HTML example, below (optional)
 - read hw3 carefully and ask questions!
 - work on examples and HW; ask questions; run about, scream and shout
 - minute cards

Classes and objects in Python
-----------------------------

Classes can be defined like so::

   class MyClass(object):
      def __init__(self, ...):
         ...

      def method1(self, ...):
         ...

and then instantiated like so::

   x = MyClass(...) # <-- __init__ arguments; no self needed.

Instantiating a class creates an empty object and then runs
__init__ on it.  You call methods on objects like so::

   x.method1(...)      # no self needed; it's passed in explicitly.

Note that the method1 call, above, is identical to::

   MyClass.method1(x, ...)

where 'x' must be an object of type MyClass.

Objects are, in essence, namespaces with behavior: that is, they contain
other objects (self.x, self.y, self.z, etc.) and behavior on them, in the
form of methods.  See cse491-numberz/series_iter/series.py for a really
simple example of this.

See `tutorialspoint
<http://www.tutorialspoint.com/python/python_classes_objects.htm>`__
for more info, or use the Google.

Refactoring
-----------

Refactoring is a really valuable buzzword to know.

Refactoring is the art of making code nicer (more modular, better
organized, etc.) *without* changing functionality.  Most students
think it's a waste of time because they only work on one homework at a
time; they're wrong.  If you consistently refactor your code to be
cleaner, more modular, and better tested, then over time your underlying
project will get much easier to modify and extend without fear.

Automated tests are a really valuable component of this.

In fact, one of the most important uses of tests is to support
refactoring -- when refactoring, you should only *add* tests to
test newly factored out bits of functionality, and never change
existing tests or remove them (unless you remove a function,
but then you should refactor the test so it still tests the
same underlying functionality).

For an example of refactoring, see: :doc:`day12-refactoring`

Basis HTML output and linking - discussion and exercise
-------------------------------------------------------

The 10-second introduction to HTML: HTML, which is how most Web pages
are formatted, consists of display instructions inside of angle
brackets, e.g.

  <b>Make this text bold</b>, and leave this text not bold.

If you put that in a file named 'bold.html' and opened it in a Web
browser, you would see the first bit bold and the second bit not bold.
The tags <b> and </b> would not be visible.  If you forget to "close"
the <b> tag with </b>, then all of the text would be bold.

Let's try it out.

Go grab github.com/ctb/cse491-linkz, clone it, and run 'python
make-html.py'.  Now open html/index.html in a Web browser (see below
for instructions on working remotely on the CSE cluster) and click
around.

Now, go into make-html.py and read through it, and then:

 1. Create a new file 'link.html' that contains 'Hello, world' in bold.

 2. At the bottom of table.html, add a link to ../index.html to go
    back "up" in the site hierarchy.  Note the connection between the
    directory structure and URLs.

 3. Fix the output of 'catastrophe.html' by closing the h3 tags
    correctly, and then link catastrophe.html into the bottom of
    index.html as 'check out the catastrophe!'

Could people post HTML tutorials that they found useful, please?  Either
in the comments on this page, or to the mailing list?

Posting Web pages on your CSE account
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If you have a CSE account and are working remotely on the CSE
machines, something like the following should work to post HTML pages
at www.cse.msu.edu/~username.  (Also read:
http://www.cse.msu.edu/facility/howto/mywebpage/) ::

   python make-html.py
   mkdir ~/web
   chmod a+rx ~/web

   rm -fr ~/web/cse491-linkz
   cp -r html ~/web/cse491-linkz
   chmod -R a+rx ~/web/cse491-linkz

You can then update this with your HTML diretory by doing::

   rm -fr ~/web/cse491-linkz
   cp -r html ~/web/cse491-linkz
   chmod -R a+rx ~/web/cse491-linkz

Homework 3 - readme
-------------------

Read through :doc:`hw3`; note that there are several branches to merge
for various bits of the homework. You can do this all at once
(recommended) or do it as you implement the functionality.

Especially check out the test format I used on the hw3-recipe-tests
branch in `test_recipes.py
<https://github.com/ctb/cse491-drinkz/blob/hw3-recipe-tests/drinkz/test_recipes.py>`__,
and read about `test fixtures
<http://en.wikipedia.org/wiki/Test_fixture#Software>`__ to understand
the `setUp and tearDown functionality in hw3-recipe-tests
<https://github.com/ctb/cse491-drinkz/blob/hw3-recipe-tests/drinkz/test_recipes.py#L9>`__.

Minute Cards
~~~~~~~~~~~~

In the last 5 minutes of class, please fill out this `minute card survey <https://docs.google.com/spreadsheet/viewform?formkey=dHFMMmg5djBFMTFQV2paSlNtWG94X0E6MQ#gid=0>`__.

