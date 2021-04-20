
.. index:: Variable, Name, Datentyp, Anweisung 

########################
Variablen und Datentypen
########################

Variablen gibt es wohl in den allermeisten Programmiersprachen,
auch wenn sie sich im Detail immer etwas unterscheiden.

Die Idee einer **Variable** ist es, einem Wert / einer Sache, einen selbstgewählten Namen 
zu geben. Der Wert kann im nachhinein geändert werden, es gibt also einen Variablennamen,
mit einem variablen Inhalt (=Wert), der über den sogenannten Variablennamen angesprochen wird.

Mit der folgenden Anweisung wird eine Variable erstellt, oder genauer gesagt,
d.h. sie wird im ersten Schritt definiert und ihr auch gleich ein ein Wert zugewiesen.

.. code:: python

    >>> zahl=5

Wir haben jetzt eine Variable mit dem Namen `zahl` und dem Inhalt `5`.
Um den Inhalt der Variablen zu überprüfen, geben wir den Namen an:

.. code:: python

    >>> zahl
    5

und wir ändern den Wert:

.. code:: python

    >>> zahl = 3 * (2 + 5)

das Entscheidende bei dieser Anweisung ist das Gleichheitszeichen,
zuerst wird der Ausdruck rechts vom **=** berechnet,
oder besser gesagt ausgewertet.
Das Ergebniss landet dann in der Variablen links vom Gleichheitszeichen.
Die Variable selbst wird entweder erstellt oder falls schon vorhanden,
weiterverwendet.

wenn wir zu dem Wert dieser Variablen etwas hinzuzählen wollen schreiben wir:

.. code:: python

    >>> zahl = zahl + 4
    >>> zahl
    25

die Variable mit dem Namen `zahl` hat jetzt den Inhalt 25.

Für den Namen einer Variablen gibt es bestimmte Regeln: er muss mit einem
Buchstaben beginnen, dann folgen Buchstaben und Zahlen und eventuell als einzig
erlaubtes Sonderzeichen ein Unterstrich (_).
Der erste Buchstabe ist vereinbarungsgemäss ein Kleinbuchstabe und zwischen 
Gross- oder Kleinbuchstaben wird unterschieden (=case sensitive).


.. _daten-typ:

Der Inhalt (=Wert) einer Variablen gehört immer einem bestimmten **Datentyp** an,
z.B. dem Typ der "Ganzen Zahlen", einer "Dezimal Zahl" oder einer Zeichenkette.
Diese Unterscheidung ist notwendig, weil mit den verschiedenen Datentypen jeweils 
nur bestimmte Dinge gemacht bzw. nicht gemacht werden können, wie wir ja schon
gesehen haben.

Die folgende Anweisung führt also wieder zu einem TypeError, d.h. eine Zahl kann nicht
durch einen String geteilt werden.

.. code:: python

    >>> zahl = zahl / "text"
    Traceback ...
    ...
    TypeError: unsupported operand type(s) for /: 'int' and 'str'


Aber eine Variable kann durchaus für einen anderen *Datentyp* verwendet werden:

.. code:: python

    >>> zahl = "Birne"


Bei unseren ersten Experimenten haben wir jetzt folgende *Datentypen* kennengelernt:


* Ganze Zahlen
    *int*
    
* Dezimal - oder Flieskommazahlen
    *float*

* Strings
    *str*

    Strings werden jeweils von einem einfachen (**\'**) oder doppelten Hochkomma (**\"**) begrenzt. Es ist egal welches
    der beiden Zeichen verwendet wird, es muss nur am Anfang und am Ende dasselbe sein.

Wir werden gleich sehen, wie der Datentyp einer Variablen ermittelt werden kann.
