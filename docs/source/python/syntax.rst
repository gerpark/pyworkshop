
.. index:: Syntax, Regeln, Grammatik, Kommentar, pass, if

######
Syntax
######

Mit der if Anweisung haben wir schon die große Besonderheit von Python
kennengelernt, das **Einrücken**.
Hier nochmal ein kleiner Überblick zur Grammatik (=Syntax) also
zu den Regeln, die beim Schreiben von Python Programmen beachtet werden müssen:

*   Alle Anweisungen beginnen genau am **linken Rand** der Zeile,
    oder sind nach besonderen Regeln nach rechts *eingerückt*. |br|
    |br|
*   Eine Anweisung endet mit dem *Ende der Zeile* 
    (Semikolons sind also nicht notwendig). 
    |br| |br|

*   Um die Lesbarkeit des Codes zu verbessern, können an bestimmten
    Stellen **Leerzeichen** und *Leerzeilen* eingefügt werden.
    |br| |br|
*   Nach einem **Doppelpunkt**, wie z.B. bei einer `If-Anweisung` folgt immer eine oder 
    mehrere eingerückte Anweisungen. Um dem Genüge zu tun kann dort einfach nur
    das Schlüsselwort ``pass`` stehen.
    |br| |br|
*   Zusammengehörende  Anweisungen, die z.B. auf eine :ref:`If-Anweisung <bool1>` folgen,
    sind alle gleich weit nach rechts **eingerückt** (TAB oder besser 4 Leerzeichen).
    (Es gibt hierfür keine geschweiften Klammern oder ähnliches)
    |br| |br|
*   Ein solcher **Anweisungsblock** endet an der Stelle, an der eine Anweisung
    wieder weiter links steht.
    |br| |br|
*   **Kommentare** innerhalb bzw. am Anfang einer Zeile beginnen mit einem '#' (hash)
    und müssen gegebenenfalls auch richtig eingerückt sein.
    |br| |br|
*   **mehrzeilige Kommentare** können auch mit einem ``"""`` beginnen und enden mit ``"""``  
    und müssen auch richtig eingerückt sein. Statt dem ``"""`` kann auch jeweils
    ein ``'''`` verwendet werden.
    |br| |br|


Hier nochmal ein kleines Beispiel:

.. code:: python

    if zahl < 100:
        print("die Bedingung stimmt,")
        # alle anderen Zeilen/Anweisungen, die dazugehören
        # müssen gleich weit eingerückt sein
        print("die Zahl ist kleiner 100.")
    else:
        pass    # macht einfach nichts
        print("... stimmt nicht, die Zahl ist zu gross.")

    # Jetzt gehts wieder auf der ersten Ebene weiter, denn
    # der "eingerückte Anweisungs-Block" ist zu Ende.
    # Die folgende Anweisung wird also in jedem Fall ausgeführt.
    print("Programm Ende")



.. |br| raw:: html

   <br>
