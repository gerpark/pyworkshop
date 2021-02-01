
.. index:: function, procedure

####################
Funktionen erstellen
####################


Alle höheren Programmiersprachen haben die Möglichkeit Anweisungen so
zusammenzufassen, dass sie auch mehrfach ausgeführt werden können.
Auch hierfür gibt es unterschiedlichste Namen wie z.B. Unterprogramm,
Prozedur oder im Falle von Python eben Funktion.

Auf diese Weise kann Programmcode (und Speicher) gespart werden
und das Programm wird auch übersichtlicher.
Funktionen enthalten häufig Parameter, damit kann die Funktion
flexibler eingesetzt werden.
Ausserdem ist es häufig die Aufgabe einer Funktion ein bestimmtes 
Ergebnis zu ermitteln, das dann an die Stelle zurückgeliefert wird,
an der die Funktion aufgerufen wurde.

Ein einfaches Beispiel dafür ist die Funktion 'len', die wir ja schon kennen:

.. code:: python

    anzahl = len("Januar")
    print("String enthält", anzahl, "Zeichen.")



Eine neue/eigene Funktionen muss zuerst `definiert` werden,
damit wird sozusagen ihr Bauplan erstellt. Der Name der Funktion beginnt mit einem Kleinbuchstaben und auch sonst
gelten dieselben Regeln, wie für die Namen von Variablen.

Der Funktionskopf beginnt mit dem Schlüsselwort **def** und endet mit Doppelpunkt.
Die folgenden Anweisungen sind alle eingerückt (wie immer nach einem
Doppelpunkt) und bilden den Funktionskörper.

Wir beginnen schrittchenweise mit einem kleinen Beispiel, in dem wir den Flächeninhalt
eines Kreises berechnen.

.. code:: python

    def flaeche():
        print("Den Flächeninhalt eines Kreises berechnen")


    # Die Definition der Funktion reicht aber noch nicht,
    # sie muss auch aufgerufen werden !
    flaeche()


Mit Hilfe von **Parametern**  kann eine Funktion für ähnliche Aufgaben
verwendet werden. `Parameter` sind Variablen, die im Funktionskopf festgelegt
werden und dann im Funktionskörper verwendet werden können.

Die beim Aufruf an die Funktion übergebenen Werte, werden als Argumente bezeichnet.

.. code:: python

    def flaeche(radius):
        print("Den Flächeninhalt eines Kreises mit Radius,", radius, "mm berechnen.")

    # die Funktion mit dem Argument 100 aufrufen

    flaeche(100)


Innerhalb der Funktion lassen sich auch Variablen definieren,
die aber nur innerhalb der Funktion benutzt werden können
(gültig sind). Sie werden als **lokale Variablen** bezeichnet.

.. code:: python

    def flaeche(radius):

        pi = 3.14

        result = pi * radius ** 2 

        print("Die Flächeninhalt beträgt ", result, "qmm.")


Hier sind also `pi`, `resultat` und auch der Parameter `radius` Lokale Variablen.


Jetzt müssen wir nur noch das errechnete Ergebnis zurückliefern und das 
geschieht mit Hilfe der **return** Anweisung.
Dabei wird das was hinter dem `return` steht, an der Stelle angeliefert
an der die Funktion aufgerufen wurde.

Gleichzeitig wird die Funktion, sobald eine return Anweisung erreicht wurde,
auch beendet.

.. code:: python

    def flaeche(radius):

        pi = 3.14
        result = pi * radius ** 2 

        return result


    ergebnis = flaeche(100)
    print("Die Flächeninhalt beträgt ", ergebnis, "qmm.")


Grundsätzlich muss die return Anweisung nicht nur am Ende, sondern kann
auch zusammen mit einer Bedingung irgendwo anders innerhalb der Funktion stehen. 
Das sollte aber besser vermieden werden, da das Programm dadurch leicht unübersichtlich wird.

Denn das **wichtigste Gesetz** beim Programmieren heißt:
Der Programmcode soll möglichst klar, gut lesbar
und verständlich sein! 
(so dass sich auch jemand anderes darin zurechtfinden kann)
