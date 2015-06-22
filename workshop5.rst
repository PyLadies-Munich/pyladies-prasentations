:title: Beginner's Workshop 5
:author: Alexander Loechel
:event: PyLadies Munich - Beginner's Workshop - Web Development
:keywords: Python, PyLadies, Workshop
:data-transition-duration: 1500
:css-all: css/workshop3.css
:auto-console: Yes


.. role:: slide-title-line1
    :class: line1

.. role:: slide-title-line2
    :class: line2

.. role:: slide-title-line3
    :class: line3

.. |br| raw:: html

    <br/>

.. |hr| raw:: html

    <hr/>

.. role:: python(code)
   :class: highlight code python
   :language: python

----

:id: title
:class: slide title-slide centered level-1
:data-x: 0
:data-y: 0

.. container:: centered

    Welcome to

    .. image:: images/pyladies-munich.png
        :height: 200px
        :class: centered

    Beginner's workshop 5

    **Web Development**

.. note::

    * Test Note



----

:id: recap-ws1
:class: slide level-1
:data-x: r-2500
:data-y: 1000

Recap Workshop 1-4
==================

* What is Python
* Setup & Tools
* Theory

----

:id: intro-pyramid
:class: slide level-1
:data-x: r+1000
:data-y: 1000

Web Development with Pyramid
============================

.. image:: images/pyramid-logo.png
    :width: 500px
    :class: centered tspacer bspacer

* http://trypyramid.com/
* http://www.pylonsproject.org/
* http://docs.pylonsproject.org/en/latest/docs/pyramid.html

----

:id: step1-setup
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Step 1: Setup environment
=========================

* Install Python 3.4
* Check Python:

.. code:: bash

    $ python3 -V
    Python 3.4.x

* Setup a Virtual Environment:

.. code:: bash

    $ pyvenv trypyramid
    $ cd trypyramid
    $ source bin/activate

* Install Pyramid Web Framework

.. code:: bash

    $ pip install pyramid


----

:id: step2-one-file-app
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Step 2: One File Pyramid App |br| Hello World
=============================================

Write this into a file `app.py`:

.. code:: python
    :number-lines:

    from wsgiref.simple_server import make_server
    from pyramid.config import Configurator
    from pyramid.response import Response

    def hello(request):
        return Response('Hello world!')

    if __name__ == '__main__':
        config = Configurator()
        config.add_route('hello_world', '/')
        config.add_view(hello, route_name='hello_world')
        app = config.make_wsgi_app()
        server = make_server('0.0.0.0', 8080, app)
        server.serve_forever()


http://trypyramid.com/

----


:id: step3-start-app
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Step 3: Start the app
=====================

.. code:: bash

    $ python app.py

Open http://127.0.0.1:8080/ in Browser

Output: **Hello World!**

----

:id: one-file-app
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Explanation of "One File Pyramid App"
=====================================

.. code:: python
    :number-lines:

    # framework imports
    from wsgiref.simple_server import make_server
    from pyramid.config import Configurator
    from pyramid.response import Response

    # hello view on route 'hello_world'
    def hello(request):
        return Response('Hello world!')

    # Base call on file
    if __name__ == '__main__':
        # Base Configuration
        config = Configurator()
        config.add_route('hello_world', '/')
        config.add_view(hello, route_name='hello_world')

        # Building and starting the app
        app = config.make_wsgi_app()
        server = make_server('0.0.0.0', 8080, app)
        server.serve_forever()


----

:id: excurses
:class: slide level-1
:data-x: r+1500
:data-y: 1000

Excurses
========

* Philosophy

  * Be lazy - Don't repeat yourself - Don't reinvent the wheel
  * Standing on the shoulders of giants
  * Test Driven Development & Documentation

* Tools

  * git
  * Python Eggs


----

:id: phil
:class: slide level-1
:data-x: r-500
:data-y: r+1000

Philosophy |br| three great virtues of a programmer
===================================================

    * **Laziness:** The quality that makes you go to great effort to reduce overall energy expenditure. It makes you write labor-saving programs that other people will find useful and document what you wrote so you don't have to answer so many questions about it.
    * **Impatience:** The anger you feel when the computer is being lazy. This makes you write programs that don't just react to your needs, but actually anticipate them. Or at least pretend to.
    * **Hubris:** The quality that makes you write (and maintain) programs that other people won't want to say bad things about.

    -- "Programming Perl", Larry Wall, 2nd Edition, O'Reilly, 1996


----

:id: dry
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Philosophy |br| DRY - Don't repeat yourself
===========================================

    **Don't repeat yourself**

    Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.

    -- Andy Hunt, Dave Thomas; The Pragmatic Programmer

DRY vs WET
----------

* **DRY:** Don't repeat yourself
* **WET:** write everything twice / we enjoy typing

It applies for one program and also to **best practice** of frameworks


----

:id: reinvent
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Philosophy |br| Don't reinvent the wheel
========================================

    To **reinvent the wheel** is to duplicate a basic method that has already previously been created or optimized by others.

* Why should I write and maintain code that others alrady have developed
* Using Best practices
* Standing on the shoulders of giants - *we don't have to reinvent the wheel, we use it*



----

:id: tests
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Test Driven Development & Documentation
=======================================

* Specification
* Testing of Specification
* Documentation



----

:id: git
:class: slide level-1
:data-x: r+1000
:data-y: 2000

Tool: GIT
=========

**git:** a distributed version control system

* git init
* git clone url
* git status
* git add
* git rm
* git commit
* git checkout
* git branch
* git push

----

:id: eggs
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Python Eggs/Wheels
==================

Eggs/Wheels are the Python Packaging Container




----

:id: scaffolds
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Scaffolds / Templates / Skeletons
=================================

Concept of Code Generation to bootstrap software components




----

:id: normal-pyramid-app
:class: slide level-1
:data-x: r+1000
:data-y: 1000

Starting a Pyramid App
======================

Steps:

#. Virtual Environment (pyvenv)
#. install pyramid
#. use scaffold to create base app / egg structure
#. check into VCS
#. start app in development mode and start developing


----

:id: venv
:class: slide level-1
:data-x: r+0
:data-y: r+1000


Virtual Environment
===================

.. code:: bash

    $ pyvenv base_app
    $ cd base_app
    $ source bin/activate


Install Pyramid
===============

.. code:: bash

    $ pip install pyramid


----

:id: bootstrap
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Bootstrap App with scaffold
===========================

.. code:: bash

    # generate app from scaffold
    # (for all avaliable scaffolds see: `pcreate --list`)
    $ pcreate -s starter base_app
    ...
    $ cd base_app

    # Check generated Code into VCS
    $ git init .
    $ git add setup.py README.txt base_app/
    $ git commit -m "initial version from scaffold"

    # build app
    $ python setup.py develop



----

:id: start
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Start App
=========


.. code:: bash

    $ pserve --reload development.ini
    Starting subprocess with file monitor
    Starting server in PID xxxx.
    serving on http://0.0.0.0:6543

open http://127.0.0.1:6543/ in Browser



----

:id: test_app
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Test App
========


.. code:: bash

    $ python setup.py test


----

:id: next-meeting
:class: slide centered level-1
:data-x: 0
:data-y: 6000

Next Workshop
=============

.. image:: images/pyladies-munich.png
    :height: 200px
    :class: centered

Thursday June 25th 2015 18:30

**Web Development** |br| **Templating / Schema / Forms**

----

:id: overview
:data-x: 0
:data-y: 3000
:data-scale: 8
