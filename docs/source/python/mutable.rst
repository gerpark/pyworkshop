.. _py-mutable:

.. index:: mutable, unmutable, Datentyp, veränderlich, unveränderlich

#############################
un-, veränderliche Datentypen
#############################

.. apr21: Vorlage war enf39i.py

Spätestens dann, wenn es darum geht, wie der Wert von Variablen
durch Funktionen geändert werden kann, kommen wir zu dem Thema:
veränderliche und unveränderliche Datentypen.

In Python lassen sich alle **Datentypen** in diese beiden Gruppen unterteilen. 

Viele Basisdatentypen wie `int`, `str`, `float` gehören zur Gruppe
der **unveränderliche** Datentypen.
Die meisten Datentypen sind allerdings **veränderlich**, wir kennen 
aus dieser Gruppe bisher nur die Liste, also den Datentyp `list`.

Wenn ich einen String, den ich an eine Funktion übergebe habe,
dort ändern will, geht das nur mit Hilfe von `return`.
Das bedeutet aber auch, dass ich dann einen neuen String
zurückgebe.

.. code:: python

    def foo(text):
        res = "<" + text + ">"
        return  res

(Ich könnte den Parameter, der ja eine lokale Variable ist, auch ändern,
aber das wäre dann nur lokal, außerhalb der Funktion würde sich der Wert nicht ändern.)

Wenn ich aber eine Liste, also einen `veränderlichen Datentyp` an die Funktion
übergebe, kann die Liste in der Funktion geändert werden !

.. code:: python
    
    def foo(liste):
        liste[0] = 111
    
    etwas = [1, 2, 3]
    foo(etwas)
    print("geändert ? :", etwas)


Zu diesem Thema gibt es noch zwei Besonderheiten bei :ref:`veränderlichen Datentypen <py-mutable2>`,
die ich später zusammen mit Objekten bespreche.
