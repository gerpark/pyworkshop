
.. index:: Kommandozeile, Konsole, Shell, Terminal, GUI, CLI, cmd 

.. _cmd-line:

#################
Die Kommandozeile
#################

Bevor wir mit Python anfangen, möchte ich ein bisschen genauer auf die
Kommandozeile bzw. Kommandozeilen Programme eingehen.

Ganz allgemein geht es um die Schnittstelle zwischen Mensch und Maschine, 
die in der IT (Informations Technologie) als *User Interface* bezeichnet wird.
Wir sind gewohnt über eine *grafische Benutzerschnittstelle* auf einen
Computer zuzugreifen, d.h. wir bewegen die Maus auf dem Bildschirm
und klicken dort auf Symbole oder ähnliches.
Ein solches Grafical-User-Interface wird abgekürzt häufig als *GUI* bezeichnet.

Bevor es hochauflösende Bildschirme gab, fand die Kommunikation (vielleicht besser Interaktion)
mit dem Computer ausschliesslich über eine Kommandozeile, - ein *Command Line Interface (CLI)* statt.

Ein Kommandozeilen Programm erkennt man an der Eingabeaufforderung (= *Prompt* ),
die am unteren Ende eines meist schwarzen Fensters zu finden ist. 

Hier kann jetzt ein Befehl über die Tastatur eingegeben werden,
der dann nach Drücken der Eingabetaste ausgeführt wird. 
Danach steht der Cursor wieder rechts vom Prompt, also bereit für weitere Eingaben.

Diese Art von Programmen haben (wie immer) die unterschiedlichsten
Bezeichnungen wie z.B. *Konsole*, *Terminal* und *Shell*.
Jedes Betriebssystem besitzt ein solches Kommandozeilenprogramm und kann darüber 
angesprochen werden.
Jetzt könnte man denken, dass das doch eher altmodisch ist, aber ganz im Gegenteil,
häufig ist die Kommandozeile die elegantere und schnellere
Alternative zu unzähligen Mausklicks.

Bei den `Django Girls <https://djangogirls.org>`_, heißt es "Dein neuer Freund, die Kommandozeile",
das kann ich nur unterstreichen. Dort gibt es überhaupt ein paar sehr `gute Tutorials <https://tutorial.djangogirls.org/de/intro_to_command_line>`_,
und das nicht nur zur Kommandozeile.


Die Windows Kommandozeile
-------------------------

wird manchmal auch als Dos-Box bezeichnet. Das eigentliche Programm heißt ``cmd.exe``.
Um es aufzurufen suchen wir z.B. das Programm ``cmd`` oder wir drücken die Windowstaste zusammen mit einem 'R' (:kbd:`<Windows>-R`)
und rufen von dort ``cmd.exe`` auf. 
Im Detail ist das auch wieder bei `den Django Girls  <https://tutorial.djangogirls.org/de/intro_to_command_line>`_ beschrieben.
Der `Prompt` beginnt unter Windows mit dem aktuellen Verzeichnis und endet mit einem '>', z.B.:

.. code-block:: text
    
    C:\USERS\OLA>

Jetzt können alle möglichen Befehle eingegeben werden. So ist es möglich sich mit ``cd`` durch das Dateisystem zu bewegen
und sich mit ``dir`` den Inhalt eines Verzeichnisses anzeigen zu lassen.
Aber dort lassen sich auch (GUI)Programme wie ``notepad`` oder der ``explorer`` aufrufen.

Python
------

Wird `Python` auf der  Windows Kommandozeile aufgerufen, kann Python interaktiv verwenden werden.
Der `Prompt` sind hier 3 "Größer-Zeichen" **>>>**  und jetzt werden nur noch gültige
Python Befehle/Anweisungen verstanden. Die "Python Kommandozeile" wird mit der Anweisung ``quit()`` verlassen
und wir befinden uns dann wieder auf der Windows Kommandozeile.

Damit das Programm ``python`` auf der Windows Kommandozeile gefunden wird,
muss bei der Installation zusätzlich :ref:`diese Option <myinstallation-hint>` ausgewählt werden.
