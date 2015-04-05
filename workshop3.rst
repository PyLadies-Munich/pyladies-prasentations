:title: Beginner's Workshop 3
:author: Alexander Loechel
:event: PyLadies Munich - Beginner's Workshop
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

    Beginner's workshop 3

    **Theory** of **data flow** and **data control**

.. note::

    * Test Note



----

:id: recap-ws1
:class: slide level-1
:data-x: r-3500
:data-y: 1000

Recap Workshop 1
================

* Introduction
* What is Python

  * About the Language
  * History and Background

* Basic Philosophy - The Zen of Python
* Tools and Setup

  * Python Interpreter
  * Virtual Environments
  * pip & easy_install

* Hello World example

----

:id: syslab
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Syllabus of the planned curriculum
==================================

* Workshop 1 - **Introduction, Setup and first steps** (February 26th 2015)
* Workshop 2 - **Theory of data types and data structures** |br|
  For beginners, March 12th 2015)

* Workshop 3 - **Theory of data flow / data contol** |br|
  (For beginners, April 1nd 2015)

* Workshop 4 - **Repeating Workshop** |br|
  (For beginners and language changer, April 16th 2015)

* Workshop 5 and ongoing: |br|
  More specialized on your preferred direction:
  web-development and data


.. class:: centered tspacer

    *up to 8-12 Workshops*

----

:id: recap-ws2-1
:class: slide level-1
:data-x: r+1000
:data-y: 1000

Recap Workshop 2
================

Theory of data types and data structures
----------------------------------------

* Paradigms |br| *all programming languages have the same power (turing complete)*
* Data types - *Duck Typing*

  .. pull-quote::

    Smart data structures and dumb code works a lot better |br| than the other way around

    -- Eric Raymond

  * Objects - *Everything is an object in Python*
  * *Primitive data types*
  * Composite types


----

:id: recap-ws2-2
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Recap Workshop 2
================

Theory of data types and data structures
----------------------------------------

* Module / Module Hierarchy
* Compiler and interpreter
* Unix Philosophies


    * Write programs that do one thing and do it well.
    * Write programs to work together.
    * Write programs to handle text streams, |br| because that is a universal interface.

    -- Doug McIlroy

----

:id: recap-ws2-3
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Recap Workshop 2
================

Theory of data types and data structures
----------------------------------------

* Standard type Hierarchy and :python:`type()`-Function
* Mutable and Immutable Types

* Numbers

  * Integrals (*Booleans & Integers*) - Boolean Operations
  * Real (*floating point*)
  * Complex


----

:id: recap-ws2-4
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Recap Workshop 2
================

Theory of data types and data structures
----------------------------------------

* Sequences, Sets and Mappings

  * Tuples (:python:`(value1, value2, ...)`)
  * Strings (*Unicode (Python2* :python:`u''` *) & Byte (Python3* :python:`b''` *)* )
  * Lists (:python:`[]`)
  * Set & Frozenset
  * Dict (:python:`{ 'key': 'value', ... }`)

* Callable types

  * Classes
  * functions and methods

* Modules


----

:id: intro-python
:class: slide level-1
:data-x: r+1000
:data-y: 1000


Introduction to Python
======================

.. code:: python
    :number-lines:

    # Python 3: Fibonacci series up to n
    def fib(n):
        a, b = 0, 1
        while a < n:
            print(a, end=' ')
            a, b = b, a+b
        print()
    fib(1000)

Important parts we see
----------------------

* method definition  :python:`def fib(n)`
* variables :python:`a, b`
* discrete values :python:`0, 1, 1000`
* data flow / control element for a loop: :python:`while`
* method calls :python:`print()` & :python:`fib()`


----


:id: base-1
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Basic Elements of |br| data flow / data control
===============================================

* Simple statements

  * Expression statements |br|

    * :python:`True`, :python:`'text'`,
    * *boolean / comparison operations* :python:`a == b`
    * List comprehension :python:`[x.id for x in my_list]`
    * *objects or procedures*

  * Assignment statements (:python:`x = y`)

  * Augmented Assignment Statements (:python:`text += 'some text'`)

  * *special simple statements with a meaning in context* |br| (:python:`pass`, :python:`return`, :python:`yield`,
    :python:`raise`, :python:`break`, :python:`continue`, :python:`import`)


----


:id: base-2
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Basic Elements of |br| data flow / data control
===============================================


* Compound statements

  * Control flow statements

    * conditional switches (:python:`if ... elif ... else`)
    * loops (:python:`while` & :python:`for ... in ...:`)
      |br| *important here:* **iterators** & **generators**

  * Exception handling (:python:`try: ... except: ... finally: ...`)
  * Context Managers (:python:`with`)

  * Definition statements (:python:`class`,  :python:`def`) and calls :python:`call()`



----


:id: class-def
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Definition Statements and Calls
===============================

.. pull-quote::

  everything in Python is an Object

.. code:: python
    :number-lines:

    import modul

    class MyClass(inheritance1, inheritance2):

        def __init__(self, param):
            self._param = param

        def get_param(self):
            return self._param

        def set_param(self, param):
            pass

    my_obj = MyClass('value')
    print(my_obj.get_param())


