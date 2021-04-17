
.. _oop-usage:

##############
Objekte nutzen
##############

Um also die Verwendung von Objekten auszuprobieren werden wir die
:ref:`Experten Version des Turtle Moduls<turtle-oop>`,  nutzen.

Es beginnt damit, dass wir ein Turtle Objekt erstellen:

.. code:: python

    >>> from turtle import *
    >>> joe = Turtle()


und können jetzt die Methoden aus der Klasse ``Turtle`` benutzen, um auf die Turtle Instanz einzuwirken.

.. code:: python

    >>> joe.color("blue")

Jetzt sollte es auch kein Problem sein, eine zweite Turtle zu erstellen,

.. code:: python

    >>> ola = Turtle()
    >>> ola.color("gold")


Die Eigenschaft, also in diesem Beispiel das Aussehen der Turtle Instanz, bleibt erhalten,
auch wenn sie von einer Funktion geändert wurde.

.. code:: python

    from turtle import *

    def init(trt):
        trt.shape("circle")

    jim = Turtle()
    jim.color("blue")
    init(jim)
    jim.forward(100)


Dass die Turtle innerhalb der Funktion geändert werden kann, hängt damit zusammen,
dass die Turtle Klasse ein :ref:`veränderlicher Datentyp  <py-mutable>` ist.





