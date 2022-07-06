
.. index:: Namen, Objekte, mutable, veränderlich, unveränderlich, globale Variable, Garbage Collection, Lebensdauer

.. _oop-namen:

#######
Namen !
#######

.. apr21: Vorlage war bas61h und bas63h

Nachdem wir jetzt eine bessere Vorstellung von Objekten haben,
können wir **Variablen**, und was sie sind, ganz neu verstehen.

Wir haben ja schon gesehen, dass eine Variable, d.h. eine Variable mit demselben Namen,
für unterschiedliche Datentypen verwendet werden kann.

Das bedeutet, dass in Python, im Gegensatz zu vielen anderen
Programmiersprachen, die Variable selbst nichts über ihren Inhalt weiß, d.h.:

.. _py-vorsicht:

**eine Variable ist einfach nur ein Name für etwas !**

Genauer gesagt, enthält eine Variable einfach nur eine Referenz auf ein beliebiges Objekt.

Dieses Konzept macht die Sprache so handlich und erspart uns 
im Vergleich zu anderen Sprachen viel Tipp-Arbeit.
Aber es hat auch eine gefährliche Nebenwirkung:
Ein bestehender, also schon vergebener Name, kann versehentlich für etwas
anderes verwendet werden und verliert damit seine ursprünglichen Inhalt, z.B. :

.. code:: python

    joe = Turtle()
    ...

    # Später im Programm überschreiben wir 'joe' versehentlich 
    joe = 47

Wenn wir nun die Turtle weiterbenutzen wollen, haben wir ein Problem,
denn wir haben für die Turtle keinen gültigen Namen.
Am Bildschirm wird die Turtle zwar noch angezeigt, kann aber nicht
angesprochen und damit auch nicht mehr verwendet werden, nur noch ein Schatten ihrer selbst!


Außerdem sind in Python alle Namen gleichwertig, d.h. dass z.B. auch ein
Funktionsname auf diese Weise unbrauchbar gemacht werden kann.
Handelt es sich bei dem Namen um eine lokale Variable, ist die Auswirkung nur begrenzt,
aber bei :ref:`global gültigen Namen<py-noglobal>` ist wirklich **Vorsicht** geboten.

Ein weiterer Grund möglichst wenig oder keine **globalen Variablen** zu verwenden!


.. _py-mutable2:

------------------------
Veränderliche Datentypen
------------------------

In diesem Zusammenhang spielt noch etwas anderes eine wichtige Rolle,
die :ref:`veränderlichen und unveränderlichen Datentypen <py-mutable>`.

Die unveränderlichen Datentypen wie z.B Strings sind unproblematisch,
sie verhalten sich wie erwartet.

Aber bei den veränderlichen Datentypen gibt es **zwei Besonderheiten**.

Was geschieht wohl bei dem folgenden Programm Code:

.. code:: python

    >>> from turtle import *
    >>> t1 = Turtle()
    >>> t2 = t1

gibt es jetzt also ein oder zwei Turtles ?

.. code:: python

    >>> id(t1)
    >>> id(t2)

    # auch 'is' prüft ob es dasselbe Objekt ist
    >>> t1 is t2


Eine Zuweisung führt also zu **keiner Kopie**, also zu keiner 2ten Turtle,
sondern nur zu einem weiteren Namen für dasselbe Objekt. Auf diese Weise,
kann es also für ein und dasselbe Objekt mehrere Namen geben.

Bei der 2ten Besonderheit geht es um globale Variablen.
Zeigt nämlich eine globale Variable auf ein veränderliches Objekt, dann
lässt sich dieses Objekt von überall aus ändern, z.B. aus einer Funktion heraus.
Aber auch hier nochmal: möglichst wenig :ref:`globale Variablen <py-noglobal>` verwenden!

.. code:: python

    def foo():
        freunde.append("Jim")

    freunde = ["Mia", "Joe", "Iri"]
    foo()
    print(freunde)

---------
Kernsätze 
---------

.. index:: Garbage Collection, Lebensdauer

..  Garbage Collection, Lebensdauer

*	Variablen sind einfach nur Namen, die auf ein Objekt zeigen. 

*   die Lebensdauer eines Objekts ist so lange, wie es dafür einen gültigen Namen gibt.

*	'veränderliche Objekte' werden bei einer Zuweisung nicht kopiert, sondern bekommen einen weiteren Namen.

*   Hat ein Objekt keinen Namen mehr, wird es aus dem Speicher entfernt (=Garbage Collection) 


