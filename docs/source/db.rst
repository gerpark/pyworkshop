
.. index:: Datenbank, relationale Datenbank, SQL, SQLight SQLight3

.. _db:

###########
Datenbanken
###########

Ganz allgemein können in Datenbanken Daten strukturiert abgelegt und abgefragt werden.
Hier wird aber nur verbreitestete Datenbanktyp behandelt,
die `Relationlen Datenbank`.
Diese Art von Datenbank enthält Tabellen, die auf vielfältige Weise 
miteinander verknüpft sind und mit einer einheitlichen Sprache
abgefragt und geändert werden können.
Es gibt eine Vielzahl solcher Datenbank, die diesen Sprachstandard 
SQL (Structured Query Language) im Großen und Ganzen unterstützen.

Bekannte Datenbanken sind z.B. Oracle und der MS-SQLServer, 
im Open Source bereich MySQL und Postgres. 

Häufig ähneln diese Datenbanksysteme fast einem Betriebssystem,
mit Benutzern, Rechten und eigener Speicherverwaltung.

Aber es gibt auch das sehr einfaches Datenbanksystem `SQLite <https://www.sqlite.org>`_, 
bei dem alles in einer einzigen Datei abgelegt ist. 

Für ein Buchungssystem, in dem viele Anwendungen gleichzeitig auf die selbe 
Datenbank zugreifen müssen, eignet sich SQLite nicht. Aber 
zur Ablage von Informationen, die bequem mit SQL ausgewertet
und geändert werden können, ist sie sehr gut geeignet.

So ist Python in seiner Standardbibliothek voll ausgestattet, um
alle Aufgaben im Zusammenhang mit einer SQLite DB erledigen zu können.

