---
template: "blog_entry.html"
title: "Mehr Sicherheit in der Luft - WPA3 für unsere Firmware"
date: 2020-03-27 00:00:00
categories: community
---

Mit unserer [aktuellen Firmware im testing Zweig](https://firmware.darmstadt.freifunk.net/) rollen wir gleich zwei neue Features aus, welche erstmals die im Freifunk Client-Netz übertragenen Daten gegen passives Mitlesen absichern und dein privates WLAN noch besser schützen.

<!-- more -->

## WPA3 für euer privates WLAN

Die „Private WLAN“ Funktion der Freifunk Firmware unterstützt nun zusätzliche zu WPA2 die Verschlüsselung mittels [WPA3](https://de.wikipedia.org/wiki/Wi-Fi_Protected_Access). Dieser neue Standard sichert durch ein neues Schlüsseltauschverfahren dein WLAN Kennwort besser vor [Brute-Force Angriffen](https://de.wikipedia.org/wiki/Brute-Force-Methode).

Angreifer können bei der ausschließlichen Verwendung von WPA3 keine Offline-Angriffe mehr durchführen. Offline bedeutet hier, dass auf den mitgeschnittenen Handshake keine [Brute-Force-](https://de.wikipedia.org/wiki/Brute-Force-Methode) oder [Wörterbuchangriffe](https://de.wikipedia.org/wiki/W%C3%B6rterbuchangriff) möglich sind.

Um WPA3 für dein privates WLAN zu aktivieren musst du deinen Freifunk Knoten in den [Konfigurationsmodus]({{ "/was-ist-freifunk/faq" | prepend: site.baseurl }}) bringen. Dort findest du zusätzlich zu den Einstellungen für Netzwerkname und Kennwort nun auch die Einstellungen für WPA3.

![]({{ "/images/posts/2020-03-27-private-wifi.png" | prepend: site.baseurl }})


WPA3 wird auf den folgenden Plattformen unterstützt:

 - **iOS** (ab Version 13)
 - **Android** (ab Version 10)

Zusätzlich zu den mobilen Betriebssystemen unterstützen folgende Desktop-Betriebssysteme WPA3 teilweise.

### Windows

Windows 10 unterstützt WPA3 **ab Version Mai 2019**, wenn eine kompatible WLAN Karte mit aktuellem Treiber vorhanden ist.

Intel stellt hierfür eine [Übersicht auf ihrer Webseite bereit](https://www.intel.de/content/www/de/de/support/articles/000054783/network-and-i-o/wireless-networking.html).

Für eine Qualcomm QCA6174/QCA9377 findest du den aktuellen Treiber auf der Seite [dieses OEM](https://support.killernetworking.com/download/killer-inf-package/).

Die Realtek RTL8822BE/CE scheint ebenfalls WPA3 Kompatibilität aufzuweisen. Den Treiber hierfür erhältst du beim Hersteller deines Computers.

### MacOS

MacOS X unterstützt WPA3 teilweise **ab Catalina**. Für eine vollständige Unterstützung benötigt dein Mac eine WLAN-Karte welche den [802.11ac](https://de.wikipedia.org/wiki/IEEE_802.11ac)-Standard unterstützt. Sollte dein Mac nur [802.11n](https://de.wikipedia.org/wiki/IEEE_802.11n) unterstützen, so funktioniert WPA3 nur mit ausgeschalteter Management Frame Protection (mehr dazu im nächsten Absatz).

### Linux

Die meisten Linux Distributionen unterstützen WPA3 in aktuellen Releases. Bei [Ubuntu](https://ubuntu.com/download) ist dies beispielsweise ab Version 19.04 der Fall. Auch hier hängt die Kompatibilität von eurer WLAN-Karte ab.

## Management Frame Protection (802.11w)

Mit WPA3 wird die Management Frame Protection zu einer Voraussetzung. Mit MFP wird die WLAN-Verbindung vor Management-Frame-Attacken geschützt, bei denen ein Angreifer die WLAN-Verbindung zwischen Access Point und Client ohne Kenntnis des WLAN-Kennwortes trennen kann.

Sollte der Angreifer das WLAN-Kennwort noch nicht kennen zwingt er bei dieser Attacke euren Client dazu, sich neu zu verbinden. Bei WPA2 erhält er dadurch einen weiteren Handshake der für einen Offline-Angriff herangezogen werden kann.

Mit Management Frame Protection ist eure WLAN-Verbindung so abgesichert, dass lediglich Client und Access Point derartige Pakete austauschen können.

Mangement Frame Protection ist ein relativ neues Feature, welches erst mit 802.11ac verpflichtend zur Zertifizierung bei der WiFi Alliance benötigt wurde. Aus diesem Grund wird WPA3 meistens erst mit WLAN Karten dieses Standards unterstützt.

Management Frame Protection kann entweder optional oder Voraussetzung für eine Clientverbindung sein. Bei WPA3 empfiehlt es sich, Managemen Frame Protection verpflichtend zu aktivieren. Solltest du ausschließlich WPA2 oder WPA2/WPA3 im gemeinsamen Modus verwenden, so ist es empfehlenswert, Management Frame Protection optional zu aktivieren.

## Enhanced Open (OWE)

Zusätzlich zu den Verbesserungen für euer privates Netz testen wir mit der aktuellen Firmware Enhanced Open für das Freifunk-Client-Netz. Hiermit wird erstmals der Datenverkehr zwischen Access Point und Client im Freifunk-Netz gegen passives Mitlesen abgesichert. Enhanced Open verwendet ebenfalls Management Frame Protection um die Verbindung vor unautorisiertem Beenden zu schützen.

Enhanced Open wird bei uns mit der SSID (WLAN Name) `owe.darmstadt.freifunk.net` ausgestrahlt. OWE steht hierbei für Opportunistic Wireless Encryption.

![]({{ "/images/posts/2020-03-27-owe-list.png" | prepend: site.baseurl }})

Enhanced Open kann auch ohne sichtbare SSID ausgestrahlt werden. Hierbei enthält das unverschlüsselte Freifunk-Client-Netz im Beacon SSID und BSSID eines versteckten Enhanced Open Netzes. Kompatible Clients können sich dann automatisch zu diesem verschlüsselten Netz verbinden.

Da Enhanced Open aktuell noch von sehr wenigen Betriebsystemen unterstützt wird, verzichten wir vorerst auf diesen so genannten Transition Mode. Damit wird die Verschlüsselung mittels Enhanced Open vorerst Opt-In für alle.

Enhanced Open wird aktuell von **Android** ab Version 10 vollständig unterstützt.

**Windows 10**, **iOS** sowie **MacOS X** unterstützen in noch keinem Release WPA3 Enhanced Open.

**Linux** unterstützt WPA3 Enhanced Open mit dem aktuellen hostapd. Die meisten Distributionen verwenden allerdings die Software NetworkManager zum verwalten der WLAN Netze. Für dieses Programm haben wir den Enhanced Open support [eingebaut](https://gitlab.freedesktop.org/NetworkManager/NetworkManager/-/merge_requests/345), allerdings liefert noch keine Linux Distribution eine Version aus, welche Enhanced Open unterstützt. Hiermit ist frühstens Mitte des Jahres zu rechnen.

## Allgemeine Hardwarevorraussetzungen

Alle beschriebenen Features werden von den meisten von der Freifunk-Firmware unterstützten Modellen unterstützt. Einige Geräte verwenden leider inkompatible WLAN Treiber, weswegen eine Unterstützung von WPA3 bei diesen Geräten nicht möglich ist. Diese Geräte sind in der nachfolgenden Liste aufgeführt:

 - D-Link DIR-825 (B1)
 - GL.iNet GL-MT300A
 - GL.iNet GL-MT300N
 - GL.iNet GL-MT750
 - Nexx WT3020AD/F/H
 - TP-Link Archer C2 v1
 - TP-Link Archer C20 (v1)
 - TP-Link Archer C20i
 - TP-Link Archer C25
 - TP-Link Archer C50 v1
 - TP-Link Archer C58
 - TP-Link Archer C60
 - TP-Link TL-WR902 v1
 - TP-Link RE450
 - TP-Link RE450 (v1)
 - Xiaomi MiWiFi Mini
 - ZyXEL WRE6606

Geräte, deren Supportende vor mehr als 2 Jahren angekündigt wurden, unterstützen kein WPA3. Eine vollständige Liste dieser Geräte findest du [hier]({{ "/news/2018/05/16/eol-devices.html" | prepend: site.baseurl }}).

## Deine Erfahrungen sind gefragt!

Da die beschriebenen Techniken sehr neu sind, würde es uns sehr Freuen wenn wenn du uns bei den Tests unterstützt und uns von deinen Erfahrungen mit WPA3 und Enhanced Open erzählst.

Was hat im ersten Anlauf funktioniert? Gab es Probleme? Welche anderen Geräte unterstützen bereits WPA3 oder Enhanced Open? Deine Erfahrungen sind am besten im [Forenthread](https://forum.darmstadt.freifunk.net/t/wpa3-enhanced-open-kompatibalitaet-und-erfahrungen/846) zu diesem Thema aufgehoben.

