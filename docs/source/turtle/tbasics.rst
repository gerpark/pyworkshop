

.. index:: Turtle Basics

########################
Turtle - Grundsätzliches
########################

Um das ``Turtle Modul`` nutzen zu können, muß es zuerst importiert werden.
Dabei sind erste 'Gehversuche' auch auf der :ref:`Python-Shell<python-shell>` möglich.

Wird aber stattdessen ein Skript erstellt, muss dort als letzte Anweisung
`mainloop()` stehen.  Dies hängt mit den Eigenschaften von grafischen Programmen
zusammen.
Wird das Programm aber nur aus der  :ref:`IDLE <idle>` heraus gestartet, ist die Anweisung
`mainloop` nicht notwendig, da deren Funktion von der IDLE übernommen werden kann.

**!!! Achtung !!!**
Wenn wir ein Script benutzen, darf die Datei **nie** `turtle.py` heißen,
da sonst die ganze Turtle-Software nicht mehr funktioniert (:ref:`Module <module-use>`!).

Die Turtle selbst, ist eigentlich ein **Zeichenstift**, die Spitze des Stifts 
kann mehrere Formen annehmen, z.B. auch die Form einer Schildkröte.


.. code:: python

    from turtle import *

    # Das Aussehen des Zeichenstifts ändern
    shape("turtle")

    # Den Zeichenstift 100 Pixel nach vorne bewegen
    forward(100)

    mainloop()
