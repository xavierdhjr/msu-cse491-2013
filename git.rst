=====================================
Basic Instructions for Git and Github
=====================================

Links:

* `An interactive git tutorial, 'try git' <http://try.github.io/levels/1/challenges/1>`__
* `Pro Git (the book) <http://git-scm.com/book>`__
* `A tutorial introduction to git <http://git-scm.com/docs/gittutorial>`__
* `Top 10 Git tutorials for beginners <http://sixrevisions.com/resources/git-tutorials-beginners/>`__

----

1. Cloning a repository.
========================

Cloning a repository (from github or anywhere else) makes a local copy
of the contents of that repository.

To clone a repository, locate your HTTPS repository URL; it should look
something like this::

   https://github.com/ctb/cse491-serverz.git

where 'ctb' is your username instead, and 'cse491-serverz' is whatever
repository you're trying to clone locally.

note: it *must* end in .git.

Then do 'git clone $URL', replacing $URL with the repository URL.
This will create a directory named after the repository.  You can
rename this directory to whatever you want, move it around, etc; it's
entirely self-contained.

You can now edit files and do whatever you want in this repo.

2. Committing changes
=====================

Do a 'git status' to see what git thinks has been changed.

'git diff' will show the differences between the last commit and
the current changes.

The command::

   git commit -am "my changes"

will commit all the changes to the repository.  A 'git status' immediately
afterwards should show no changes.

'git log' will show you a list of commits.

3. Pushing changes to github
============================

The command::

   git push origin master

will push all changes in the master branch (the default one) to the
remote location called 'origin', which, by default, is wherever you
cloned things from.

You can use 'git remote' to add, remove, edit, and otherwise mess with your
various location aliases.
