Day 25 - Th, April 25, 2013
===========================

========================================================
Stuff I didn't teach, couldn't teach, or forgot to teach
========================================================

Cookies and logging in
======================

See https://github.com/ctb/cse491-webz/blob/cookies/app.py for code for
seting cookies.

Security
========

0. As a Web developer, how do you protect against guessing?

Answer: by not being dumb.

1. As a Web developer, how do you protect against eavesdropping?

Answer: HTTPS.

2. As a Web developer, how do you protect against server compromise?

Answer: you try not to write insecure servers.

3. How do you protect against client (browser-side) compromise?

Answer: you can't.

Scaling; latency; throughput
============================

How do you scale up to handle hundreds or thousands of concurrent sessions?

How do you minimize latency, the "turnaround time"?

How do you maximize throughput, the amount of "stuff" being delivered?

What do real Web developers use?
================================

All of the tech we used in the class is "real", including WSGI,
Jinja2, JSON and JSON-RPC, CSS, JQuery, SQLite, etc.  But people have
built layers on top of WSGI and SQL (in particular) to automate as much
of the manual stuff as possible.

Real Python Web developers use things like `Django <https://www.djangoproject.com/>`__ and `Pyramid <http://pyramid.readthedocs.org/en/latest/>`__.

Personally, I have always had a soft spot for `Quixote <http://quixote.ca/>`__,
which is a nice, simple, extensible Web framework.  To take a look, ::

   source env941/bin/activate.csh
   curl -O http://quixote.ca/releases/Quixote-2.7.tar.gz
   pip install Quixote-2.7.tar.gz
   tar xzf Quixote-2.7.tar.gz

   cd Quixote-2.7
   python quixote/server/simple_server.py  --port=8000

See the files quixote/demo/root.ptl and quixote/demo/extras.ptl for the
source for the examples.
