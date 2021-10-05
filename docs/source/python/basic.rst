
.. index:: rechnen, Dezimalzahlen, Fehlermeldung

##################
Der Taschenrechner
##################



Als erstes versuchen wir auf der :ref:`Kommandozeile <cmd-line>` etwas zu rechnen,
denn - ist es ein Wunder - die Programmiersprache Python kann auch rechnen !

.. code:: python

    >>> 5+7
    12

Wie könnte es heißen, wenn wir "1,2 * 3" rechnen wollen:

.. code:: python

    >>> 1,2 * 3
    (1,6)

??? - das Komma ist auf Englisch ein Punkt, also:

.. code:: python

    >>> 1.2 * 3
    3.5999999999999996

Dezimalzahlen, die auch als Fließkommazahlen bezeichnet werden,
sind in Programmiersprachen immer ungenau. Das Ergebnis schöner aussehen
zu lassen, ist nicht schwer, wie wir schon bald sehen werden.

Aber jetzt geben wir mal was anderes ein:

.. code:: python

    >>> hallo
        Traceback (most recent call last):
          File "<pyshell#3>", line 1, in <module>
            hallo
        NameError: name 'hallo' is not defined

Dies führt zu einer Fehlermeldung, das ist nicht weiter schlimm,
es ist nur eine Erklärung, was schief gelaufen ist.
Das wichtigste steht unten, nämlich dass der Name `hallo`
nicht definiert ist.

Wenn wir nur einen Text ausgeben wollen, dann muss der 
Text in Hochkommas eingeschlossen werden:

.. code:: python

    >>> "hallo"
    hallo

Was wohl dabei rauskommt?

.. code:: python

    >>> "hallo" * 3
    hallohallohallo

oho - und hierbei:

.. code:: python

    >>> "hallo" + 5
        ...
        TypeError: must be str, not int

Diese Fehlermeldung deutet auf das Thema `Datentypen`, und besagt,
dass hier ein falscher Datentyp verwendet wurde.
"hallo" ist eine Zeichenkette, ein `String`  (=str) und hierzu
könnte zwar ein weiterer String, aber keine `ganze Zahl` (=int) addiert werden.
Wie müsste es heißen ?
