
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
Es gibt eine Vielzahl solcher Datenbanksysteme, die diesen Sprachstandard 
**SQL** (Structured Query Language) im großen und ganzen unterstützen.

Bekannte Datenbanken sind z.B. Oracle und der MS-SQLServer, 
im Opensource Bereich MySQL und Postgres. 

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
gibt es das Konzept der **Transaktionen**. Damit können mehrere Änderungen, d.h. 
SQL-Anweisungen so zusammen gefasst werden, dass entweder **alle** Änderungen
**oder keine** Änderung durchgeführt wird. So wird sichergestellt, dass bei
einem Buchungssystem z.B. ein Sitzplatz auch nur einmal verkauft wird.

Jedes Datenbanksystem enthält ein eigenes grafisches Programm
mit dem komfortabel Daten verwaltet, angesehen und geändert werden können,
und natürlich auch SQL-Befehle direkt eingeben werden können.

Es gibt aber auch Programme wie den DbVisualizer, der für mehrere
Datenbanksysteme benutzt werden kann und z.B. auch bei de Zeitschrift
`chip <https://www.chip.de/downloads/DbVisualizer_33173230.html>`_ zu erhalten ist.

Jedes Datenbanksystem kennt aber auch immer ein Kommandozeilenprogramm, das z.B. für Administrative Zwecke
verwendet wird und in dem SQL-Skripte ausgeführt werden können.
bei `SQLite` ist ein solches 'Command-line-tool' `hier <https://www.sqlite.org/download.html>`_ zu finden.

In der Regel wird aber von einer Anwendung aus auf eine Datenbank zugegriffen, d.h. es gibt
für die meisten Programmiersprachen die Möglichkeit sich mit Datenbanken zu verbinden und dann
dort SQL auszuführen.

Wir werden hier zu einem von `Python` aus, eine SQLite Datenbank verwenden,
aber zusätzlich auch ein spezielles grafisches Tool für  `SQLite`  nutzen. Die Software ist Opensource und damit auch auf allen
Betriebssystem-Plattformen kostenlos verfügbar: `DB-Browser für SQLite <https://sqlitebrowser.org/dl/>`_. 

SQL
---

Die Art wie die Daten abgelegt, gelesen und manipuliert
werden, geschieht in der Sprache SQL, das steht für **Structured Query Language**.
Wikipedia enthält einen ganz `guten Überblick <https://de.wikipedia.org/wiki/SQL>`_. 

Die SQL-Befehle lassen sich in 2 Gruppen unterteilen.

Zum einen die Befehle zur Datenmanipulation,
das sind `insert`, `select`, `update` und `delete`.

Zum anderen eine Reihe von Befehlen zu Verwaltung der
Datenstrukturen, z.B. zum Erzeugen einer Tabelle, `create table`, `create index` etc..

Hierbei gibt es zwischen den Datenbanksystem meist einige Unterschiede. Bei den Grundoperationen
dagegen, mit select, insert, ... wird der Sprachstandard aber weitestgehend eingehalten. 
Dies gilt auch für `SQLite`, d.h. hier können komplizierte Abfragen etc. erstellt werden,
die dem aktuellen SQL-Standard entsprechen.
