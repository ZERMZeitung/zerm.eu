[_Ein halbes Jahr ist’s her, Zeit für einen neuen ZERM-Artikel!_](https://twitter.com/nichtchrissx/status/1409117348108324866)

Angesichts der anstehenden Bundestagswahl sind ein paar neue Artikel, sowie sonstige politische Aktivitäten einmal wieder nötig. Dieser Artikel soll die technischen Erneuerungsbestrebungen der letzten Monate dokumentieren und einen Ausblick auf die nächsten Artikel geben.

In den letzten Monaten wurden alle Tools zur Erstellung der ZERM grundlegend überarbeitet: `zm` wurde neugeschrieben, `zerm2pdf` stark verändert, `jasmin` eingeführt und `static-short` abgeschafft. Des Weiteren wurde der Server zur Auslieferung der Seite auch geografisch verschoben.

Das alte `zm`, jetzt als [`zm1`](https://github.com/ZERMZeitung/zm1) bekannt, basiert auf dem Tool [`lb`](https://github.com/LukeSmithxyz/lb). `zm1` generierte aus Artikeln, ursprünglich in HTML, später auch in Markdown, geschrieben, die Artikelseiten, Gesamtausgaben, Vorderseite und den RSS-Feed. Vorteile wie Nachteile sind hier eigentlich offensichtlich: Die Erstellung der Artikel war relativ einfach und die ZERM-Website konnte zusammen mit vier anderen Webseiten von [einem Apache-Webserver](https://github.com/chrissxMedia/chrissx.de.conf.sh/blob/14b0712def19e791c0e3d28e000b86f7259ef9e0/apache2/default-ssl.conf) ausgeliefert werden, dafür ließen sich die Artikel im Nachhinein nur schwer bearbeiten. \{https://github.com/ZERMZeitung/zerm.eu/commit/eb6ddcef08e1b34b3a19a168c2263f2f556c7723\} Dabei fielen RSS-Feed und Gesamtausgaben auch gerne einmal unter den Tisch. \{https://github.com/ZERMZeitung/zerm.eu/commit/a08f9c89603ca5b1f5cf5865734ebd212ed0705e\}

Das neue [`zm2`](https://github.com/ZERMZeitung/zm2) hingegen speichert die Artikel nur im Erstellungsformat (Markdown) und generiert die für `jasmin` nötigen CSV-Einträge.

`zerm2pdf` benötigte bisher [„eine Menge kruder Skript-Magie“](https://github.com/chrissxYT/zerm2pdf/blob/master/zerm2pdf#L31-L56), die jetzt endlich entfernt werden konnte. \{https://github.com/ZERMZeitung/zerm2pdf/blob/master/zerm2pdf\}

Bisher lieferte die Seite ein Apache HTTPD 2.4, zusammen mit anderen Seiten der chrissx Media, aus, die Weiterleitungen unter `zerm.link` übernahm ein eigener Webserver namens [`static-short`](https://github.com/ZERMZeitung/static-short).

Diese werden jetzt durch [`jasmin`](https://github.com/ZERMZeitung/jasmin) ersetzt: Ein Webserver, der dynamisch aus der Artikelliste die Startseite und den RSS-Feed generiert. Die Artikel werden beim Seitenaufruf von Markdown in HTML übersetzt und für die Gesamtausgaben werden alle Artikel des Jahres hintereinander gehängt. Die `zerm.link`-Weiterleitungen werden ebenfalls, fast genau wie in `static-short`, hier behandelt.

Zuletzt wurde noch der physische Server geändert: Von Anfang an wurde die ZERM vom `httpi` \{https://github.com/chrissxMedia/chrissx.de.conf.sh/blob/f43bb11e829792a84816534782ad54504c222d49/README.md#servers\}, später dem `httpis` \{https://github.com/chrissxMedia/chrissx.de.conf.sh/blob/14b0712def19e791c0e3d28e000b86f7259ef9e0/README.md#servers\}, aus Pegnitz ausgeliefert. Seit Kurzem allerdings wird ein neuer Server unter dem Codenamen `sophia` von chrissx Media betrieben. Dieser befindet sich in einem Rechenzentrum in Nürnberg und hat eine viel schnellere Internet-Anbindung. Darauf wird die ZERM, neben vielen anderen chrissx Media Webseiten, mit einem Nginx ausgeliefert, `jasmin` übernimmt für die ZERM das Backend. \{https://github.com/chrissxMedia/chrissx.de.conf.sh/blob/c28f60ac004e56ce982344201d7cb4b4684ed0cc/README.md#servers\}

Zuletzt, inmitten der Entstehung dieses Artikels, wurde auch das Design nochmals etwas überarbeitet \{https://github.com/ZERMZeitung/zerm.eu/commit/16b13f032720509552773cf4a6884ce7cbbdbabb\} \{https://github.com/ZERMZeitung/zerm.eu/commit/a2fbc7f097838a68fea05ad0867d254e04b3e86e\}, wie Ihnen vielleicht schon aufgefallen ist.

Man kann also konkludieren, dass die gesamte ZERM-Infrastruktur erneuert wurde. Sie wollen aber vielleicht noch wissen, welche Artikel als nächstes kommen.

Welche Sie einschicken \{https://github.com/ZERMZeitung/zerm.eu/pulls\} \{mailto:zerm@chrissx.de\}, können wir natürlich nicht vorhersehen, aber bezüglich meiner kann ich Aussagen treffen: Die nächsten Artikel werden sich zumeist direkt mit der anstehenden Bundestagswahl befassen. Hier wird dann beispielsweise der Versuch des Aufbaus eines neuen Images der AfD behandelt oder über die, leider noch zu unbekannten, Skandale einiger großer Parteien berichtet.

Nach der Bundestagswahl werden wieder Artikel zu allgemeineren Themen erscheinen.
