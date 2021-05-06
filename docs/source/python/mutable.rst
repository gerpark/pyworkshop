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
aus dieser Gruppe bisher nur die Liste `list`.

Wenn ich z.B einen String an eine Funktion übergebe,
dann kann ich die entsprechende Variable innerhalb der Funktion ändern,
aber der Wert ausserhalb der Funktion bleibt trotzdem erhalten.

.. code:: python

    def foo(text):
        text = "neues"
        print("Text in foo:", text)
    
    etwas = "altes"
    foo(etwas)
    print("Text ausserhalb:", etwas)


Wenn ich aber eine Liste, also einen veränderlichen Datentyp
an die Funktion übergeben, kann ich die Liste auch verändern !

.. code:: python
    
    def foo(liste):
        liste[0] = 111
    
    etwas = [1, 2, 3]
    foo(etwas)
    print("geändert ? :", etwas)


Zu diesem Thema gibt es noch zwei Besonderheiten bei :ref:`veränderlichen Datentypen <py-mutable2>`,
die ich später zusammen mit Objekten bespreche.
