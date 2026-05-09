.. _py-format:

.. index:: string, format, formatierung, formatanweisung 

###################
String Formatierung
###################

String Formatierung verwenden wir um  eine Ausgabe besser aussehen zu lassen.
So könnten z.B. Preise so ausgeben werden, dass sie ordentlich untereinander stehen.

Innerhalb des **Formatierungsstrings** werden die `geschweiften Klammern` durch die
entsprechenden Variableninhalte ersetzt und gegebenenfalls auch formatiert.

Dazu gibt es eine ausführlichere Variante, zu der es aber auch eine Kurzform gibt.
Beide Formen funktionieren aber nach demselben Prinzip. In der **Kurzform** wird ein `f` vor den String gestellt.

Im Beispiel mit der String-Methode format() steht die '0' innerhalb der geschweiften Klammern für das erste Argument.
Die Methode selbst kann, so wo wie wir es von ``print()`` kennen, beliebig viele Argumente enthalten.
In der Kurzform können die Variablen direkt innerhalb der geschweiften Klammern verwendet werden.

.. code:: python

   >>> preis = 4.65
   >>> artikel = "Brot"
   >>> out1 = "Das {0} kostet {1} €".format(artikel, preis)
   >>> print("Out1 : ", out1)

   # Die entsprechende Kurzform:
   >>> out2 = f"Das {artikel} kostet {preis} €"
   >>> print("Out2 : ", out2)

Hiermit haben wir aber noch nicht viel erreicht. 
Der eigentliche Trick sind die Formatierungshinweise,
die in den geschweiften Klammern auf den Doppelpunkt folgen.

Im folgenden Beispiel bedeutet der Formatierungshinweis ``5.1f``:

    * f --->  eine Fließkommazahl soll formatiert werden.

    * 5 --->  die Ausgabe soll 5 Zeichen lang sein.

    * 2 --->  die 2 in '5.2' bedeutet zwei Nachkommastellen.

.. code:: python

   >>> out = "{0} mit einer {0:5.2f} Nachkommastelle".format(4.6666)
   >>> print(out)


Die Datentypen haben die Bezeichnungen:  d = ganze Zahl, f = Fließkomma, s = String

Hier noch einige Beispiele:

.. code:: python

    >>> out = "Ein {0:20s} Wort".format("langes")

    #  Links- und rechtsbündig mit < und >
    >>> out = "Ein {0:>20s} Wort".format("langes")
    >>> out = "Zahlen 'sind {0:7d} rechtsbündig'"


Zu diesem Thema gäbe es noch sehr viel zu sagen, aber entscheidende Dinge sind schon mal
angesprochen, einfach ausprobieren!

Unter `diesem Link <https://www.python-kurs.eu/python3_formatierte_ausgabe.php>`_,
gibt es viel Information zu diesem Thema, eher zu viel (z.B. die %-Syntax aus Python2 Zeiten),
der wichtige Abschnitt für uns heißt "Der pythonische Weg: Die String-Methode" .

Noch mehr 'schwere Kost' auf Englisch bietet die Python-Hilfe:

.. code:: python

    >>> help('FORMATTING')

Zur Ausgabe mit ``print()`` oder auch bei der Ausgabe in eine Datei gibt es noch
wichtige Sonderzeichen, die mit einem Backslash (\\) beginnen.
Dies sind vor allem die Zeichen für den Zeilenumbruch (\\n) und für den Tabulator (\\t).

.. code:: python

    >>> print('Hallo\n')
    >>> print('\tHallo\n')

