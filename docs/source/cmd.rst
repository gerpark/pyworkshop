
.. index:: Kommandozeile, Konsole, Shell, Terminal, GUI, CLI, cmd 

.. _cmd-line:

#################
Die Kommandozeile
#################

Bevor wir mit Python anfangen, möchte ich bisschen genauer auf die
Kommandozeile bzw. Kommandozeilen Programme eingehen.

Ganz allgemein geht es um die Schnittstelle zwischen Mensch und Maschine, 
die in der IT (Informations Technologie) als *User Interface* bezeichnet wird.
Wir sind gewohnt über eine "grafische Benutzerschnittstelle" auf einen
Computer zuzugreifen, d.h. wir bewegen die Maus auf dem Bildschirm
und klicken dort auf Symbole oder ähnliches.
Ein solches Grafical-User-Interface wird als *GUI* abgekürzt.

Bevor es hochauflösende Bildschirm gab, fand die Kommunication mit dem
Computer über eine Kommandozeile, - ein Commandline Interface ( *CLI* ) statt.

Ein Kommandozeilen Programm sieht dann so aus, dass am unteren Ende eines meist schwarzen Fensters 
die sogenannte Eingabeaufforderung (= *Prompt* ) zu sehen ist.
Hier wird jetzt ein Befehl über die Tastatur eingegeben,
der dann mit dem Drücken der Eingabetaste ausgeführt wird.

Danach steht der Cursor wieder rechts vom Prompt, also bereit für weitere Eingaben.

Diese Art von Programmen haben (wie immer) die unterschiedlichsten
Bezeichnungen wie z.B. *Konsole*, *Terminal* und *Shell*.
Jedes Betriebssystem hat z.B. eine solches Kommandozeilenprogramm und kann darüber 
angesprochen werden.
Jetzt könnte man denken, dass das doch eher altmodisch ist, aber ganz im Gegenteil,
häufig ist die Kommandozeile die viele elegantere und schnellere
Alternative zu unzähligen Mausklicks.

Bei den `Django Girls <https://djangogirls.org>`_, heisst es "Dein neuer Freund, die Kommandozeile",
dem kann ich mich nur anschliessen. Dort gibt es überhaupt ein paar sehr `ansprechende Tutorials <https://tutorial.djangogirls.org/de/intro_to_command_line>`_,
und das nicht nur zur Kommandozeile.


Die Windows Kommandozeile
-------------------------

wird manchmal auch als Dos-Box bezeichnet. Der eigentliche Programmname heißt ``cmd.exe``.
Um es aufzurufen suchen wir z.B. das Programm cmd oder wir drücken die Windowstaste zusammen mit einem 'R' (:kbd:`Windows-R`)
und rufen von dort ``cmd.exe`` auf. 
Im Detail ist das unter dem `Link oben <https://tutorial.djangogirls.org/de/intro_to_command_line>`_ beschrieben.
Der `Prompt` beginnt unter Windows meist dem aktuellen Verzeichnis und endet mit einem `>`.

.. code-block:: text
    
    C:\USERS\OLA>

Jetzt können alle möglichen Befehle eingegeben werden. So ist es möglich sich mit ``cd`` durch das 
Dateisystem zu bewegen und sich mit ``dir`` den Inhalt von Verzeichnisses anzeigen zu lassen.
Aber von dort lassen sich auch Programme wie ``firefox`` oder der ``explorer`` aufrufen.

Und dann gibt es auch ein Programm  ``python`` mit dem interaktiv Befehle in der Computersprache python ausgeführt werden können.
Damit das Programm python auf der Kommandozeile auch gefunden werden kann, muss bei der Installation 
:ref:`die Option <myinstallation-hint>`
ausgewählt worden sein.






