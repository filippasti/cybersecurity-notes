# 🛡️ Cybersecurity Cheatsheet – Filip Pasti
> TryHackMe Pre-Security Path  
> Regel: Nur eintragen was ich selbst verstanden und in eigenen Worten erklären kann.

---

## 📑 Inhaltsverzeichnis
1. [Introduction to Cyber Security](#1--introduction-to-cyber-security)
2. [Network Fundamentals](#2--network-fundamentals)
3. [How The Web Works](#3--how-the-web-works)
4. [Linux Fundamentals](#4--linux-fundamentals)
5. [Windows Fundamentals](#5--windows-fundamentals)
6. [Tools Übersicht](#6-️-tools-übersicht)
7. [Begriffe & Definitionen A–Z](#7--begriffe--definitionen-az)

---

## 1. 🔐 Introduction to Cyber Security

### Was ist Cyber Security?
Cyber Security beschäftigt sich mit dem Schutz von digitalen Systemen, Netzwerken und Daten vor unbefugtem Zugriff oder Angriffen. Ziel ist es Vertraulichkeit, Integrität und Verfügbarkeit von Informationen sicherzustellen.

### CIA Triad: 
Confidentiality: Daten nur für Berechtigte zugänglich
Integrity: Daten dürfen nicht unbemerkt verändert werden
Availability: Systeme müssen verfügbar sein wenn man sie braucht


### Offensive vs. Defensive Security

| | Offensive (Red Team) |
-> Offensive Security ist es zu denken wie ein Hacker um Schwächen im System/Netzwerk zu finden bevor der Hacker es tut.

| Defensive (Blue Team) |
-> Defensive Security ist der Prozess Geräte und Systeme zu mit gewissen Maßnahmen zu beschützen.

### Karrierewege in Cyber Security

| Rolle | Was man macht |
|-------|--------------|
| Seurity Analyst | Security Analysten überwachen, untersuchen und reagieren auf Aktivitäten, welche im System und auf Geräten von                              Organsisationen bzw. Unternehmen auftauchen, um eine Sicherheit zu gewährleisten |
| Security Engineer | Security Engineers entwickeln und warten Systeme und Prozesse, die das Netzwerk und die Geräte einer Organisation                           schützen |
| Pentester | Pentester sind dafür zuständig, die Sicherheit der Systeme und Software eines Unternehmens zu überprüfen, indem er                           versucht, auf sichere Weise in diese einzudringen. |

--------------------------------------------------------------------------------------------------------------------------------------------

## 2. 🌐 Network Fundamentals

### Was ist ein Netzwerk?
Ein Netzwerk bedeuet die "Dinge die miteinander verknüpft sind". Im Computing bedeutet es einfach die Verknüpfung technischer Geräte wie z.B. Computer, Smartphones etc.

### Was ist das Internet?
Das Internet ist ein riesiges Netwerk, worin weitere kleinere Netwerke eingegliedert sind. Die kleinen Netzwerke werden als private Netzwerke bezeichnet, wobei die Netzwerke, welche die kleineren Netzwerke miteinander verknüpfen öffentlich (public) Netwerke heißen.

### IP- und MAC-Adresse
Eine IP - Adresse (Internet Protocol) ist ein Set von Nummern, welche in 4 Oktets unterteilt sind (gehen von 0-255). Die Nummer wird durch eine Technik namens IP Adressing & Subnetting berechnet. Eine öffentliche IP Adresse wird benutzt um ein Gerät im Internet zu erkennen. Eine private IP Adresse wird verwendet um die Geräte untereinander zu identifizieren.
Eine MAC - Adresse (Media Access Control) ist eine zwölfstellige Hexadezimalzahl. Sie ist in zwei Teile unterteilt und wird mit Doppelpunkten unterteilt. Der erste Teil gibt an, von welchem Anbieter das Network Interface erstellt wurde. Der zweite Teil ist eine einzigartige Adresse vom Network Interface.

### Spoofing (MAC Adresse):
Spoofing bedeutet es, wenn ein Gerät vortäuscht eine anderes Gerät zu sein, indem es seine MAC Adresse benutzt.

### Ping: 
Der Ping benutzt ICMP Pakete, um die Performance zwischen Geräten zu messen. Diese Zeit wird in ms gemessen  


### LAN Topologies und Geräte: 
LAN-Topologie = Aufbau/Design eines Netzwerks.

Star Topology: Alle Geräte über ein zentrales Gerät (Switch/Hub) verbunden. → zuverlässig und leicht erweiterbar, aber teurer und Ausfall des Zentrums legt alles lahm.

Bus-Topologie: Alle Geräte an einem Hauptkabel. → billig und einfach, aber langsam bei viel Traffic und Kabelbruch stoppt alles.

Ring-Topologie: Geräte in einem Kreis verbunden. → Daten laufen durch Geräte weiter, leicht zu diagnostizieren, aber ein Defekt kann das ganze Netzwerk stoppen.

Switch: Verbindet viele Geräte im Netzwerk und schickt Daten nur an das richtige Gerät → effizienter als ein Hub.
Router: Verbindet verschiedene Netzwerke miteinander und leitet Daten zwischen ihnen weiter (Routing).

### Subnetting: 
Subnetting bedeutet es, Netzwerke in immer kleinere Netzwerke aufzuteilen. ESubnetting benutzt 3 verschiedene Arten von IP Adressen:
Network Address: Identifiziert den Start eines Netzwerkes und wird benutzt um die Existenz eines Netzwerks zu bestätigen
Host Address: Wird benutzt um ein Gerät um Subnet zu identifizieren
Default Gateway: ist die Adresse eines Geräts, das Daten aus deinem lokalen Netzwerk in andere Netzwerke weiterleitet

### ARP (Address Resolution Protocol):
Verbindet eine IP Adresse mit der passenden MAC Adresse im Netzwerk. Geräte speichern dabei diese Zuordnung in einer ARP Tabelle
ARP Request: Bei einer ARP-Request fragt ein Gerät im Netzwerk: „Welche MAC-Adresse gehört zu dieser IP?“
ARP Reply: Das Gerät mit dieser IP antwortet mit seiner MAC-Adresse, und die Zuordnung wird im ARP-Cache gespeichert.

### DHCP (Dynamic Host Configuration Protocol):
IP-Adressen können manuell vergeben werden. Sie können auch automatisch vergeben werden. Dafür ist DHCP zuständig. 
Ablauf bei DHCP:
1. Discover – Gerät sucht einen DHCP-Server.
2. Offer – Server bietet eine IP-Adresse an.
3. Request – Gerät akzeptiert die IP.
4. ACK – Server bestätigt → Gerät nutzt die IP.

### OSI Modell (Open Systems Interconnections Model):
Das Modell liefert ein Framework, das vorschreibt, wie alle vernetzten Geräte Daten senden, empfangen und interpretieren. Es besteht aus 7 Layern (Physical, Data Link, Network, Transport, Session, Presentation, Application)
Physical: Physische Komponenten von Hardware in einem Network werden hier angegeben

Data Link: Verantwortlich für die physische Adressierung; fügt den vom Network Layer erhaltenen Paketen die MAC-Adresse des Empfängers hinzu und steuert die Kommunikation über die Network Interface Card (NIC) mit eindeutiger MAC-Adresse.

Network: Verantwortlich für Routing und das Zusammensetzen von Datenpaketen; entscheidet den optimalen Pfad anhand von Kriterien wie kürzester Weg, Zuverlässigkeit und Geschwindigkeit der Verbindung. Arbeitet mit IP-Adressen und verwendet Layer-3-Geräte wie Router. Protokolle wie OSPF und RIP steuern die Pfadauswahl.

Transport: Verantwortlich für die zuverlässige oder schnelle Übertragung von Daten zwischen Geräten. Verwendet zwei Hauptprotokolle:
	TCP (Transmission Control Protocol):
	•	Zuverlässig, garantiert die korrekte Reihenfolge der Daten und integriert Fehlerprüfung.
	•	Reserviert eine ständige Verbindung zwischen den Geräten während der Übertragung.
	•	Geeignet für Dateiübertragungen, E-Mails und Web-Browsing.
	•	Nachteile: langsamer, aufwändiger, Verbindung kann andere Geräte blockieren.
	UDP (User Datagram Protocol):
	•	Schnell, aber unzuverlässig; keine Garantie, dass Daten ankommen oder in der richtigen Reihenfolge sind.
	•	Nutzt keine dauerhafte Verbindung und überlässt der Anwendung die Kontrolle über Paketfluss.
	•	Geeignet für Streaming, ARP/DHCP und andere Anwendungen, bei denen kleinere Datenverluste akzeptabel sind.

Session: Verantwortlich für das Erstellen, Aufrechterhalten und Beenden von Verbindungen (Sessions) zwischen Computern. Enthält Mechanismen wie Checkpoints, sodass bei Datenverlust nur die neuesten Daten erneut gesendet werden müssen. Jede Session ist einzigartig, Daten reisen nur innerhalb der jeweiligen Verbindung.

Presentation: Verantwortlich für die Standardisierung und Übersetzung von Daten zwischen unterschiedlichen Anwendungen, sodass verschiedene Softwarearten dieselben Daten korrekt interpretieren können. Führt auch Sicherheitsfunktionen wie Datenverschlüsselung (z. B. HTTPS) durch.

Application: Stellt die Schnittstelle zwischen Benutzer und Netzwerk dar. Regelt, wie Daten gesendet, empfangen und dargestellt werden. Beinhaltet Anwendungen wie E-Mail-Clients, Browser oder Dateiübertragungssoftware sowie Protokolle wie DNS zur Übersetzung von Domainnamen in IP-Adressen.


--------------------------------------------------------------------------------------------------------------------------------------------


## 3. 🌍 How The Web Works

### Was passiert wenn du eine Webseite aufrufst?
```
1.
2.
3.
4.
5.
```

### HTTP Request-Methoden

| Methode | Zweck |
|---------|-------|
| | |
| | |
| | |
| | |

### HTTP Status Codes

| Code | Bedeutung |
|------|-----------|
| | |
| | |
| | |
| | |
| | |

### HTTP vs. HTTPS

| | HTTP | HTTPS |
|---|---|---|
| **Verschlüsselung** | | |
| **Port** | | |
| **Sicher?** | | |

### Begriffe aus diesem Modul

| Begriff | Bedeutung |
|---------|-----------|
| | |
| | |
| | |
| | |
| | |

---

## 4. 🐧 Linux Fundamentals

### Navigation & Dateisystem

| Befehl | Was er macht | Beispiel |
|--------|-------------|---------|
| | | |
| | | |
| | | |
| | | |
| | | |
| | | |

### Wichtige Linux-Verzeichnisse

| Pfad | Inhalt |
|------|--------|
| | |
| | |
| | |
| | |

### Dateirechte

```
-rwxrw-r--
```

| Recht | Buchstabe | Zahl |
|-------|-----------|------|
| | | |
| | | |
| | | |

### Netzwerk-Befehle

| Befehl | Was er macht |
|--------|-------------|
| | |
| | |
| | |
| | |

### Begriffe aus diesem Modul

| Begriff | Bedeutung |
|---------|-----------|
| | |
| | |
| | |
| | |
| | |

---

## 5. 🪟 Windows Fundamentals

### Wichtige Verzeichnisse

| Pfad | Inhalt |
|------|--------|
| | |
| | |
| | |

### Nützliche CMD-Befehle

| Befehl | Was er macht |
|--------|-------------|
| | |
| | |
| | |
| | |

### Begriffe aus diesem Modul

| Begriff | Bedeutung |
|---------|-----------|
| | |
| | |
| | |
| | |

---

## 6. 🛠️ Tools Übersicht

| Tool | Kategorie | Wofür | Beispielbefehl |
|------|-----------|-------|---------------|
| | | | |
| | | | |
| | | | |
| | | | |
| | | | |

---

## 7. 📚 Begriffe & Definitionen A–Z

| Begriff | Erklärung in eigenen Worten |
|---------|----------------------------|
| | |
| | |
| | |
| | |
| | |

---

## ✅ Fortschritt – TryHackMe Pre-Security Path

| Modul | Status | Abgeschlossen am |
|-------|--------|-----------------|
| Introduction to Cyber Security | ⬜ | – |
| Network Fundamentals | ⬜ | – |
| How The Web Works | ⬜ | – |
| Linux Fundamentals Part 1 | ⬜ | – |
| Linux Fundamentals Part 2 | ⬜ | – |
| Linux Fundamentals Part 3 | ⬜ | – |
| Windows Fundamentals Part 1 | ⬜ | – |
| Windows Fundamentals Part 2 | ⬜ | – |
| Windows Fundamentals Part 3 | ⬜ | – |

> ⬜ Offen | 🟡 In Bearbeitung | ✅ Fertig

---
*Zuletzt aktualisiert: –*
