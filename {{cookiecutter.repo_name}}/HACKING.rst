=======
HACKING
=======

Getting Started
---------------

Getting the code
~~~~~~~~~~~~~~~~

If you just want to look at the code, you can just clone the main repository:

::
    $ git clone git@github.com:{{ cookiecutter.github_username }}/{{ cookiecutter.repo_name }}.git

If you want to hack on {{ cookiecutter.repo_name }}, you should first 

Setting up a development environment
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Get Started!
------------
1. Fork_ the `{{ cookiecutter.repo_name }}` repo on GitHub.

2. Clone your fork locally::

    $ git clone git@github.com:your_name_here/{{ cookiecutter.repo_name }}.git

3. Create a branch for local development::

    $ git checkout -b name-of-your-bugfix-or-feature

Now you can make your changes locally.

4. When you're done making changes, check that your changes pass style and unit
   tests, including testing other Python versions with tox::

    $ tox

To get tox, just pip install it.

5. Commit your changes and push your branch to GitHub::

    $ git add .
    $ git commit -m "Your detailed description of your changes."
    $ git push origin name-of-your-bugfix-or-feature

6. Submit a pull request through the GitHub website.

.. _Fork: https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.repo_name }}/fork

Pull Request Guidelines
-----------------------

Before you submit a pull request, check that it meets these guidelines:

1. The pull request should include tests.
2. If the pull request adds functionality, the docs should be updated. Put
   your new functionality into a function with a docstring, and add the
   feature to the list in README.rst.
3. The pull request should work for Python 2.7 and 3.4.

Tips
----

To run a subset of tests::

	 $ py.test -s {{ cookiecutter.repo_name }}/tests/

Useful git aliases
~~~~~~~~~~~~~~~~~~
::

  # Update your local develop branch with the latest from the juju remote.
  # Then make sure to push that back up to your fork on github to keep
  # everything in sync.
  sync-upstream = "!f() { git checkout develop && git pull upstream develop && git push origin develop; }; f"

  # Rebase develop (trunk) into the current feature branch.
  sync-trunk = rebase develop

Hooks
~~~~~

Our test/lint targets are run by CI, but it can be hard to remember to run that
before proposing your branch.  If you would like to have those run before you
push your code to Github, you can add any of those targets to either the
`pre-commit` or `pre-push` (git 1.8.2+) hook, like:

::

  #!/bin/sh

  if test ! $NO_VERIFY ; then
      make lint
  fi

Add the above to the file `.git/hooks/pre-commit` or `.git/hooks/pre-push` then
run `chmod a+x .git/hooks/<the chosen hook>`.  `lint` is the simplest target
and will allow you to commit broken code so long as it passes lint.  `check` is
the most stringent option that requires passing tests in debug and prod as
well.  You can then use the command `NO_VERIFY=1 git commit` to commit or
`NO_VERIFY=1 git push origin <branch name>` to push a branch that will not pass
lint.  Running the command without the variable will cause lint to prevent the
command from succeeding if your branch does not lint.

Read more about hooks and how to install them `here
<http://www.git-scm.com/book/en/Customizing-Git-Git-Hooks>`_. Please note that
this will only work in environments where the app can build and run.  Since the
application will not run in OS X, you will have to run your push or commit from
vagrant instead.


