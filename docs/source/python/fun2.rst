
.. index:: Function, Procedure, Unterprogramm, def, parameter, argumente

####################
Funktionen erstellen
####################


Alle höheren Programmiersprachen haben die Möglichkeit Anweisungen so
zusammenzufassen, dass sie auch mehrfach ausgeführt werden können.
Hierfür gibt es unterschiedlichste Bezeichnungen wie z.B. Unterprogramm,
Prozedur oder im Falle von Python eben Funktion.

Auf diese Weise kann Programmcode (und Speicher) gespart werden
und das Programm wird zudem übersichtlicher.
Funktionen enthalten häufig Parameter, um die Funktion
flexibler einsetzen zu können.
Außerdem ist es häufig die Aufgabe einer Funktion ein bestimmtes 
Ergebnis zu ermitteln, das dann an die Stelle zurückgeliefert wird,
an der die Funktion aufgerufen wurde.

Ein einfaches Beispiel dafür ist die Funktion ``len``, die wir ja schon kennen:

.. code:: python

    anzahl = len("Januar")
    print("String enthält", anzahl, "Zeichen.")



Eine neue/eigene Funktionen muss zuerst `definiert` werden,
damit wird sozusagen ihr Bauplan erstellt. Der Name der Funktion beginnt mit einem Kleinbuchstaben und auch sonst
gelten dieselben Regeln, wie für die Namen von Variablen.

Der Funktionskopf beginnt mit dem Schlüsselwort **def** und endet mit Doppelpunkt.
Die darauf folgenden Anweisungen sind alle eingerückt (wie immer nach einem
Doppelpunkt) und bilden den Funktionskörper.

Wir beginnen schrittchenweise mit einem kleinen Beispiel, in dem wir den Flächeninhalt eines Kreises berechnen.

.. code:: python

    def flaeche():
        print("Den Flächeninhalt eines Kreises berechnen")


    # Die Definition der Funktion reicht aber noch nicht,
    # sie muss auch aufgerufen werden !
    flaeche()


Mit Hilfe von **Parametern**  kann eine Funktion für ähnliche Aufgaben
verwendet werden. `Parameter` sind Variablen, die im Funktionskopf festgelegt
werden und dann im Funktionskörper verwendet werden können.

Die beim Aufruf an die Funktion übergebenen Dinge, werden als Argumente bezeichnet.

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

        print("Der Flächeninhalt beträgt ", result, "qmm.")


Hier sind also `pi`, `resultat` und auch der Parameter `radius` Lokale Variablen.


Jetzt müssen wir nur noch das errechnete Ergebnis zurückliefern und das 
geschieht mit Hilfe der **return** Anweisung.
Dabei wird das was hinter dem `return` steht, an die Stelle zurückgeliefert
an der die Funktion aufgerufen wurde.

Gleichzeitig wird die Funktion, sobald eine Return-Anweisung erreicht wurde,
auch beendet.

.. code:: python

    def flaeche(radius):

        pi = 3.14
        result = pi * radius ** 2 

        return result


    ergebnis = flaeche(100)
    print("Der Flächeninhalt beträgt ", ergebnis, "qmm.")


Grundsätzlich muss die Return-Anweisung nicht nur am Ende, sondern kann
auch zusammen mit einer Bedingung irgendwo anders innerhalb der Funktion stehen. 
Das sollte aber besser vermieden werden, da das Programm dadurch leicht unübersichtlich wird.

Denn das **wichtigste Gesetz** beim Programmieren heißt:
Der Programmcode soll möglichst klar, gut lesbar
und verständlich sein! 
(so dass sich auch jemand anderes darin zurechtfinden kann)


Parameter und Argumente
-----------------------

Parameter sind die Variablen im Funktionskopf, die dann in der Funktion verwendet
werden können. **Argumente** sind die Werte bzw. Variablen, die beim Aufruf
an die Funktion übergeben werden.

Für die **Zuordnung** von den Argumenten zu den Parameter gibt es mehrere Möglichkeiten.
Standardmäßig geschieht das über die Reihenfolge, d.h. das erste Argument
wird an den ersten Parameter übergeben, und das zweite Argument landet im
zweiten Parameter u.s.w.
Die Zahl der Parameter und Argumente muss übereinstimmen.

Bei unserem Flächenbeispiel könnte der Aufruf dann so aussehen:

.. code:: python

    def flaeche(radius, einheit):
        ...
        ...

    ergebnis = flaeche(100, "cm")


Default Werte
-------------

Es gibt aber auch die Möglichkeit die Parameter mit einem Wert vorzubelegen,
d.h. dem Parameter einen **Defaultwert** zu geben.

Ich bleibe bei dem Beispiel mit der Flächenberechnung, auch wenn die Vorbelegung
des Radius nicht besonders sinnvoll ist.

.. code:: python

    def flaeche(radius=50):
        ...
        ...

    ergebnis = flaeche()

Dadurch dass der Parameter 'radius' im Funktionskopf schon einen Wert hat,
kann die Funktion jetzt mit oder ohne Argument aufgerufen werden.

Benannte Parameter
------------------

Die Zuordnung der Parameter zwischen der Definition und dem Aufruf einer Funktion
wurde bisher durch die Reihenfolge der Parameter bestimmt.

Stattdessen kann die Zuordnung aber auch so geschehen, dass beim Aufruf der Funktion
einfach die Namen der Parameter benutzt werden.
Das hat zudem den Vorteil, dass das Programm leichter zu lesen ist.

Die beiden Möglichkeiten lassen sich auch kombinieren, dann müssen aber zuerst
die Parameter kommen, die über die Reihenfolge zugeordnet werden.
