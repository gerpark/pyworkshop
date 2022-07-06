
.. _aggr:

.. index:: list, tuple, dictionary, dict, assoziative, array

######################
Aggregierte Datentypen
######################

Es gibt eine ganze Reihe von Zusammengesetzten- oder Sammel-Datentypen.

Gemeinsam ist ihnen, dass auf die einzelnen Elemente mit
`Eckigen Klammern` zugegriffen wird und die Anzahl der Elemente
mit der Funktion ``len()`` ermittelt werden kann.

Auch das Schlüsselwort ``in`` kann bei allen zusammengesetzten Datentypen
verwendet werden und liefert ein ``True`` oder ``False`` zurück, z.B:

.. code:: python

    >>> 'o' in 'wort'
    True


Der Datentyp wird bei den vier gebräuchlichsten Datentypen
durch die Begrenzungszeichen beim Initialisieren festgelegt.

.. code:: python

    >>> string = 'Dies ist ein String'
    >>> liste  = [5, 4, 12] 

Neu ist der Datentyp `Tuple`:

.. code:: python

    >>> tup = (7, 2, 16)

String, Liste und Tuple sind `sequentielle Datentypen`, d.h. die Elemente stehen in einer festen
Reihenfolge und werden über einen `Index` angesprochen.
Hier können auch Teilbereiche ermittelt werden, diese Technik heißt `Slicing`:

.. code:: python

    >>> s = 'Frühling'
    >>> s[4:7]
    'lin'

Zuletzt das `Dictionary`, hier werden die Elemente nicht über einen `Index`,
sondern über einen `Schlüssel` angesprochen.
Für die Initialisierung werden gescheifte Klammern verwendet.

.. code:: python

    >>> dic = {'jan':31, 'apr':30}


Allen diesen Datentypen ist gemeinsam, dass sie zusammen mit der for-Schleife verwendet werden können.
Bei den sequentielle Datentypen wird dabei über die einzelnen Elemente iteriert, bei
dem Dictionary über eine Liste der Schlüssel.

Liste
-----

Die **Liste** haben wir schon :ref:`zuvor <liste>` besprochen, sie ist ein :ref:`veränderlicher Datentyp <py-mutable>`.

Tuple
-----

Das Tuple ist wie z.B. der String ein :ref:`unveränderlicher Datentyp <py-mutable>`,
d.h. einmal initialisiert kann das Tuple, im Gegensatz zu einer Liste, nicht mehr geändert werden.

In manchen Situation soll z.B. deutlich gemacht werden, dass der Inhalt der Variablen
nicht geändert werden kann, darüber hinaus benötigt ein Tuple weniger Speicherplatz
und ist auch sonst schneller zu verarbeiten.

Werden bei einer Aufzählung (Kommas) die Begrenzungszeichen weggelassen, 
so führt das auch zu einem **Tuple**:

.. code:: python

    >>> tup = 5, 9
    >>> type(tup)
    <class 'tuple'>


Aber es ist auch folgende Zuweisung möglich:

.. code:: python

    >>> var1, var2 = 5, 9

Hier wird also der Wert ``5`` der Variablen ``var1``, und ``9`` der Variablen ``var2`` zugewiesen.
Dies wird häufig zusammen mit der Return-Anweisung verwendet, wenn mehrere Werte
zurückgeliefert werden sollen.

Darüber gibt es noch die Technik des Entpackens, dabei steht das Tuple
auf der rechten Seite und die Werte werden entsprechend verteilt:

.. code:: python

    >>> tup = ("na", "sowas")
    >>> var1, var2, var3 = ("na", "so", "etwas")


Hierbei müssen allerdings die Zahl der Elemente im Tuple und 
Zahl der Variablen übereinstimmen, sonst gibt es einen Laufzeitfehler,
d.h. eine Exception wird geworfen.

Dictionary
----------

Die Datentypen `string`, `list` und `tuple` sind `"sequentielle Datentypen"`,
d.h. die Elemente stehen in einer festen Reihenfolge hintereinander und werden über einen
(numerischen) Index angesprochen.

Das Dictionary dagegen ist ein `"assoziatives array"`, die Elemente sind ungeordnet und
die einzelnen Werte werden über einen **Schlüssel (key)** angesprochen.
Wie die Liste ist das Dictionary ein :ref:`veränderlicher Datentyp <py-mutable>`.

Wir beginnen mit einem leeren **Dictionary**:

.. code:: python

    >>> monate = {}

und können jetzt einzelne Werte zufügen, und kontrollieren das Ergebnis wie immer,
in dem wir einfach den Namen des Dictionarys eingeben:

.. code:: python

    >>> monate["Januar"] = 31
    >>> monate["April"]  = 30
    >>> monate["Juli"]   = 31

    >>> monate
    {'Januar': 31, 'April': 30, 'Juli': 31}


Das einzelne Element erhalten wir wieder mit Hilfe des `Schlüssels`:

.. code:: python

    >>> monate["April"]
    30     

Diese Art des Zugriffs ist sehr schnell, d.h. wir würden das Ergebnis
auch bei einem großen Dictionary sofort erhalten.

Wenn wir auf ein Element zurückgreifen, dass es gar nicht gibt,
führt das zu einem Fehler. Dies lässt sich leicht vermeiden, indem wir zuerst prüfen, 
ob es den jeweiligen `Schlüssel` überhaupt gibt:

.. code:: python

    >>> monat = input("Bitte den Monat eingeben: ")
    >>> if monat in monate:
            print("Der Monat", monat, "hat", monate[monat], "Tage.")
        else:
            print("Fehler: über den Monat <", monat, "> ist nichts gekannt!")
