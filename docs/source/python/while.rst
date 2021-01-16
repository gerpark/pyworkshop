
.. _while:

.. index:: while

##################
Die while Schleife 
##################

Mit Schleifen können eine oder mehrere Anweisungen wiederholt werden.
In Python gibt es 2 Schleifentypen, wir beginnen mit der `while-Schleife`.

Bei einer Schleife geht es varallem darum die Zahl der Wiederholungen zu steuern.
Wir probieren das mit einem sehr einfachen Beispiel und lassen uns irgendetwas
vier mal am Bildschirm anzeigen (auch wenn das nicht gerade viel Sinn macht):

Am Anfang, dem Schleifenkopf, wird eine Bedingung geprüft, wie wir das schon
von der `if-Anweisung` kennen. Auch hier endet die Zeile mit einem Doppelpunkt
und die folgenden Anweisungen werden eingerückt.
Falls die Bedingung richtig war, wird der 'Schleifenkörper', also 
die eingerückten Anweisungen, ausgeführt.

Danach wird die Ausführung des Programms wieder oben im Schleifenkopf
fortgesetzt und die Bedingung erneut geprüft.
Die Schleife wird also solange durchlaufen, wie die Bedingung richtig ist.
Sobald die Bedingung falsch ist, ist auch die Schleife zu Ende
und das Programm wird unterhalb der Schleife fortgesetzt.






Wie wird jetzt der Ablauf des Programms gesteuert, d.h. wie kann festgelegt
werden, was als nächstes im Programmablauf ausgeführt werden soll.

Dazu gibt es die `If-Anweisung`, die mit dem Schlüsselwort **if**
beginnt, dann folgt die Bedingung (der *boolscher Ausdruck*)
und am Ende steht ein **Doppelpunkt**:

Wir erstellen eine Datei z.B. quiz.py und schreiben:

.. code:: python

    farbe = input("Was ist die beliebteste Farbe ? ")

    if farbe == "blau":
        print("Das ist richtig.")
        print("Es ist die Farbe", farbe, '.')

Falls die Bedingung richtig ist, werden alle Anweisungen (=Anweisungsblock) 
ausgeführt, die gleich weit eingerückt stehen.
In der Regel wird um 4 Leerzeichen eingerückt und ein für Python gut 
geeigneter Editor, wir ein "Tab"-Zeichen entsprechend ersetzen.

Die *if-Anweisung* kann mit **else** und **elif** (=else if) erweitert werden.
Sobald eine der Bedingungen erfüllt ist, werden die übrigen Bedingungen
nicht weiter geprüft.

Wir erstellen eine weiter Datei und schreiben: 

.. code:: python

    eingabe = input("Wieviel Tage hat der November? ")

Um prüfen zu können, ob dieser Monat mehr oder weniger Tage hat,
muss der String, den wir von der Funktion `input` zurückerhalten haben,
zuerst in eine Zahl gewandelt werden:

.. code:: python

    tage = int(eingabe)

und jetzt können wir die richtigen Hinweise geben:

.. code:: python

    if tage == 30:
        print("Richtig !")
    elif tage < 30:
        print("falsch, es sind mehr Tage.")
    else:
        print("falsch, es sind weniger Tage.")

die Funktion ``print`` steht wieder ganz links und wird damit in jedem Fall ausgeführt.

.. code:: python

    print("Programm Ende")
 
Der Programmcode steht also immer ganz links, oder nach bestimmten Regeln,
nach rechts eingerückt. 
