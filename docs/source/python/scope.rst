
.. index:: global, local, lokal, globale Variable, lokale Variable, Geltungsbereich, Scope, Konstante

.. _py-scope1:

#######################
Scope / Geltungsbereich
#######################

.. apr21: Vorlage war bas61h und bas63h - stimmt nicht !


Scope ist die Bezeichnung für den **Geltungsbereich**, d.h. wo kann
welche Variable verwendet werden, wo ist sie gültig ?

Variablen, die innerhalb einer Funktion erstellt (=definiert)
wurden, sind **lokale Variablen**. Das bedeutet, dass diese Variable
nur innerhalb der Funktion verwendet werden kann.  
Genauer gesagt, existiert die Variable auch nur zur Laufzeit, 
also für die Zeit, bei der die Funktion abgearbeitet wird.


.. code:: python

    def foo():
        # Eine lokale Variable
        innen = "green"

    foo()
    print(innen)
    # führt zu dem Fehler: name 'innen' is not defined


Variablen, die aber außerhalb von Funktionen, und damit
also \'ganz links\' im Programmcode stehen, heißen **globale Variablen**.

.. _py-noglobal:

Diese Variablen können prinzipiell überall verwendet werden,
auch wenn globale Variablen möglichst **nicht verwendet** werden sollen.

.. code:: python

    def foo():
        print("Aussen", aussen)

    # Eine globale Variable
    aussen = "red"
    foo()


Der Kritikpunkt hier ist eine `unsaubere Schnittstelle`, denn die Funktion
verlässt sich darauf, dass es die Variable `aussen` gibt. Gibt es keine Variable mit diesem Namen,
stürzt das Programm mit einem Laufzeitfehler ab.
Für eine `saubere Schnittstelle` hätte ein Parameter verwendet werden müssen.

Aber wie so manchmal lässt uns Python hier große Freiheiten, 
aber im Sinne von einem sicheren, gut verständlichen und gut wartbaren Programmcode
sollten globale Variablen nur sehr sparsam und wohlüberlegt verwendet werden.

Manchmal werden `globale Variablen` benutzt, wenn ein bestimmter Wert
an sehr vielen Stellen benötigt wird, aber immer gleich bleibt.
So etwas wird als **Konstante** bezeichnet und häufig, ungeachtet der allgemeinen
Regeln, komplett großgeschrieben.

.. code:: python

    def foo(): 
        distance = 9 * UNIT

    # Eine globale Variable
    UNIT = 20
    foo()


Ein weiterführendes Thema, sind dann `Namensräume`, d.h. der lokale 
und der globale Namensraum, die aber hier nicht besprochen werden sollen.
