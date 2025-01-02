
.. index:: environment, virtual environment, Umgebung, virtuelle Umgebung
.. _venv-index:

####################
Virtuelle Umgebungen
####################


Neben den Modulen der Standardbibliothek können von `PyPI <https://pypi.org>`_ 
noch alle möglichen Pakete und Module installiert werden.

Das kann dazu führen, dass bestimmte Paket Versionen nicht zusammenpassen,
oder bestehende Python Software nicht mehr :ref:`richtig funktioniert <py-vorsicht>`!

Eine virtuelle Umgebungen (=virtual environment) bildet einen Arbeitsbereich,
in dem Python-Pakete und Module  so voneinander getrennt bzw. zusammengestellt werden,
dass sie sich nicht gegenseitig in die Quere kommen können.

Auch zum Erstellen einer virtuellen Umgebung gibt es mehrere Varianten.
Ich bevorzuge das Module ``venv``, so wie es bei den `Django Girls <https://tutorial.djangogirls.org/de/installation/>`_ 
im Abschnitt 'Virtuelle Umgebung' beschrieben ist.

..
    Ich bevorzuge das Module ``venv``, so wie es bei den `Django Girls <https://tutorial.djangogirls.org/de/installation//#virtualenv>`_ beschrieben ist.
    im Abschnitt 'Virtuelle Umgebung'    (falls das # in der Url nicht tut)

In der Regel werden Virtuelle Umgebungen nicht systemweit, sondern im Bereich des jeweiligen Benutzers erstellt.
Jede virtuelle Umgebung erhält ein eigenes Verzeichnis, in dem die jeweilige Software abgelegt wird.
In welcher Umgebung jeweils gearbeitet werden soll, geschieht dann durch einen
einen Befehl, so dass der Arbeitsbereich jederzeit leicht gewechselt werden kann.

Im Wissenschaftlichen Umfeld ist die Python-Distribution Anaconda weit verbreitet.
Die Hauptaufgabe von Anaconda ist das reibungslose Zusammenspiel von 
der für diesen Bereich wichtigen Python-Paketen und dem Verwalten der Virtuellen Umgebungen.

.. _anac_ide:

Anaconda
--------

Anaconda ist eine Distribution (=Zusammenstellung), die aus der Programmiersprache Python und einer ganzen Reihe von Werkzeugen und Bibliotheken besteht.

Verwendet wird Anaconda v.a. im Wissenschaftlichen Bereich, für Datenanalyse und große Datenmengen. Es enthält dafür schon alle wichtigen Module und Pakete
und hat einen weiteren Schwerpunkt bei der interaktiven Verwendung von Python, wie z.B. den Jupyter Notebooks.

Der eigentliche Kern von Anaconda ist aber ein Paketmanagement System, d.h. die Möglichkeit
Arbeitsumgebungen (= virtual Environments) zu erstellen, zu ändern usw.

Solche Werkzeuge für virtuellen Umgebungen werden auch von der Python-Standard-Bibliothek angeboten.
Anaconda kann aber mit seinem conda-Tool die Abhängigkeiten von verschiedenen Paket-Versionen untereinander besser berücksichtigen.

Dazu bietet Anaconda eigene Repositories an, enthält aber auch das 
Kommandozeilen-Programm ``pip`` und kann damit auf des Repository 
von `PyPI <https://pypi.org>`_ zugreifen.
Wenn ein Paket aber in einem der Anaconda Repositories vorhanden ist, sollte das bevorzugt werden.

Der Anaconda Navigator ist das grafische Frontend zur Paketverwaltung von Anaconda und startet bzw. zeigt
die Anaconda Prompt aus zu verwenden bzw. zu starten.

.. toctree::
    :maxdepth: 3

    cprompt.rst
    conda.rst
