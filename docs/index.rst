
pyEffects: Monads for Python™
=============================


Handle your side-effects in Python like a boss.  Implements functional types for Either, Option, Try, and Future.

----------------

**Using Option**::

   >>> from pyeffects.Option import *
   >>> val = Some(5).map(lambda v: v * v)
   >>> val
   Some(25)
   >>> val.is_defined()
   True
   >>> val.get()
   25

**Using Try**::

   >>> from pyeffects.Try import *
   >>> val = Success(5).map(lambda v: v * v)
   >>> val
   Success(25)
   >>> val.is_success()
   True
   >>> val.get()
   25

**Using Either**::

   >>> from pyeffects.Either import *
   >>> val = Right(5).map(lambda v: v * v)
   >>> val
   Right(25)
   >>> val.is_right()
   True
   >>> val.get()
   25

**Using Future**::

   >>> from pyeffects.Future import *
   >>> val = Future.of(5).map(lambda v: v * v)
   >>> val
   Future(Success(25))
   >>> val.subscribe(lambda v: print(v))
   Success(25)
   >>> val.get().get()
   25