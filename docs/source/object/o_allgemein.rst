
.. _oop-allg:

#################
Objekte Allgemein
#################

Was ist nun ein Objekt?
-----------------------

Es ist nicht einfach sich diesem großen Thema zu nähern.
Grundsätzlich handelt es sich bei einem Objekt um ein etwas komplexeres Gebilde.
Das Wichtigste ist vielleicht, dass dort mehrere Variablen unter einem 
Dach zusammengefasst werden können. Außerdem befinden sich unter diesem Dach
noch Funktionen, die als Methoden bezeichnet werden, und die diese Variablen
auslesen oder auch ändern können.

Ein Objekt basiert, ähnlich wie eine Funktion, auf einem Bauplan der als
**Klasse** bezeichnet wird. Nachdem eine solche Klasse definiert ist,
können nach diesem Bauplan Objekte erstellt, (oder man sagt auch)
instanziiert werden. **Instanz** und Objekt sind dabei zwei Worte für dieselbe Sache.

Um ein Objekte erkennen zu können, gibt es zwei Funktionen, die normalerweise
gar nicht benutzt werden, aber zum Verständnis von Objekten nützlich sind.
Eine kennen wir schon, das ist die Funktion ``type``.  Vor ihr erhalten
wir den Datentyp und das ist nichts anderes als die Klasse.

Die andere Funktion heißt ``id``, und liefert zu jedem Objekt eine eindeutige
(Identifikations) -Nummer. An dieser Nummer kann erkannt werden, ob es sich
bei zwei sonst gleichen Objekten wirklich um dasselbe Objekt handelt.

In `Python` ist praktisch alles, was einen Namen hat auch ein Objekt,
z.B. eine Liste:

eine Liste initialisieren:

.. code:: python

    >>> liste = [90, 2, 7, 9]

und ermitteln den Datentyp:

.. code:: python

    >>> type(liste)
    <class 'list'>  

und lassen uns interessehalber die `Identifikationsnummer` anzeigen. Die Zahl selbst hat
für uns keine Bedeutung und wird auch immer unterschiedlich sein.

.. code:: python

    >>> id(liste)
    140096095297928


Wie werden Objekte verwendet ?
------------------------------

.. _oop-usage1:

Die übliche Art Objekte zu nutzen geschieht mit Hilfe von **Methoden**.
Funktionen und Methoden sind sich sehr ähnlich. Der Unterschied besteht
darin, dass eine Funktion "einfach so" aufgerufen wird, während eine
Methode immer nur zusammen mit einem Objekt verwendet werden kann.
Objekt und Methode sind dabei durch einen **Punkt** verbunden.

.. code:: python

    >>> liste.append(55)

**!!!** Links vom ``Punkt`` steht das ``Objekt``, rechts davon die ``Methode`` **!!!**


Eigenschaften und Fähigkeiten
-----------------------------

Etwas abstrakter gesehen, werden in einer Klasse die Eigenschaften
und Fähigkeiten für die daraus abgeleiteten Objekte festgelegt.
Die Fähigkeiten entsprechen den Methoden und die Eigenschaften 
werden in sogenannten **Instanzvariablen** gespeichert.
Mit Objekten lassen sich so viele Dinge der realen Welt häufig besser abbilden,
das gilt ganz besonders für Dinge oder Aufgaben im grafischen Bereich.

Wäre da nicht vielleicht die :ref:`Turtle <turtle-index>`
das beste Beispiel für ein Objekt, denn sie hat als Eigenschaften Farbe und Form
und kann sich drehen und laufen ?

Ja - natürlich ist die Turtle ein Objekt, es blieb
nur im Verborgenen. 
Denn wir haben bisher die Einstiegs Variante der Turtle Software benutzt,
aber jetzt gehts weiter mit der richtigen, **"der** 
:ref:`Experten <turtlexpert>`
**Version"** und die ist objektorientiert !
