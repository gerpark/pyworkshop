

.. index:: function, procedure

####################
Funktionen verwenden
####################

Sowie es bei den meisten Programmiersprachen Variablen gibt, so gibt es auch
immer Unterprogramme oder Prozeduren, die je nach Programmiersprache auch wieder
unterschiedlich bezeichnet werden.

In Python sprechen wir von Funktionen, und sie dienen dazu
bestimmte Dinge zu ermitteln oder zu bewirken.

Funktionen erkennen wir daran, dass sie mit einem Namen beginnen,
und dann etwas "Eingeklammertes" folgt.  Innerhalb der Klammeren stehen,
falls vorhanden, ein oder mehrere durch Kommas getrennte Argumente
(Das Komma hat unter Python immer die Bedeutung einer Aufzählung).

Wir probieren also wieder auf der :ref:`Python-Shell <python-shell>`:

.. code:: python

    >>> len("Sahne")
        5

Wir übergeben der Funktion ``len`` als Argument einen String und erhalten
als Ergebnis die Anzahl der Buchstaben.
Soll das Ergebnis in einer Variablen gespeichert werden, heißt es:

.. code:: python

    >>> buchstaben = len("Sahne")
    >>> buchstaben
        5

An die Funktion ``type`` können wir etwas beliebiges übergeben, das kann ein `fester Wert`
oder der Name einer `Variablen` sein. Als Ergebnis erhalten wir eine Information über den
Datentyp:

.. code:: python

    >>> type(12.46)
        <class 'float'>

Datentyp und 'class' sind dasselbe, und der Name des Datentyps ist gleichzeitig der Name der
`Umwandlungsfunktion` zu dem jeweiligen Datentyp.

.. code:: python

    >>> float("12.46")
        12.46

Hier habe ich einen String an die Funktion ``float`` übergeben. Um dass zu überprüfen, könnte man
sich das Ergebnis in einer Variablen merken und sich dann den Inhalt der Variablen mit der Funktion
``type`` anzeigen lassen.


Um Fließkommazahlen auf eine bestimmte Zahl nach dem Komma zu runden gibt es die Funktion ``round``,
bei der 2 Argument möglich sind.  Das erste Argument ist die eigentliche Zahl, im 2ten Argument
kann die gewünschte Zahl an Nachkommastellen angegeben werden: 

.. code:: python

    >>> round(12.46, 1)
        12.5

In Regel ist es so, dass für jede Funktion genau festgelegt ist, was und wie viele Argumenten übergeben 
werden können.  Bei der Funktion ``print`` können es aber, jeweils durch ein Komma getrennt, beliebig viele Argumente sein und dabei spielt es auch keine Rolle, welchen Datentyp sie haben.

.. code:: python

    >>> var = 12.46
    >>> print("var hat den Wert", var, "!")
        var hat den Wert 12.46 !

Hilfe zu den einzelnen Funktion kann mit der Funktion ``help`` erhalten werden, möglicherweise
sind die Erklärungen bei unserem aktuellen Kenntnisstand noch nicht immer ganz hilfreich.

.. code:: python

    >>> help(round)
