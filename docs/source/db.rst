
.. index:: Datenbank, relationale Datenbank, SQL, SQLite, SQLite3

.. _db:

###########
Datenbanken
###########

Ganz allgemein können in Datenbanken Daten strukturiert abgelegt und abgefragt werden.
Hier wird aber nur der am meisten verbreitete Datenbanktyp behandelt,
die **Relationale Datenbank**.
Diese Art von Datenbank enthält Tabellen, die auf vielfältige Weise 
miteinander verknüpft sind und mit einer einheitlichen Sprache
abgefragt und geändert werden können.
Es gibt eine Vielzahl solcher Datenbanken, die diesen Sprachstandard 
**SQL** (Structured Query Language) im großen und ganzen unterstützen.

Bekannte Datenbanken sind z.B. Oracle und der MS-SQLServer, 
im Open Source bereich MySQL und Postgres. 

Häufig ähneln diese Datenbanksysteme fast einem Betriebssystem,
mit Benutzern, Rechten und eigener Speicherverwaltung.

Aber es gibt auch das sehr 'schlanke' Datenbanksystem `SQLite <https://www.sqlite.org>`_, 
bei dem die gesamte Datenbank in einer einzigen Datei abgelegt ist. 

Für ein Buchungssystem, in dem viele Anwendungen gleichzeitig auf dieselbe 
Datenbank zugreifen müssen, eignet sich `SQLite` nicht. Aber 
zur Ablage von Informationen, die bequem mit SQL ausgewertet
und geändert werden können, ist sie sehr gut geeignet.

Die Python Standardbibliothek enthält alles notwendige um alle Aufgaben
im Zusammenhang mit einer `SQLite DB` erledigen zu können.

Verbindungen
------------

Eine Datenbank liegt meist als ein Datenbankserver vor, d.h. dass sich
viele verschiedene Anwendungen gleichzeitig mit dieser Datenbank verbinden können.

Damit sich die einzelnen Anwendungen nicht gegenseitig in die Quere kommen
gibt es das Konzept der **Transaktionen**. Hiermit können Änderungen an mehreren
Datenbanktabellen so zusammen gefasst werden, dass entweder **alle** Änderungen
**oder keine** Änderung durchgeführt wird. So wird sichergestellt, dass bei
einem Buchungssystem z.B. ein Sitzplatz auch nur einmal verkauft wird.

Jede Datenbank hat auch ein Kommandozeilenprogramm, das für Administrative Zwecke
verwendet wird, in dem aber auch SQL-Befehle eingegeben werden können.
bei `SQLite` ist das 'Command-line-tool' `hier <https://www.sqlite.org/download.html>`_ zu finden.

Dann gibt es speziell für `SQLite` ein grafisches Programm,
in dem komfortabel Daten angesehen und geändert werden können,
bei dem aber natürlich auch SQL-Befehle eingeben werden können.

Es gibt auch andere Programme wie der DbVisualizer, der für mehrere
Datenbanksysteme benutzt werden kann und z.B. auch bei de Zeitschrift
`chip <https://www.chip.de/downloads/DbVisualizer_33173230.html>`_ zu erhalten ist.

Wir werden hier zu einem von `Python` aus, eine SQlite Datenbank verwenden,
aber zusätzlich auch ein grafisches Tool nutzen. Die Software ist Open-Source und damit auch auf allen
Plattformen kostenlos verfügbar: `DB-Browser für SQLite <https://sqlitebrowser.org/dl/>`_. 
