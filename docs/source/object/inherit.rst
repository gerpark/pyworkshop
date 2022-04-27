

.. index:: inherit, erben, Klasse, class

########
Vererben
########

.. Vorlage war j.tier51


Ein wichtiges Konzept bei OOP ist die Vererbung.

Bei der Vererbung erbt eine neue (spezialisierte) Klasse von 
einer (schon vorhandenen) Basisklasse alle Attribute und Methoden.
Beispielsweise könnte es zu einer `Fahrzeug`-klasse als spezialisierte Klasse
eine `Auto`-klasse oder ähnliches geben.


Klassendefinition
=================

Wir erstellen den Bauplan für eine Klasse ``Vogel`` und finden heraus,
dass wir die ``Vogel``-Klasse genauso wie die ``Tier``-Klasse verwenden können.

Die spezialisierte (=abgeleitete) Klasse enthält den Namen der Basisklasse
in der Kopfzeile der Klassendefinition:

.. code:: python

    # Basisklasse
    class Tier():
        def __init__(self):
            print("Konstruktor Tier")
            self.futter = "alles"

        def sprich(self):
            print("Ich mag gerne", self.futter)

    # spezialisierte Klasse
    class Vogel(Tier):
        pass


Nutzen
======

Die **abgeleitete Klasse** kann zum einen alle Instanzvariablen und Methoden
der Basisklasse nutzen:

.. code:: python

    spatz = Vogel()
    spatz.sprich()


und sie kann bestehende Attribute ändern und neue Eigenschaften (Variablen) und Fähigkeiten (Methoden) hinzufügen.


.. code:: python

    class Vogel(Tier):
        # eine zusätzliche Methode
        def flieg(self):
            print("Ich fliege !")


Vererben schafft Überblick und spart eine Menge Programmcode,
da der vorhandene Code ja einfach weiterverwendet werden kann.

überladene Methoden
===================

Die abgeleitete Klasse kann natürlich auch einen Konstruktor haben:

.. code:: python

    class Vogel(Tier):
        def __init__(self):
            print("Konstruktor Vogel")

    spatz = Vogel()
    spatz.sprich()

Aber wenn die Methode ``sprich()`` aufgerufen wird führt das zu einem Fehler,
denn jetzt wird nur noch der Konstruktor der Klasse Vogel aufgerufen.
Die Methode ``sprich()`` hätte aber die Instanzvariable ``self.futter`` benötigt, 
die in der Basisklasse initialisiert wird.
Der Konstruktor der Basisklasse wurde mit dem Konstruktor der abgeleiteten Klasse **überladen**.

Deshalb müssen wir den Konstruktor der Basisklasse explizit, also
selber aufrufen:

.. code:: python

    class Vogel(Tier):
        def __init__(self):
            Tier.__init__(self)
            print("Konstruktor Vogel")

    spatz = Vogel()
    spatz.sprich()

.. advanced14f/tier25

Die Syntax dazu kennen wir noch nicht, sie hat das folgende Schema:
Zu Anfang den Klassenname der Basisklasse, dann die ``init``- Methode, 
an die als (erster) Parameter ``self`` übergeben wird.

Dieses Prinzip des Überladens funktioniert auch für alle andere Methoden,
wenn sie denselben Namen haben.
