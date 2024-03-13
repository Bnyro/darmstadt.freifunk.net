---
template: "blog_entry.html"
title: "Aufteilung des Darmstädter Freifunk-Netzes"
date: 2018-09-20 12:00:00
categories: community
---

Das Wachstum der letzten Jahre ist technisch nicht Spurlos am Freifunk-Netz vorbeigegangen. Um weiter wachsen zu können und Ressourcen besser auszunutzen wird das Netz in den kommenden Wochen in Domains aufgeteilt.

<!-- more -->

[![Domainkarte von Freifunk Darmstadt]({{ "/images/posts/2018-09-20-ankuendigung-multidomain/karte.png" | prepend: site.baseurl }})]({{ "/mitmachen/domains" | prepend: site.baseurl }})

## Technischer Hintergrund
Das Freifunk-Netz ist technisch gesehen ein großes Layer 2 (Ethernet) Netzwerk. Man kann sich das Freifunk-Netz also wie einen übergroßen Switch vorstellen, an dem alle Teilnehmer (Nutzer wie Knoten) angeschlossen sind. Damit alle Knoten das Wissen besitzen um Daten in die richtige Richtung zu senden müssen in regelmäßigen Abständen alle Knoten eine Nachricht aussenden, die bestätigt, dass sie noch Teil des Netzes sind. Dieser und noch weitere Management-Datenverkehre (ARP, NDP) sind im Falle unseres Netzes nun bei etwa 170 kbit/s, die an jedem Knoten anfallen, in der täglichen Spitze angekommen. Das macht sich auch im monatlichen Trafficvolumen mit rund 30 TB bemerkbar.

![Grundlast im derzeitigen Freifunk Darmstadt Netz]({{ "/images/posts/2018-09-20-ankuendigung-multidomain/graph_legacy.png" | prepend: site.baseurl }})

Ein Aufteilen des Netzes in mehrere Domains führt zu einer drastischen Reduzierung dieses Datenverkehrs, da Routinginformationen an viel weniger Knoten verteilt werden müssen.

Für die Freifunker in Babenhausen ist diese Migration bereits erfolgt. Der Management-Datenverkehr ist infolge dessen auf etwa 15-20 Kbit/s gefallen.

![Grundlast in der domain "Babenhausen (Hessen)"]({{ "/images/posts/2018-09-20-ankuendigung-multidomain/graph_multidomain.png" | prepend: site.baseurl }})

Die entstehenden Domains werden alle mit eine ähnliche Knotenzahl verkehren, daher ist eine Reduktion um etwa Faktor 10 an jedem Knoten zu erwarten.

## Domainauswahl & Meshfähigkeit
Freifunker, welche einen neuen Knoten flashen werden bereits seit Firmware v1.2.3 zur Auswahl einer solchen Domain aufgefordert. Bei der Aufteilung haben wir uns im Darmstädter Umland an Postleitzahlgebieten, innerhalb Darmstadts an den Wahlbezirken orientiert.

Jeder eingezeichnete Bereich entspricht einer solchen Domain. Benachbarte Domains, welche die gleiche Farbe aufweisen teilen sich ein gemeinsames Subnetz und können somit untereinander meshen. Mit der feineren Benennung und Aufteilung innerhalb einer Farbe halten wir uns die Möglichkeit offen, in Zukunft auf einfache Weise weiter zu segmentieren.

## Automatische Migration

In den nächsten Wochen werden wir Knoten, die eine aktuelle Stable-Firmware (1.2.4 und neuer) einsetzen automatisch eine passende Zieldomaine zuweisen, da wir nicht erwarten, dass wir in der gebotenen Kürze der Migration jeden Betreiber erreichen und zur manuellen Rekonfiguration bewegen können.
Die Automatische Migration erfolgt dann zu einem programmierten Zeitpunkt, damit vorhandene Mesh-Netze gleichzeitig rekonfiguriert werden, so dass nur eine kurzzeitige Unterbrechung entsteht.

Für die automatische Domainmigration beziehen wir automatisch die BSSID und Empfangsstärke benachbarter WLAN-Netze von den Knoten, die wir ausschließlich für die temporäre Geolokalisierung der Knoten verwenden und nicht dauerhaft speichern. Dies ist notwendig, da wir für eine große Menge von Knoten keinerlei Positioninformationen kennen, diese aber grob bekannt sein müssen um die passende Zieldomaine auszuwählen. Sollten keine WLAN-Netze in der Nähe sein, so wird die Position des Knotens auf der Karte herangezogen.

Zuerst werden am kommenden Freitag (22.09.) gegen 10 Uhr eine kleine Anzahl an Knoten mit der aktuellen Experimental-Firmware migriert werden. Eine Woche später (29.09.) folgen dann alle weiteren Knoten.

## Manuelle Migration

Falls du schon heute in deine Zieldomain wechseln möchtest, kannst du dies einfach über den [Konfigurationsmodus](https://darmstadt.freifunk.net/was-ist-freifunk/faq/#wie-kann-ich-nachtr%C3%A4glich-%C3%A4nderungen-am-router-vornehmen) tun. Dort ist ab sofort ein Drop-Down-Menü mit der Domainauswahl zu finden.

## Häufige Fragen
### Was passiert, sollte mein Freifunk-Knoten am Stichtag ausgeschaltet sein?
In diesem Fall muss unterschieden werden, ob dein Knoten eine Verbindung zu unseren Gateways aufbaut oder ob dieser ein reiner Mesh-Knoten ist.

Sollte dein Knoten eine Verbindung zu unseren Gateways haben, wird dieser innerhalb von 24 Stunden seine Zieldomäne erfragen und in diese wechseln.

Ist dein Knoten ein reiner Mesh-Knoten, so kommt es darauf an, ob dieser bereits Firmware 1.2.4 hat und damit im Freifunk-Netz war oder nicht. War der Knoten bereits im Netz und hat seine Zieldomäne bezogen, so wechselt er innerhalb von 7 Stunden automatisch in seine Zieldomäne. Während dieses Zeitraums ist der Knoten allerdings offline!

Sollte dein Knoten noch mit einer älteren Firmware laufen, so ist eine Aktualisierung sowie manuelle Einstellung der Domain nötig. Aktualisiere hierfür über den Config-Mode zuerst die Firmware. Anschließend kannst du, ebenda, deine zugehörige Domäne auswählen.

### Was ist mit bestehenden Mesh-Netzen?
Wir beachten aktuell bestehende Mesh-Verbindungen und behalten diese auch während der Migration bei. Für den Fall dass ein Mesh zwischen zwei Knoten in Unterschiedlichen Domänen existiert, so werden beide Knoten in die gleiche Zieldomäne zugeordnet.

### Was ist nach der Umstellung zu beachten
Für Clients passiert die Umstellung weitgehend unbemerkt. Allerdings werden nun IPv6-Adressen mit einem anderen Präfix vergeben. Damit ändert sich auch die IP-Adresse deines Knotens. Die neue IP_adresse deines Knotens kannst du auf unserer Karte in Erfahrung bringen.

