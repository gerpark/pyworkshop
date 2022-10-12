
.. index:: Namen, Objekte, mutable, veränderlich, unveränderlich, globale Variable, Garbage Collection, Lebensdauer

.. _oop-class:

##############
Eigene Klassen
##############

.. apr21: Vorlage war j.tierXX

Häufig ist es sinnvoll eigene Klassen/Datentypen zu erstellen,
bei Programmen mit einer GUI ist es fast unerlässlich.

Definition
==========

Die Klasse ist also der Bauplan, aus dem 'konkrete' Objekte (Instanzen)
erstellt werden. Klassennamen beginnen vereinbarungsgemäß
mit einem Groß-Buchstaben !

Wir beginnen mit der leeren Hülle einer **Klasse**:
(die Anweisung ``pass`` "macht nichts", es geht nur um die Syntax/Sprachregeln,
da ja nach dem ':' etwas Eingerücktes stehen muss.)

.. code:: python

    class Tier():
        pass

    # Der leere Bauplan genügt schon, um daraus Objekte erzeugen zu können.
    elch = Tier()

Methoden und Instanzvariablen
=============================

Jetzt wollen wir die Klasse mit etwas Inhalt füllen und erstellen eine Methode.
Eine **Methode** ist eine spezielle Art von Funktion,
die nur zusammen mit einem Objekt dieser Klasse verwendet werden kann.

Methoden haben in ihrer Parameterliste immer als erstes ein ``self`` stehen.
Beim Aufruf fehlt dieser Parameter, d.h. der Aufruf hat immer ein Argument
weniger als es Parameter in der Definition der Methode gibt.

.. code:: python

    class Tier():
        def sprich(self):
            print("Hallo")

    elch = Tier()
    elch.sprich()


Die Dinge, die bei jedem einzelnen Objekt einen eigenen Wert haben können,
werden in Attributen, oder besser **Instanzvariablen** gespeichert.

Zu erkennen sind Instanz-Variablen daran, dass sie mit einem ``self`` beginnen.
Sie haben den großen Vorteil, dass sie in allen anderen Methoden derselben Klasse
einfach weiterverwendet werden können.

.. code:: python

    class Tier():
        def setfutter(self, futter):
            # eine Instanzvariable definieren
            self.futter = futter

        def sprich(self):
            # die Instanzvariable kann hier verwendet werden !!!
            print("Ich mag", self.futter)

    elch = Tier()
    elch.setfutter("Kräuter")
    elch.sprich()

Konstruktor
===========

Allerdings gibt es bei diesem Programm noch ein Problem, denn
was passiert, wenn wir die Methode ``sprich()`` verwenden, bevor wir 
die Methode ``setfutter()`` aufgerufen haben?

Es gibt einen Fehler, denn die Instanzvariable ``self.futter`` wurde noch nicht definiert,
der entsprechende Programmcode wurde noch nicht durchlaufen.

Dass läßt sich aber leicht vermeiden, denn wie bei allen objektorientierten Sprachen,
gibt es die Möglichkeit ein Objekt zu initialisieren.
Ein solche Methode wird (in allen OO-Sprachen) als **Konstruktor** bezeichnet.

Wenn also in einer Klasse eine Methode mit dem dem festgelegten Namen ``__init__(...)`` 
definiert wurde (zwei Unterstriche), dann wird diese Methode einmal
beim Erstellen eines jeden Objekts ausgeführt.
Das ist der richtige Ort, um die Instanzvariablen zu initialisieren.
Ich würde also grundsätzlich empfehlen, alle Instanzvariablen schon im Konstruktor anzulegen.

.. code:: python

    class Tier():
        def __init__(self):
            print("Konstruktor Tier")
            # Instanzvariablen initialisieren
            self.futter = "alles"
            self.gewicht = None

        def
            ...

    elch = Tier()
    elch.sprich()


Das Schlüsselwort ``None``  bedeutet, dass der Wert noch nicht festgelegt ist.
Die Instanzvariable ``self.gewicht`` ist damit definiert und kann verwendet werden
ohne dass das Programm abstürzt.

Der Konstruktor kann auch **Parameter** haben und damit lässt sich sicherstellen,
dass z.B. für jedes Tier eine Tierart festgelegt werden muss (=mandatory).

.. code:: python

    class Tier():
        def __init__(self, art):
            print("Konstruktor Tier:", art)
            self.art = art
            self.futter = "alles"

        def sprich(self):
            print("Ich bin ein ", self.art, "und mag gerne", self.futter)


    tier = Tier("Elch")
    tier.sprich()


Namensraum
==========

Setter- und Getter-Methoden sind die klassische Art um 
den Wert von Instanzvariablen zu setzen oder zu ermitteln.
Natürlich könnten die Methodennamen auch anders heißen,
aber set...() und get...() haben sich eingebürgert.


.. code:: python

    class Tier():
        def __init__(self):
            self.futter = "alles"

        def setfutter(self, futter):
            self.futter = futter

        def getfutter(self):
            return self.futter


    elch = Tier()
    elch.setfutter("Kräuter")
    myfood = elch.getfutter()
    print("und mag", myfood)


In vielen `Objektorientierten Sprachen`, kann auf einzelne Objekte
nur über Methoden zugegriffen werden, in Python ist es aber auch
direkt über den Objektnamen möglich.
Das Objekt bildet dabei sozusagen einen eigenen **Namensraum**.

In diesem Beispiel könnte ich das Futter also auch direkt verwenden:

.. code:: python

    elch = Tier()
    elch.setfutter("Kräuter")
    print("Ich mag", elch.futter)


Methoden
========

Soll innerhalb einer Methode eine andere Methode der gleichen Klasse aufgerufen werden,
geschieht das in der üblichen Weise, links vom Punkt das Objekt und rechts die Methode:

.. code:: python

    class Tier():
        def __init__(self, art):
            self.art = art
            self.futter = "alles"

        def sprich(self):
            print("Ich bin ein ", self.art, "und mag gerne", self.futter)

        def setfutter(self,futter):
            self.futter = futter
            # ==>  Um eine Methode aus der eigenen Klasse aufzurufen,
            # wird vor den Namen der Methode das 'self' gestellt !
            self.sprich()

    tier = Tier("Elch")
    tier.sprich()