----

:id: ifthen
:class: slide level-1
:data-x: r+1000
:data-y: 1000

Conditional Switch
==================

Classic if then else

.. code:: python

    if a == 0:
        expression
    elif a > 0 and a < 10:
        expression
    elif a < 0:
        expression
    else:
        expression

Base
----

Truth evaluation of values and Operations (Boolean, Comparison, Shifting, ... Operations)

Test via :python:`bool(expression)`
...................................



----

:id: bools1
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Boolean Operations
==================

.. code:: python

    >>> True and True
    True
    >>> True or False
    True
    >>> not False
    True


----

:id: bools2
:class: slide level-1
:data-x: r+0
:data-y: r+1000


Comparison Expressions
======================

.. code:: python

    >>> 1 > 0
    True
    >>> ' text '.strip() == 'text'
    True
    >>> result = None
    >>> result is not None
    False
    >>> 11 in range(5)
    False

----

:id: bools3
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Truth Value of expressions
==========================

.. code:: python

    >>> # An empty sequence has a Truth-Value of False
    >>> # A sequence with content has a Truth-Value of True
    >>> my_list = []
    >>> if not my_list:
    >>>    print('List is empty')
    'List is empty'

    >>> # NoneType has a Truth-Value of False
    >>> return_value = function_call()
    >>> # if return_value is None
    >>> if return_value:
    >>>     return_value.start()


----

:id: loops
:class: slide level-1
:data-x: r+1000
:data-y: 1000

Simple Loops
============

Simple **for** loop
-------------------

.. code:: python

    for index in list:
        print(index)

Simple **while** loop
---------------------

.. code:: python

    index = 1
    while index <= 100:
        print(index)
        index += 1

----

:id: aloops1
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Advanced **for** Loop
=====================

.. code:: python

    >>> for fruit in ['banana', 'apple', 'orange']:
    >>>     print(fruit)
    >>> else:
    >>>     print('no more fruits available.')
    banana
    apple
    orange
    no more fruits available.

----

:id: aloops2
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Advanced **for** Loop & Context Manager
=======================================

.. code:: python
    :number-lines:

    with open(file, 'r')  as input_file:
        line_number = 0
        for line in input_file.readlines():
            line_number += 1
            if line == 'Appendix':
                break
            elif line.startswith('#'):
                # Line starts with comment sign: ignore and continue
                continue
            print(line)
        else:
            print('No Appendix found')
        print('We have read {lines}'.format(lines=line_number))


* :python:`with` indicates a Context Manager - means that specific operations are automatically applied on exit of context
  here the file is closed

* :python:`break` quites the loop before the normal ending condition of the loop is reached

* :python:`continue` indicates that all following expressions in the loop is not executed and next loop circle starts

* :python:`else` is only executed if no break statement has quite the loop


----

:id: iter-gen
:class: slide level-1
:data-x: r+1000
:data-y: 1000

Iterator
========

* you can only loop (:python:`for ... in ... :`) over a sequence-like object
* sequences implements a __next__() method
* everything that behaves like a sequence and implements a __next__() method is iterable


----

:id: gen
:class: slide level-1
:data-x: r+0
:data-y: r+1000

Generator
=========

.. code:: python
    :number-lines:

    import time

    def my_takt_generator():
        num = 1
        while True:
            yield num
            num = num % 4 + 1

    takt = my_takt_generator()

    counter = 0
    for takt_elem in takt:
        print(takt_elem)
        counter += 1
        if counter >= 60:
            break
        time.sleep(1)

counts 1 2 3 4 1 2 3 4 ...

----

:id: async
:class: slide level-1
:data-x: r+0
:data-y: r+1000

AsyncIO Generators
==================



.. code:: python
    :number-lines:

    class DistanceSensor(Sensor):

        @asyncio.coroutine
        def get_distance(self):
            while true:
                distance = yield from self._messure_distance()
                if distance < 100:
                    print('Warning Distance too low')



----

:id: exceptions
:class: slide level-1
:data-x: r+1000
:data-y: 1000

Exceptions & Exception Handling
===============================

.. code:: python
    :number-lines:

    def div(value1, value2):
        if value2 == 0:
            raise ZeroDivisionError
        return value1 / value2

    try:
        value1, value2 = 10, 0
        print(div(value1, value2))
    except Error as e:
        print('something went totally wrong')
        print(e.message)









----

:id: try
:class: slide level-1
:data-x: r+1000
:data-y: 1000

All following explanations and examples are practical session

please open your |br| **IPython Notebook** http://localhost:8888/


----

:id: next-meeting
:class: slide centered level-1
:data-x: 0
:data-y: 5000

Next Workshop
=============

.. image:: images/pyladies-munich.png
    :height: 200px
    :class: centered

Thursday April 23th 2015 18:30 ???

**Repeating Workshop - Exercises**

----

:id: overview
:data-x: 0
:data-y: 2500
:data-scale: 8
