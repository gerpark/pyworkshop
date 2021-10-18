
.. index:: bool

.. _bool-expression:

###########
Bedingungen
###########


In einem Computer Programm werden die einzelnen Befehlszeilen (Anweisungen)
eine nach der anderen ausgeführt, so wie es beispielsweise bei einem
Konzertprogramm wäre.

Wenn aber von diesem Ablauf abgewichen werden soll, muss es dafür
einen Grund geben, - ich nenne es mal eine *Bedingung*.

Wir probieren auf der :ref:`Python-Shell <python-shell>`:

.. code:: python

    >>> 5 > 2
    True

In der Informatik werden solche *Bedingungen* als **boolsche Ausdrücke**
bezeichnet. Das Ergebnis eines *Boolschen Ausdrucks* kann nur die 
Werte richtig (True) oder falsch (False) annehmen.

.. code:: python

    >>> 500 < 30
    False

Um zu prüfen, ob 2 Dinge den gleichen Wert haben, verwenden wir **==** , denn
das einfache Gleichheitszeichen hat ja die Bedeutung, dass einer
Variablen ein Wert zugewiesen wird.

.. code:: python

    >>> 30 == 30
    True

Das Ergebnis eines boolschen Ausdrucks lässt sich auch in einer Variablen speichern.

.. code:: python

    >>> vergleich = "Jacke" == "Hose"
    >>> vergleich
    False

``True`` und ``False`` sind Konstanten, sie können ganz normal verwendet werden,
so können wir sie z.B. einer Variablen zuweisen:

.. code:: python

    >>> stimmt = True


Und wie können wir den  :ref:`Datentyp <daten-typ>` der Variablen *stimmt* überprüfen?

Hier noch die häufigsten Vergleichs-Operatoren:

.. csv-table::
   :header: "Vergleichs-Operator", "Bedeutung"

   "<",              "kleiner"
   "<=",             "kleiner gleich "
   ">",              "größer"
   ">=",             "größer gleich "
   "==",             "gleich "
   "!=",             "ungleich "

Zu diesem Thema gibt es noch eine Menge zu sagen, aber um den
Ablauf eines Programms steuern zu können, sind wir jetzt schon 
gut vorbereitet.
