
.. index:: datetime, date, Datum, Zeit, time, timedelta, Zeitdifferenzen, Stringformatierung, Formatierung

.. _date:

##############
Datum und Zeit
##############

Zur Verarbeitung von Datums- und Zeitangaben hält die Standardbibliothek
das Module ``datetime`` bereit.  Die Syntax ist vielleicht auf den ersten Blick etwas verwirrend, 
aber eigentlich sind die Methoden gut zu benutzen.

Dieses Module enthält 4 Klassen:

*   time

*   date

*   datetime

*   timedelta


Ich importiere die Klassen immer auf dieselbe Weise und immer nur das was ich brauche.
Wenn es z.B. nur um das **Datum** geht und vielleicht noch Datumsdifferenzen
schreibe ich:

.. code:: python

    >>> from datetime import date, timedelta

Jetzt möchte ich vielleicht wissen, was das aktuelle Datum ist:

.. code:: python

    >>> d1 = date.today()
    >>> print(d1)

Und zum 15ten Januar 2019 komme ich so:

.. code:: python

    >>> d2 = date(2019, 1, 15)
    >>> print(d2)

Die Klasse ``date`` hat die Attribute ``year``, ``month`` und ``day``,
die ich direkt verwenden kann.

.. code:: python

    >>> d2.month

Ein häufige Anforderung ist es ein Datum in einen String, also in ein
bestimmtes Format zu überführen, wie das z.B. auf Deutsch verbreitet ist.

.. code:: python

    >>> datum = d2.strftime("%d.%m.%Y")

Für Zeitdifferenzen ist das Module **timedelta** zuständig.
Die Klasse timedelta kennt die Attribute ``days`` und ``seconds``,
mit denen sich ja jede Zeitdifferenzen abbilden läßt.

.. code:: python

    >>> delta = d1 - d2
    >>> delta.days

Und jetzt können wir z.B. 2 Tage zu einem Datum addieren:

.. code:: python

    >>> td = timedelta(2)
    >>> d3 = d2 + td
    >>> print(d2, "+ 2 Tage", d3)

Aber die wichtigste oder zumindest vielseitigste Klasse heißt wie das Module **datetime**:

.. code:: python

    >>> from datetime import datetime, date, timedelta
    >>> dt1 = datetime.now()
    >>> print(dt1)

Häufig verhält sich ein datetime-Objekt ähnlich wie ein date-Objekt,
die wichtigsten zusätzlichen Attribute sind ``hour``, ``minute``, ``second``.
So kann ein ein  datetime-Objekt, genauso wie ein date-Objekt 
erstellt werden. Die Argumente mit den Zeitangaben haben 0 als Defaultwerte.
Bei Zeitdifferenzen geht es jetzt natürlich nicht nur um Tage, sondern
auch um Stunden und Minuten.

Wir hatten zuvor aus einem Datums-Objekt einen String erzeugt. 
Für die umgekehrt Richtung benötigen wir aber das datetime - Module.

So kann hier aus einem String mit einer Zeitangabe ein datetime-Objekt erzeugt werden:

.. code:: python

    >>> datum = "1.12.21"
    >>> dt2 = datetime.strptime(datum, "%d.%m.%y")

Für die Zeitangaben gibt es noch einige **andere Kürzel**, hier also
das Link zu den `Format Kürzeln <https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes>`_. 

Und bevor ihr zu lange probiert, so einfach aus einem datetime-Objekt ein date-Objekt zu erzeugen
funktioniert nicht und für die umgekehrte Richtung gilt das natürlich auch. Mit 'so einfach' ist
ein 'casting' gemeint, also etwas wie ``datetime(date(2020,12,1))`` geht nicht, aber
es gibt ja andere Möglichkeiten, bei denen die Konvertierung dann auch eindeutig ist.
