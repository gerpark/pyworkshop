
.. index:: modul, module, dir, namen, namensraum, global

.. _py-module:

######
Module
######

Programme können auch aus mehreren Dateien bestehen.
Wenn wir in unserem (Haupt)Programm eine andere Datei nutzen wollen,
sprechen wir davon, dass wir ein Modul importieren.
Tatsächlich aber ist ein Modul nichts anderes als ein Python Script.
Ist euch der Menütext in der IDLE aufgefallen, mit
dem wir ein Programm starten, - `Run Module`!

Wir schauen uns als erstes an, wie ein Python-Script importiert,
also verfügbar gemacht werden kann.

Module importieren
------------------

Um Python Scripte zu importieren gibt es mehrere Möglichkeiten oder Varianten.
Das hat unter anderem das Ziel, die Zahl der `global gültigen Namen` möglichst klein zu halten,
wie ich etwas später zeigen werde.

.. Die Namen für Variablen, Funktionen, etc. sind in Python gleichwertig  !

Wenn wir z.B. die Quadratwurzel einer Zahl berechnen wollen, benötigen wir dazu
das Modul `math`.  Die wichtigste Variante zum Importieren heißt dann einfach:

.. code:: python

    >>> import math

Danach stehen uns eine Reihe von Mathematischen Funktionen zur Verfügung, wie z.B `sqrt()`.

.. code:: python

    >>> math.sqrt(16)
    4

Die Syntax dafür enthält wieder, wie bei den :ref:`Objekten<oop-usage1>`, einen **Punkt**.
Hier steht links vom Punkt der Modulname und rechts davon die Funktion.
Links von einem Punkt steht also immer entweder der Name eines Moduls
oder der Name eines Objekts.

Damit bildet der Name des Moduls einen Namensraum, der die Namen
der darin enthaltenen Funktionen enthält.

In diesem Zusammenhang gibt es eine hilfreiche Funktion `dir()`.

.. code:: python

    >>> dir()

Ohne Parameter bekommen wir eine Liste der aktuell verwendeten Namen angezeigt,
das sind einige voreingestelle Dinge, aber eben auch `math`, den Namen
unseres eben importierten Moduls.

Wenn wir jetzt die Variante nehmen, die wir bisher für das Turtle Modul benutzt haben,
kann auf den Modulnamen verzichtet werden:

.. code:: python

    >>> from math import *
    >>> sqrt(16)

Aber `dir()` liefert jetzt ein ganz anderes Ergebnis, nämlich alle Namen der dort
zur Verfügung gestellten Funktionen.

.. code:: python

    >>> dir()

Diese große Zahl von `global gültigen Namen` ist mit einigen Nachteilen verbunden,
wie ich :ref:`hier <py-noglobal>` beschrieben habe.

Bei größeren Programmen oder Projekten sollte diese Variante besser nicht zum
Einsatz kommen, obwohl sie natürlich einfach und praktisch ist.

Statt der eben beschriebenen Variante gibt es noch zwei weitere Möglichkeiten,
(ohne den Globale Namensraum mehr als nötig aufzublasen),
so kann für den Modulnamen eine Abkürzung vergeben werden:

.. code:: python

    >>> import math as ma
    >>> ma.sqrt(16)

oder es wird genau aufgeführt, was im Einzelnen verwendet werden soll,
in diesem Beispiel also die Funktionen `sqrt` und `sin`.

.. code:: python

    >>> from math import sqrt, sin
    >>> sqrt(16)


Hier noch ein Hinweis zur `Hilfe`, die Funktion help() funktioniert nur für Dinge,
die zuvor importiert wurden.

.. code:: python

    >>> import os
    >>> help(os)
    >>> help(os.getcwd)


.. _module-use:

Eigene Module nutzen
--------------------

Module sind also einfach Python-Scripte,
d.h. jedes Python-Script lässt sich auch importieren.

Hier ein kleines Beispiel, wir erstellen
eine Datei/Script mit dem Namen ``tools.py``:

.. code:: python

    var = "Eine Variable"

    def plus19(wert):
        print("Funktion plus19")
        steuer = wert * 0.19
        return wert + steuer

    result = plus19(100)

Und wir erstellen im selben Verzeichnis eine Datei/Script mit
beispielsweise dem Namen ``foo.py``.

In  ``foo.py`` können wir das Script ``tools.py`` einfach importieren,
indem wir den Namen der Datei ohne Endung verwenden.
(Modulnamen sollen übrigens grundsätzlich klein geschrieben werden !)

.. code:: python

    import tools
    print("Programm-Ende")

Wenn wir dieses Script ausführen, stellen wir fest, dass nicht
nur die Definition von plus19() importiert wurde, sondern
dass plus19() auch gleich ausgeführt wurde.

Zur Sicherheit probieren wir noch, ob die Funktion und die Variable
auch wirklich genutzt werden können:

.. code:: python

    import tools
    result = plus19(50)
    print("->", result, "var=", var)
    print("Programm-Ende")


Importiert oder nicht ?
-----------------------

In der Regel werden aus einem Modul nur die Definitionen benötigt. Beim Entwickeln und Testen eines Moduls,
ist es aber praktisch, wenn die jeweiligen Funktionen auch im selben Script aufgerufen werden können.

Hierfür gibt es eine interne Variable `__name__` (je 2 Unterstriche), die wenn das Script importiert wurde,
den Namen des Moduls enthält. Falls das Script aber direkt aufgerufen wurde, sozusagen das Hauptprogramm
ist, enthält die Variable stattdessen den Wert \'__main__\'.

Ein Script/Modul, dass diese Unterscheidung nutzen möchte, sieht dann so aus:

.. code:: python

    def plus19(wert):
        steuer = wert * 0.19
        return wert + steuer


    if __name__ == "__main__":
        result = plus19(100)

d.h. wenn das Script/Modul importiert wurde, wird die Funktion `plus19` nicht aufgerufen.
