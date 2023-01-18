.. _bool1:

.. index:: Bedingte Anweisung, if, elif, else

##################
Bedingte Anweisung
##################

(ECDL: Bedingungsanweisung)

Wie wird jetzt der Ablauf des Programms gesteuert, d.h. wie kann festgelegt
werden, was als nächstes im Programmablauf ausgeführt werden soll?

Dafür gibt es die `If-Anweisung`: sie beginnt mit dem Schlüsselwort **if**,
dann folgt die :ref:`Bedingung <bool-expression>` (der *boolsche Ausdruck*) 
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
geeigneter Editor, wird ein :kbd:`<Tab>`-Zeichen durch 4 Leerzeichen ersetzen.


Die *if-Anweisung* kann mit **else** und **elif** (=else if) erweitert werden.
Sobald eine der Bedingungen erfüllt ist, werden die übrigen Bedingungen
nicht weiter geprüft.

Wir erstellen eine weitere Datei und schreiben: 

.. code:: python

    eingabe = input("Wie viele Tage hat der November? ")

Um prüfen zu können, ob dieser Monat mehr oder weniger Tage hat,
muss der String, den wir von der Funktion ``input`` zurückerhalten haben,
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

    # die Funktion print() steht wieder ganz links und wird damit in jedem Fall ausgeführt.
    print("Programm Ende")

Der Programmcode steht also immer ganz links, oder nach bestimmten Regeln
nach rechts eingerückt. 
