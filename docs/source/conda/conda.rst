
.. index:: conda, Paket, environment, prompt, pypi

.. _anac-conda:

#####
Conda
#####


Conda ist das Kommandozeilenprogramm für das Paketmanagementsystem,
d.h. mit dem Conda-Programm wird die jeweilige Arbeitsumgebung ausgewählt,
erstellt, Pakete dazugefügt u.s.w..

Der Anaconda-Navigator ist das grafische Frontend für ``conda``,
aber überlicherweise wird der :ref:`Anaconda Prompt <anac-prompt>` verwendet.

Die Arbeitsumgebung (=virtual Environment) steht am Anfang
des `Anaconda Prompts`. Die Standard (=Default) Umgebung heißt ``base``
und der Prompt sieht unter Windows dann so aus.

.. code-block:: text
    
    (base) C:\USERS\OLA>

Um zu sehen welche Pakete in der aktuellen Arbeitsumgebung vorhanden sind:

.. code-block:: text
    
    (base) C:\USERS\OLA> conda list

Um sehen welche Arbeitsumgebungen es gibt:

.. code-block:: text
    
    (base) C:\USERS\OLA> conda env list

Wenn es nun z.B. eine Arbeitsumgebung mit dem Namen `thonny` gibt,
können wir folgendermassen zu dieser Arbeitsumgebung wechseln:

.. code-block:: text
    
    (base) C:\USERS\OLA> conda activate thonny

und wechseln so wieder zurück:

.. code-block:: text
    
    (thonny) C:\USERS\OLA> conda deactivate

    (base) C:\USERS\OLA>

Für eine neue Arbeitsumgebung muss auch immer die gewünschte Python-Version angegeben werden.
(Die Angabe der Python-Version kann mehr oder weniger genau sein z.B. 3.8 oder 3.11.5)
Wir erstellen also ein neues `virtual environment` mit dem Namen `testenv`:

.. code-block:: text
    
    (base) C:\USERS\OLA> conda create --name testenv python=3.9


wechseln zur neu erstellten Arbeitsumgebung und installieren das Paket `openpyxl`
aus dem Anaconda Repository.

.. code-block:: text
    
    (base)    C:\USERS\OLA> conda activate testenv
    (testenv) C:\USERS\OLA> conda install openpyxl

Wenn ich noch zusätzlich die :ref:`IDE Thonny <thonny_ide>` installieren möchte,
prüfe ich, ob es das Paket unter `anacanda` gibt. Dazu suche ich Internet nach "conda thonny",
finde aber nichts. Dann installiere ich `Thonny` stattdessen aus dem `PyPI Repository <https://pypi.org>`_.

.. code-block:: text
    
    (testenv) C:\USERS\OLA> pip install thonny

    und rufe es gleich mal auf

    (testenv) C:\USERS\OLA> thonny
