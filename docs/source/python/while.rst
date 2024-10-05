
.. _while:

.. index:: while, break, schleife, True, Endlosschleife

##################
Die while Schleife 
##################

In Python gibt es 2 Schleifentypen, wir beginnen mit der `while-Schleife`.

Mit Schleifen können eine oder mehrere Anweisungen wiederholt ausgeführt werden.
Dabei stellt sich zuerst die Frage, wie sich die Zahl der **Wiederholungen** steuern läßt.

Wir probieren es mit einem einfachen Beispiel und lassen uns irgendetwas
vier mal am Bildschirm anzeigen (auch wenn das nicht gerade viel Sinn macht):

Am Anfang, dem Schleifenkopf, wird eine Bedingung geprüft, wie wir das schon
von der `if-Anweisung` kennen. Auch hier endet die Zeile mit einem Doppelpunkt
und die folgenden Anweisungen werden eingerückt.
Falls die Bedingung richtig war, wird der `Schleifenkörper`, also die
eingerückten Anweisungen, ausgeführt.

Danach wird die Ausführung des Programms oben am Schleifenkopf
fortgesetzt und die Bedingung erneut geprüft.
Die Schleife wird solange durchlaufen, wie die Bedingung richtig ist.
Sobald die Bedingung falsch ist, ist auch die Schleife zu Ende
und das Programm wird unterhalb der Schleife fortgesetzt.

Wir verwenden jetzt eine Variable `zaehler` um steuern zu können, wie oft
die Schleife durchlaufen wird. Damit wir die Variable innerhalb der Schleife
benutzen können, müssen wir sie zuvor **initialisieren**, d.h. wir definieren sie
und geben ihr einen Anfangswert. Innerhalb der Schleife müssen wir 
die Variable jetzt nur noch entsprechend verändern.

.. code:: python

    zaehler = 1

    while zaehler <= 4:
        print("Zähler", zaehler)
        print("-------")
        # !!! die im Schleifenkopf verwendete Variable erhöhen (=inkrementieren).
        zaehler = zaehler + 1

    print("Programm Ende")


Falls versehentlich vergessen wurde, die Variable im Schleifenkörper zu verändern,
erhalten wir eine **Endlosschleife**.

Das Programm kann dann mit der Tastenkombination (:kbd:`Strg-C`) abgebrochen
werden. Dabei wird zuerst die Taste `'Strg'` gedrückt und gehalten,
und dann die Taste `'c'` dazu gedrückt (das muss evtl. mehrfach wiederholt werden).

`while-Schleifen` werden in der Regel dann verwendet, wenn zu Beginn noch nicht 
bekannt ist, wie oft die Schleife wiederholt werden soll.
Dafür gibt es das Schlüsselwort **break**, mit dem die Schleife jederzeit
beendet werden kann. Im Schleifenkopf darf die Bedingung dann `immer richtig` sein,
dass kann mit dem Schlüsselwort **True** erreicht werden.

Dazu ein Beispiel, in dem wir eine Einkaufsliste erstellen.

.. code:: python

    einkauf = ""
    print("Einkauf mit 'ende' beenden")

    while True:
        was = input("Was brauche ich noch?")

        # ==> die Schleife wird beendet
        if was == "ende":
            break

        # Wir merken uns den Einkauf in einem String
        einkauf = einkauf + " "  + was

    print("Einkauf:", einkauf)
