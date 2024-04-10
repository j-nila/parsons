======================
Parsons Problem Webapp
======================
Parsons programming puzzles are a type of scaffolded program
construction tasks where the learner is given a set of code fragments,
blocks of a single or multiple lines of code,
and the task is to piece together a program from these.
Learners not only select and order but also indent code fragments.

They are challenging problems that reduces the cognitive load
and time spent for students.

This variant of Parsons programming puzzles is called two-dimensional (2D) Parsons problems.
In Python, code indentation has a semantic meaning, as an indented statement falls into
the surrounding control structure, which has lower indentation.
That is, code blocks are deﬁned by indentation instead of start and end symbols like curly braces.

(from *js-parsons*)

The use of Parsons puzzles is an evidence-based teaching practice.

Based on `js-parsons <https://js-parsons.github.io/>`_ and inspired by `Python Tutor <http://pythontutor.com>`_.

Example
-------
``find_max`` function:
http://parsons.problemsolving.io/puzzle/cbb39952d55a4be38f935c573a065f9f

Embedded in Jupyter Notebook (you need to run it locally):
https://github.com/ProblemSolvingIO/parsons/blob/master/demo/find-max.ipynb

References
----------
1. Parsons, D., & Haden, P. (2006, January).
   `Parson's programming puzzles: a fun and effective learning tool for first programming courses <http://crpit.com/confpapers/CRPITV52Parsons.pdf>`_.
   In Proceedings of the 8th Australasian Conference on Computing Education-Volume 52 (pp. 157-163).
   Australian Computer Society, Inc.
2. Ihantola, P., & Karavirta, V. (2011).
   `Two-dimensional parson’s puzzles: The concept, tools, and first observations <http://jite.org/documents/Vol10/JITEv10IIPp119-132Ihantola944.pdf>`_.
   Journal of Information Technology Education, 10, 119-132.
3. `CS Teaching Tips - Use Parson’s Puzzles to help students engage with a concept without writing code or experiencing frustrating syntax errors <http://csteachingtips.org/tip/use-parson%E2%80%99s-puzzles-help-students-engage-concept-without-writing-code-or-experiencing>`_.


Notes added by Jaya
===================

This repo uses pipenv for package management and virtual environment (i.e., replacing pip, requirements.txt, and venv). To test locally on a Windows system:

* install it! pip install pipenv (or pip3 install pipenv). You will need admin privileges on your terminal.
* update Python versions on Pipfile and Pipfile.lock as needed
* you may need to uninstall and reinstall virtualenv:
  * pip3 uninstall virtualenv -y
  * pip3 install -U virtualenv pipenv waitress
* pipenv install
* pipenv shell
* pipenv install -e .

* install sqlite tools bundle, download from https://sqlite.org/download.html. This site has a good lay-of-the-land tutorial that you can glance over https://www.sqlitetutorial.net/download-install-sqlite/
* run ``/c/sqlite/sqlite3.exe`` to open the cli. It will create a database called app.db. Otherwise, run ``/c/sqlite/sqlite3.exe app.db`` to connect to this database
* in the cli, run ``.read parsons/schema.sql`` to run the sql
* run ``.tables`` to ensure the ``program`` table is created, then ``.exit``

* make sure the database is created
* waitress-serve --listen=127.0.0.1:5000 --call parsons:create_app



