
.. index:: turtle, objektorientiert 

.. _turtle-oop:

#######################
Turtle Objektorientiert
#######################

Die eigentliche, die Experten Version des Turtle Moduls ist :ref:`objektorientiert<oop-index>`, 
und enthält mehrere Klassen.

Das Turtle Modul hat die etwas unschöne Besonderheit, dass für viele
Methoden derselbe Name wie für die entsprechende Funktionen verwendet wird.
Das ist ziemlich irreführend, da eine Methode und eine Funktion 
aus `Programmier-Sicht` gar nichts miteinander zu tun haben.

!!! Also **Achtung**, falls wir den Objektnamen weglassen, also statt der Methode die Funktion
benutzen, bekommen wir eine zusätzliche, ich nenne sie mal die `Standard Turtle`.
Es ist sicherlich keine gute Idee, die `benannten Turtles` und die 
`Standard Turtle` in einem Programm zusammen zu benutzen.

Wir erstellen also eine Turtle Instanz,
und versuchen gleich mal, ob es eine Methode forward gibt:

.. code:: python

    from turtle import *

    joe = Turtle()
    joe.forward(100)

    
und probieren gleich weiter:

.. code:: python

    # und geben ihre Form ...
    joe.shape("turtle")

    # und eine Farbe
    joe.color("blue")


So ist die Farbe der Turtle natürlich eine Eigenschaft, aber im Fall der Turtle Software können
wir die Eigenschaften des jeweiligen Turtle Objekts nur mit Hilfe von Methoden ändern.
Es gibt aber Klassen, wie z.B. 'date', bei denen auf die Eigenschaften,
also die Attribute (=Instanzvariablen) direkt zugegriffen werden kann.
