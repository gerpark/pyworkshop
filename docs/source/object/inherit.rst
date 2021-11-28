

.. index:: inherit, erben, Klasse, class

########
Vererben
########

.. Vorlage war j.tier51


Ein wichtiges Konzept bei OOP ist die Vererbung.

Bei der Vererbung erbt eine neue (spezialisierte) Klasse von 
einer (schon vorhandenen) Basisklasse alle Attribute und Methoden.
Beispielsweise könnte es zu einer Fahrzeugklasse als spezialisierte Klasse
eine Autoklasse oder ähnliches geben.


Klassendefinition
=================

Wir erstellen den Bauplan für eine Klasse `Vogel` und finden heraus,
dass wir die `Vogel-Klasse` genauso wie die `Tier-Klasse` verwenden können.

Die abgeleitete Klasse enthält den Namen der Basisklasse
in der Kopfzeile der Klassendefinition:

.. code:: python

    # Basisklasse
    class Tier():
        def __init__(self):
            print("Konstruktor Tier")
            self.futter = "alles"

        def sprich(self):
            print("Ich mag gerne", self.futter)

    # Spezialsierte Klasse
    #           ==>
    class Vogel(Tier):
        pass


    spatz = Vogel()
    spatz.sprich()


