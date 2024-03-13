---
template: "blog_entry.html"
title: "Angriff auf freie Software? EU-Richtlinie schränkt Gerätehoheit ein"
date: 2015-11-23 11:00:00
categories: community
---



Nach einer Richtlinie der Europäischen Union sollen Hersteller von funkfähigen Geräten stärker reguliert werden. Hersteller sollen sicherstellen, dass die Geräte ausschließlich so wie vorgegeben funktionieren. Dafür sollen Veränderungen der Software zukünftig durch die Hersteller verhindert werden. Das ist insbesondere bei WLAN-Routern ein Problem für freie Software und schränkt das Prinzip der Gerätehoheit ein. Die Käufer.innen hätten damit keine Kontrolle mehr über ihre Geräte, sondern würden von den Herstellern ausgesperrt.

Diese Regulierung ist aber auch ein Sicherheitsproblem, weil die Hersteller bei Sicherheitsupdates oft weniger gewissenhaft sind als die freie Softwaregemeinschaft mit Projekten wie [OpenWRT](https://openwrt.org/) oder [DD-WRT](https://www.dd-wrt.com/site/). Diese Projekte bieten Nutzer.innen eine Möglichkeit, auch die Router abzusichern, die von den Herstellern keine Sicherheitsaktualisierungen mehr erhalten.
<!-- more -->

#### EU gibt Einschränkung der Gerätehoheit vor
Die bisher weitgehend unbeachtete [Richtlinie 2014/53/EU](http://eur-lex.europa.eu/legal-content/DE/TXT/HTML/?uri=CELEX:32014L0053&from=DE) der EU sieht vor, dass Hardware, die zum Versenden von Funkwellen geeignet ist, nur mit vom Hersteller geprüfter Software verwendbar sein soll. Wörtlich heißt es in der Richtlinie:

> „Funkanlagen müssen in bestimmten Kategorien oder Klassen so konstruiert sein, dass sie die folgenden grundlegenden Anforderungen erfüllen: Sie unterstützen bestimmte Funktionen, mit denen sichergestellt werden soll, dass nur solche Software geladen werden kann, für die die Konformität ihrer Kombination mit der Funkanlage nachgewiesen wurde.“ (Art. 3, Abs. 3 lit i).

Eine solche Vorschrift kommt einem Verbot von alternativer Software auf funkfähigen Geräten gleich. Denn für den verlangten Nachweis, dass die Kombination von Software und Gerät mit der Richtlinie konform ist, sind die Hersteller zuständig. Folglich müssten die Hersteller alternative Software für ihre Geräte ebenfalls prüfen und zertifizieren lassen, oder sie müssten die Installation dieser Software technisch verhindern.

Begründet wird die Richtlinie mit der öffentlichen Sicherheit und Gesundheit, da alternative Software in manchen Fällen in der Lage ist, die erlaubten Grenzwerte für Übertragungsstärke und Frequenzen zu überschreiten oder nicht-standardkonforme Signale zu übertragen. Dies könnte eine Gefahr für Gesundheit und für andere Geräte sein. Jedoch offenbart der Blick in die Software vieler Router, dass schon seit Jahren auch mit der Software des Herstellers die Grenzwerte überschritten werden können, falls falsche Einstellungen vorgenommen werden (z.B. Länder-Einstellung auf USA).

####Widerspruch zur Endgerätefreiheit
Diese Einschränkung der Gerätehoheit kommt überraschend, da die Bundesregierung die Wahlfreiheit gerade mit dem [Gesetzentwurf zur Abschaffung des „Routerzwangs“](https://netzpolitik.org/2015/der-lange-weg-des-routerzwangs-zur-endgeraetefreiheit/) stärken möchte. Der Gesetzentwurf zur Endgerätefreiheit ist zielführend und wird von Digitalcourage und anderen Organisationen wie der [Free Software Foundation Europe](https://fsfe.org/) und dem [Verbraucherzentrale Bundesverband](http://www.vzbv.de/) in [einem Verbändeschreiben](https://fsfe.org/news/2015/news-20151028-01.html) unterstützt.

#### Deutsche Umsetzung
Die Richtlinie ist auf EU-Ebene bereits beschlossen, es folgt nun die Umsetzung in nationales Recht in allen Mitgliedsstaaten. Eine [Anfrage nach dem Informationsfreiheitsgesetz](https://fragdenstaat.de/anfrage/stand-der-umsetzung-der-richtlinie-2014-53-eu/#nachricht-32705) hat ergeben, dass die Vorbereitungen dazu in Deutschland bereits laufen und wir in den nächsten Wochen einen Gesetzentwurf erwarten können.

Dabei wird das Gesetz voraussichtlich nicht definieren, welche Geräte genau von dieser Regulierung betroffen sind. Stattdessen wird der EU-Kommission das Recht gegeben, diese Klassen durch spätere Beschlüsse zu definieren, die dann vermutlich in Form von Verwaltungsanordnungen auch in Deutschland bindend werden, ohne dass sie als Gesetz den Bundestag passieren müssten. Neue Regulierungsentscheidungen können im EU-Rat und -Parlament durch ein Veto blockiert, müssen aber nicht explizit gebilligt werden.

#### Das Aus für Freifunk?
Sollte die Kommission entscheiden, dass auch WLAN-fähige Geräte unter diese Definition fallen, würde dies weitreichende Konsequenzen haben. Zum Beispiel basiert die [Freifunk-Initiative](https://freifunk.net/) auf der Verwendung von existierenden Routern mit alternativer, freier Software. Ein Verbot dieser Art der Verwendung würde Freifunk die technische Grundlage entziehen. Dies gefährdet auch das soziale Engagement von vielen Freifunk-Communities, die [unter anderem auch Unterkünfte von Geflüchteten mit Internet versorgen](http://www.golem.de/news/freifunk-kostenloses-internet-fuer-fluechtlinge-1509-116249.html).

Auch Amateurfunker sind potentiell von dem Verbot betroffen. Zwar sind gewisse Geräte für Funkamateure explizit von der Richtlinie ausgenommen (siehe [Anhang 1 der Richtlinie](http://eur-lex.europa.eu/legal-content/DE/TXT/HTML/?uri=CELEX:32014L0053&from=DE)), aber auch Funkamateure verwenden teilweise modifizierte WLAN-Router, um zum Beispiel Kommunikation in so genannten [HAMNETs](https://de.wikipedia.org/wiki/HAMNET) zu ermöglichen.

Sogar alternative Betriebssysteme wie Linux oder BSD für PCs und CyanogenMod oder Replicant für Android-Geräte könnten betroffen sein, da auch sie eigene Software für die Interaktion per WLAN nutzen.

####Mehr Schaden als Nutzen?
Der EU scheint dieses Risiko bewusst zu sein: In § 19 der Erwägungsgründe der Richtlinie heißt es:

>„Die Überprüfung der Konformität von Kombinationen aus Funkanlagen und Software durch die Funkanlagen selbst sollte nicht dazu missbraucht werden, die Verwendung der Anlagen mit Software von unabhängigen Anbietern zu verhindern.“

Doch eine explizite Abwägung zwischen Schaden und Nutzen der Regulierung bestimmter Klassen von Geräten ist nicht vorgesehen. Stattdessen wird darauf verwiesen, dass die Kommission bestimmen kann, welche Geräte reguliert werden sollen und die Kommission diese Abwägung dann wohl schon vornehmen wird. Der scheinbar beruhigende Text in § 19 steht außerdem im Widerspruch zum Erwägungsgrund in § 16:

> „Die Konformität einiger Kategorien von Funkanlagen […] kann durch die Integration von Software oder durch Änderungen der bestehenden Software beeinträchtigt werden. Ein Laden von Software durch den Benutzer, die Funkanlage selbst oder einen Dritten sollte nur möglich sein, wenn dies keine Beeinträchtigung der Konformität […] zur Folge hat.“

Der eigentliche Gesetzestext löst diesen Widerspruch nicht auf. Leider sind außerdem die Entscheidungsprozesse innerhalb der Kommission alles andere als transparent. Daher ist die demokratische Einflussnahme auf ihre Entscheidungen schwierig.


#### Jetzt handeln!
*   Für die Umsetzung der EU-Richtlinie in Deutschland gibt es Gestaltungsspielräume. Darum lohnt es sich, **mit Abgeordneten über kritische Punkte der Richtlinie** zu sprechen, zum Beispiel über die Folgen der Richtlinie für Freifunk, freie Software-Projekte und die Abhängigkeit von Anbieter.innen in Puncto Sicherheit und Gerätehoheit.
*   Eine konkrete Frage der Umsetzung ist Artikel 3.3 der Richtlinie 2014/53/EU: Darf der eigene WLAN-Router weiterhin mit eigener Software betrieben werden?
*   Auch die **Hersteller** werden von der Umsetzung der Richtlinie betroffen sein. Hier ist es angebracht darüber zu sprechen, wie Hersteller Artikel 3.3 umsetzten wollen.
*   **Informieren Sie Ihre Freund.innen, Bekannten und Kolleg.innen** über die  EU-Richtlinie und deren Folgen.
*    [weitere Handlungsvorschläge von der EU-Parlamentarierin Julia Reda](https://juliareda.eu/2015/10/liebe-bundesregierung-macht-freifunk-nicht-kaputt/)

#### Weiterführende Links

*   [Daniel AJ Sokolov (heise.de): Funkregulierung: Angriff auf alternative Software](http://www.heise.de/newsticker/meldung/Funkregulierung-Angriff-auf-alternative-Software-2803189.html)
*   [Julia Reda: Liebe Bundesregierung, macht Freifunk nicht kaputt](https://juliareda.eu/2015/10/liebe-bundesregierung-macht-freifunk-nicht-kaputt/)
*   [netzpolitik.org: Der lange Weg des Routerzwangs zur Endgerätefreiheit](https://netzpolitik.org/2015/der-lange-weg-des-routerzwangs-zur-endgeraetefreiheit/)
*   [FSFE: Verbändeschreiben gegen Routerzwang](https://fsfe.org/news/2015/news-20151028-01.html)


Im Original erschienen auf [digitalcourage.de](https://digitalcourage.de/blog/2015/angriff-auf-freie-software-eu-richtlinie-schraenkt-geraetehoheit-ein)

Dieser Text steht unter der Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

Autoren: Max Maass und Sebastian Lisken ([AG Text](https://digitalcourage.de/blog/2015/ag-text-jetzt-mitmachen)), mit Dank an [Freifunk Darmstadt](https://darmstadt.freifunk.net) und [Freifunk Bielefeld](http://www.freifunk-bielefeld.de/) für Hinweise und Korrekturen.





