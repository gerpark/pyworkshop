
.. _for:

.. index:: Schleife, for

##################
Die for Schleife 
##################

Jetzt aber zum 2ten Schleifentyp:
Die `for-Schleife` ist eine besondere Stärke von Python, kurz und effektiv,
kein Wunder dass sie ständig und überall benutzt wird.
Sie wird meist in Kombination mit `Zusammengesetzte Datentypen` verwendet und
ist dann eigentlich nur eine Kurzform der `while-Schleife`.

Ein kleines Beispiel mit einer `while-Schleife`:

.. code:: python

    namen = ['Ola','Jim','Iri']

    idx = 0
    while idx < len(namen):
        vorname = namen[idx]
        print("Hallo", vorname)
        idx = idx + 1

Die `for-Schleife` leistet genau dasselbe, nur viel eleganter und viel kürzer:

.. code:: python

    namen = ['Ola','Jim','Iri']
     
    for vorname in namen:
        print("Hallo", vorname)

Rechts vom Schlüsselwort **in** steht die Liste, die benutzt werden soll. Die Schleife wird
also so häufig durchlaufen, wie es Elemente in der Liste gibt.
Rechts vom Schlüsselwort **for** steht der Name einer Variablen, die bei jedem Schleifendurchlauf
den Wert des jeweiligen Elements erhält.

So kann mit der `for-Schleife` auch eine neue Variable erstellt werden, bisher
ging das nur mit einer Zuweisung, also mit Hilfe von einem Gleichheitszeichen.

Der Datentyp rechts vom Schüsselwort `in` muss nicht unbedingt eine Liste sein, es kann auch
ein anderer (iterierbarer) Datentyp sein, also etwas das aus mehreren Elementen besteht.
Die Funktion ``range()`` liefert so etwas 'iterierbares', in diesem Beispiel die Werte 0,1,2,3 und 4.
Auf diese Art können wir also ganz leicht eine **Zählschleife** erstellen.

.. code:: python

    for zahl in range(5):
        print("Zahl", zahl)

