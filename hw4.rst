Homework #4
===========

Due Mar 27th at 11:59pm.  I'd suggest starting it BEFORE class on
Tuesday so that you can ask questions in class or at office hours.

(See :doc:`day11` for collaboration instructions.)

0. Cleanup.  I won't grade your homework if this isn't the case.

   (a) Merge with my master branch:

      https://github.com/ctb/cse491-drinkz.git

   such that 'git pull https://github.com/ctb/cse491-drinkz.git
   master' says "up to date", and make sure that your code includes
   everything through the end of HW 3.  This includes fixes for anything
   that was graded as 'broken' at the end of HW 3.
  
   (b) The default branch should be master, so, ::

      https://github.com/<USERNAME/cse491-drinkz/blob/master/<filename>

   should be what's on the main page when you go to ::

      https://github.com/<USERNAME>/cse491-drinkz

   and when you do a 'git clone' of your repository, you should have
   your latest code in default branch.

   (See https://github.com/blog/421-pick-your-default-branch.)

1. Refactor/fix.  10/100.

   (a) Put your unit conversion code in one file, consolidated into a single
       function.  Your tests shouldn't need to change.

   (b) Make sure all your tests pass.  This doesn't mean "delete them",
       this means "fix your code."

   Done.

2. Integrate a Web frontend to your drinkz code.  50/100.

   Copy or merge or otherwise integrate 'app.py' from cse491-webz
   (https://github.com/ctb/cse491-webz/blob/master/app.py) into the
   'drinkz/' directory, and then --

   (a) write a 'bin/' script called 'run-web' that starts up a Web
       application as at the bottom of the current app.py.

   (b) dynamically generate the Web pages from HW as part of 'app.py';
       for example, 'localhost:9786/' should show an index page that
       links to list of recipes, inventory, etc.

   (c) provide another link on your index page that connects to a page
       with a form on it that takes in some amount of liquid in a text
       box, and, when 'submit' is clicked, goes to a new Web page that
       shows the amount converted into ml.  Make sure that there are links
       back to the index page, too.

   (d) create a new file 'drinkz/test_app.py' that exercises the WSGI
       interface by

         - initializing a clean database with some recipe data;
	 - create a new SimpleApp object;
	 - calls the __call_ function on the SimpleApp object
	   with an 'environ' dictionary and a 'start_response' function
	   of your own creation.
	 - runs the code to generate the page that lists the recipes.
	 - checks that the right recipe data is on that generated page.

3. Save to/load from disk. 15/100.

   Merge really trivial file saving/loading.  More specifically, 

   (a) merge the code in
       https://github.com/ctb/cse491-drinkz/tree/hw4-save-load into
       your repo, alter the db.load_db and db.save_db functions to
       save and load recipes as well, and make sure that you can
       "properly" save and load bottle types, inventory, and recipes.

       See bin/save-load for example usage/script creation.

   (b) Create a script 'bin/make-test-database' that adds some data
       (recipes, etc.) and then saves the database into a filename
       provided on the command line.

   (c) Modify make-html.py and app.py (from #2) to load that data in.

   Note, it would be really nice if you made sure that you could
   create a file with (b) that I could then load with (c), and if it
   were really obvious what the filename should be.  Hint.  HINT.

4. Simple CSS/JavaScript. 15/100. (You'll need to get #2 working first.)

   Integrate some really CSS and JavaScript into your HTML.  Go check
   out `the latest commit to cse491-linkz
   <https://github.com/ctb/cse491-linkz/commit/f303f182016ae30d7b503645d8e709bf8a1e8362>`__
   and then:

   (a) Modify all your Web pages in #2 to contain the html, head, and body
       regions, as well as a title.  Make the title different on each page,
       please.

   (b) Modify all your Web pages in #2 to contain the <style> modification,
       and put an <h1> title on each page (which should now be red).
       The <h1> title should be different on each page.

   (c) On your index page, add the button to show an alert box with JavaScript.
       Make sure it works!

   Note: if you have other obvious CSS and JavaScript on your pages,
   e.g. because you've put together a style thing, you can skip this
   part of the homework.  Just make sure it's obvious, m'kay?

5. JSON-RPC. 15/100. (You'll need to get #2 working first.)

   (a) Change the JSON-RPC functionality in app.py to provide the following
       functions::

           convert_units_to_ml(amount) - given a str amount, returns ml
 	   get_recipe_names() - returns a list of all recipe names
           get_liquor_inventory() - returns a list of (mfg, liquor) tuples.

   (b) Create a new file 'drinkz/test_jsonrpc.py' that tests these functions
       through the 'app' interface.  That is, you should have at least three
       tests, each of which

          - initializes a clean database with some data (if needed)
	  - creates a new SimpleApp object
	  - calls the __call__ function on the SimpleApp object with
	    an 'environ' dictionary and a 'start_response' function
	    of your own creation.
	  - 'environ' should contain the information (PATH_INFO,
	    CONTENT_LENGTH, etc.) that makes the SimpleApp run the
	    relevant JSON-RPC accessible function (e.g. rpc_get_recipe_names).
	  - checks to make sure that the WSGI app returns the right answer.

       Under no circumstances should you directly call anything other than
       __call__ on the WSGI SimpleApp object, i.e. this should mimic closely
       a "normal" call from the WSGI server into the app object.

       Protip: use simplejson as in
       https://github.com/ctb/cse491-webz/blob/master/json-rpc-client.py
       and a StringIO object
       (http://docs.python.org/2/library/stringio.html) to set up
       environ['wsgi.input'] to pass in the JSON necessary to make the
       call.  You might also want to read
       http://en.wikipedia.org/wiki/JSON-RPC.

6. HTTP GET. 15/100. (You'll need to get #2 working first.)

   Write a standalone Python script that does an HTTP GET using the
   'socket' library in Python.  More specifically, read
   http://effbot.org/zone/socket-intro.htm and then write a standalone
   script called 'grab-page' (not in bin, or drinkz/, and not with a
   .py on the end, and not with an underscore) in the root directory
   of your repository.  This script should take two command line
   arguments, the hostname and the port for your running app.py
   server, and print out the results of submitting a GET request for
   '/' on the app.py server.

   This might be worthwhile reading, too, if you're confused or interested:

     http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol

7. Hand in your homework by tagging it as tag 'hw4'::

      git tag hw4
      git push origin hw4:hw4

   I strongly suggest that you make sure you can clone your repo into
   a new directory, check out 'hw4', and run all of your tests properly.
   You might want to double-check that everything above works, too...

   Note that it's fairly easy to delete tags, so you should try this early
   on and tell me if it doesn't work; then you can delete the first hw4
   tag and update it to whatever you want to hand in.
