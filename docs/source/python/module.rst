
.. index:: modul, module, dir, namen, namensraum, global

.. _py-module:

######
Module
######

Programme können auch aus mehreren Dateien bestehen.
Wenn wir in unserem (Haupt)Programm eine andere Datei nutzen wollen,
sprechen wir davon, dass wir ein Modul importieren.
Tatsächlich aber ist ein Modul nichts anderes als ein Python Script.
Ist euch die Bezeichnung in der IDLE aufgefallen, mit
der wir ein Programm starten, - `Run Module`!

Zuerst schauen wir uns an, wie ein Python Script importiert,
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

Die Syntax dafür enthält wieder, wie bei den Objekten, einen **Punkt**.
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

Wenn wir jetzt die Variante nehmen, die wir für das Turtle Module benutzt haben,
kann auf den Modulnamen verzichtet werden:

.. code:: python

    >>> from math import *
    >>> sqrt(16)

Aber `dir()` liefert jetzt ein ganz anderes Ergebnis, nämlich alle Namen der dort
zur Verfügung gestellten Funktionen.

.. code:: python

    >>> dir()

Diese große Zahl von `global gültigen Namen` ist mit einigen Nachteilen verbunden,
wie ich :ref:`hier <py-noglobal>` ja schon beschrieben habe.

Bei größeren Programmen oder Projekten sollte diese Variante vielleicht besser nicht zum
Einsatz kommen, obwohl sie natürlich einfach und praktisch ist.

Statt der eben beschriebenen Variante gibt es noch zwei andere Möglichkeiten,
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


Hier möchte ich nochmal auf die `Hilfe` hinweisen, denn sie kann erst verwendet
werden, sobald das Modul (in welcher Variante auch immer) importiert wurde.

.. code:: python

    >>> import os
    >>> help(os)
    >>> help(os.getcwd)


eigene Module nutzen
--------------------

Vielleicht einfach ein kurzes Beispiel, wir erstellen eine Datei 
mit dem Namen `tools.py` :

.. code:: python

    def plus19(wert):
        print("Funktion plus19")
        steuer = wert * 0.19
        return wert + steuer

    plus19(100)
    var = "Variable"

Und wir erstellen im selben Verzeichnis eine Datei mit
dem Namen `main.py`.

Jetzt können wir das Script tools.py einfach importieren,
dabei ist der Modulname einfach der Name der Datei ohne die Endung.

.. code:: python

    import tools
    print("Programm-Ende")

Siehe da, auch der Aufruf der Funktion wird ausgeführt.
Aber jetzt probieren wir, ob die Funktion und die Variable
auch genutzt werden können:

.. code:: python

    import tools
    result = plus19(50)
    print("->", result, "var=", var)
    print("Programm-Ende")


importiert oder nicht ?
-----------------------

In der Regel werden aus Modulen nur die Definitionen benötigt.  Beim Entwickeln und testen eines Moduls, 
ist es aber praktisch, wenn die jeweiligen Funktionen auch im selben Script aufgerufen werden können.

Dafür gibt es eine interne Variable `__name__` (2 Unterstriche), die wenn das Script importiert wurde,
den Namen des Moduls enthält. Falls das Script aber direkt aufgerufen wurde, sozusagen das Hauptprogramm
ist, enthält die Variable den Wert \'__main__\'.

Ein Script/Modul, dass diese Unterscheidung nutzen möchte, sieht dann so aus:

.. code:: python

    def plus19(wert):
        steuer = wert * 0.19
        return wert + steuer


    if __name__ == "__main__":
        result = plus19(100)

d.h. wenn das Script importiert wurde, wird die Funktion `plus19` nicht aufgerufen.
