==========
Homework 1
==========

Due by noon on Thursday, Jan 16th.  Reminder, per `the syllabus
<_static/cse491-spring2014-syllabus.pdf>`__ you may use The Google,
friends, family, etc. to complete the homework.

0. Sign up for `the class mailing list <http://lists.idyll.org/listinfo/cse491-spring-2014>`__.

1. Sign up for a github account (it's free!) at http://github.com/.
   (You can use whatever account name you want, but it will be public
   and may be connected to your real name by The Google, so 'luzer420'
   is probably a bad idea for your future.)

2. Go to `the cse491-serverz repository
   <https://github.com/ctb/cse491-serverz>`__ and fork it into your
   own github account; then, clone it into your own CSE cluster
   account on arctic and follow the instructions in README.txt to get
   'server.py' running.  (See :doc:`git` for clone instructions.
   Please feel free to use your own computer, too; just make sure
   you're using python2.7 and a recent version of git.)

   Once you have server.py running, modify the code to return an HTTP
   1.0 response, containing '200 OK' response line, a 'Content-type'
   of text/html, and a message body saying '<h1>Hello, world<h1> this
   is ctb's Web server.'  (Replace 'ctb' with your own NetID or github
   username.)

   For more information on HTTP, please see this link:

      http://www.jmarshall.com/easy/http/#structure

   especially 'Sample HTTP exchange'.

   Verify that when you point your Web browser at your network server,
   you see the message you wrote, with 'Hello, world' in bigger letters
   than the rest.  (The <h1> and </h1> should be invisible.)

   Once complete, commit your changes with a sensible commit message,
   and push them to your repository (again, see :doc:`git`).  **Make
   sure your changed code is present in your repository by visiting
   the Web site for your repository and viewing the code.  Deviation
   will not be tolerated.**

   OPTIONAL: immediately after the 'accept' call, put in a line
   'print c.recv(1000)'.  What does this do, and what is the format of the
   output?

3. Update ChangeLog with whatever it is you've changed; commit, push.
   (Yes, this is part of your homework.)

3. Fill out `this form
   <https://docs.google.com/forms/d/1y_OqqlM8Y98H8HoyiVUHCuz3HlbDECooT08rd5lIsbE/viewform>`__
   so that I know what repository is connected to what NetID!

----

Links:

* :doc:`git`
* `The socket module in Python <http://doughellmann.com/2010/09/pymotw-socket-network-communication.html>`__
