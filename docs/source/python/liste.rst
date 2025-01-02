
.. _liste:

.. index:: list, liste, Index, aggregierter Datentyp, zusammengesetzte Datentypen, array, vector

#################
Der Datentyp list 
#################

Um die `for-Schleife` verstehen oder nutzen zu können, müssen wir zuerst
die Gruppe der `aggregierten Datentypen` kennen lernen. Diese Datentypen
sind z.B. auch als `Sammel-Datentypen` bekannt oder ich bezeichne sie gern
als `zusammengesetzte Datentypen`. 

Eine Variable kann auch aus mehreren Teilen bestehen, oder besser mehrere Elemente enthalten.
Jede Computersprache kennt etwas in dieser Art, wie immer, mit unterschiedlichen Bezeichnungen
und Ausprägungen (array, vector, ...).

In Python ist hierfür die **Liste** der prominenteste Vertreter, aber es gibt 
noch viele andere `zusammengesetzte Datentypen` wie Tuple, Dictionary,  ...  und was kennen wir schon?

Eine Liste besteht aus mehreren Elementen, ähnlich wie eine Fahrradkette aus
einzelnen Kettengliedern, oder eine Perlenkette aus aneinander gereihten Perlen besteht.
Allerdings hat eine Liste einen festen Anfang und die Elemente eine feste Reihenfolge.

Eine Liste wird mit eckigen Klammern erstellt (=initialisiert), die einzelnen Werte werden durch Kommas getrennt:

.. code:: python

    >>> zahlen = [5,9,20,3]

Die Anzahl der Elemente wird mit der Funktion ``len()`` ermittelt.

.. code:: python

    >>> len(zahlen)
    4

Auf die einzelnen Elemente wird über einen sogenannten **Index** zugegriffen, dafür werden erneut eckige Klammern benutzt.
Ein Index ist eine `Ganze Zahl`, die sich auf die Reihenfolge der Elemente bezieht.

Was wird wohl der Ergebnis sein ?

.. code:: python

    >>> zahlen[1]

Das erste Element in der Liste hat also den Index 0 !

Wir können auch den Wert/Inhalt der einzelnen Elemente ändern:

.. code:: python

    >>> zahlen[0] = 55
    >>> zahlen
        [55,9,20,3]


`Zusammengesetzte Datentypen` und Schleifen hängen eng miteinander zusammen:

.. code:: python

    namen = ['Ola','Jim','Iri']
    idx = 0
    while idx < len(namen):
        # print("Index", idx)

        vorname = namen[idx]
        print("Hallo", vorname)

        idx = idx + 1


Die Variable `vorname` verwende ich hier nur der Übersichtlichkeit halber, stattdessen hätten
wir auch direkt ``print("Hi", namen[idx])`` schreiben können.
