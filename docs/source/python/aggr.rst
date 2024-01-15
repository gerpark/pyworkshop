
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
Beim String sind es die Hochkommas, bei der Liste die ``eckigen Klammern``:

.. code:: python

    >>> string = 'Dies ist ein String'
    >>> liste  = [5, 4, 12] 

Neu ist der Datentyp `Tuple`, der an den Klammern zu erkennen ist:

.. code:: python

    >>> tup = (7, 2, 16)

Zuletzt das `Dictionary`, es wird mit gescheifte Klammern initialisiert.
Hier werden die Elemente nicht über einen `Index`,
sondern über einen `Schlüssel` angesprochen.

.. code:: python

    >>> dic = {'jan':31, 'apr':30}

Allen diesen Datentypen ist gemeinsam, dass sie zusammen mit einer for-Schleife verwendet werden können.
Bei den sequentiellen Datentypen wird dabei über die einzelnen Elemente iteriert, bei
dem Dictionary über eine Liste der Schlüssel.

Liste
-----

Die :ref:`Liste <liste>` haben wir schon zuvor besprochen, sie ist ein :ref:`veränderlicher Datentyp <py-mutable>`.

Wenn eine Liste aber veränderlich ist muß es auch möglich sein, ihr weitere Elemente zuzufügen.
Dabei stoßen wir spätestens auf die Syntax, die bei der 
:ref:`ObjektOrientierung<oop-usage1>` verwendet wird, den `'Punkt'`.

Das passiert mit der Methode ``append()``, die am Ende einer bestehende Liste ein neues Element anfügt.

.. code:: python

    >>> liste = ["A", "B", "C"]
    >>> liste.append("D")
    >>> len(liste)
    4


String
------

Auch der String ist ein Sammel-Datentyp, so können wir einen String mit einer For-Schleife
in seine Teile zerlegen oder auf die einzelnen Zeichen über 'eckige Klammern' zugreifen.

Zu Strings gibt es eine ganze Reihe von Methoden, zwei davon möchte ich kurz vorstellen:
mit ``split()`` erhalte ich aus einem String eine Liste. Ohne Parameter ist das Trennzeichen
ein `Leerzeichen`, ansonsten kann das Trennzeichen im ersten Parameter mitgegeben werden.

Die zweite Methode ist ``strip()`` und entfernt sogenannte `white spaces` (Leerzeichen,Tabularen, Zeilenende)
am Anfang und Ende eines Strings.

Wenn Text angezeigt oder in eine Datei geschrieben wird, soll die Ausgabe
häufig etwas in Form gebracht werden. Das Sprachkonstrukt dafür sieht auf den ersten Blick etwas
verwirrend aus, das Thema heißt :ref:`String-Formatierung <py-format>`.

Eine weitere sehr praktische Technik möchte ich zusammen mit den Strings erwähnen, obwohl sie auch für die anderen `sequentielle Datentypen`
gilt, das sogenannte `Slicing`. Hiermit können mit Hilfe einer einfachen Syntax Teilbereiche eines Strings
ermittelt werden (In anderen Sprachen wären dafür Funktionen mit Namen wie 'substring' notwendig).

Ich zeige hier nur ein kurzes Beispiel:

.. code:: python

    >>> txt = 'Hausboot'
    >>> s[1:4]
    'aus'

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


Das einzelne Element erhalten wir mit Hilfe des `Schlüssels`:

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


Häufig ist der Schlüssel ein String, aber es kann auch eine anderer unveränderlicher Datentyp sein.
