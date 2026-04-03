# 🛡️ Cybersecurity Cheatsheet – Filip Pasti

> 📚 TryHackMe Pre-Security Path  
> Regel: Nur eintragen, was ich selbst verstanden habe und in eigenen Worten erklären kann.

---

# 📑 Inhaltsverzeichnis

1. [Introduction to Cyber Security](#1--introduction-to-cyber-security)
2. [Network Fundamentals](#2--network-fundamentals)
3. [How The Web Works](#3--how-the-web-works)
4. [Linux Fundamentals](#4--linux-fundamentals)
5. [Windows Fundamentals](#5--windows-fundamentals)
6. [Fortschritt – TryHackMe Pre-Security Path](#--fortschritt--tryhackme-pre-security-path)

---

# 1. 🔐 Introduction to Cyber Security

## Was ist Cyber Security?

Cyber Security beschäftigt sich mit dem Schutz von digitalen Systemen, Netzwerken und Daten vor unbefugtem Zugriff oder Angriffen.  
Ziel ist es Vertraulichkeit, Integrität und Verfügbarkeit von Informationen sicherzustellen.

---

## CIA Triad

| Prinzip | Bedeutung |
|-------|-----------|
| **Confidentiality** | Daten nur für Berechtigte zugänglich |
| **Integrity** | Daten dürfen nicht unbemerkt verändert werden |
| **Availability** | Systeme müssen verfügbar sein, wenn man sie braucht |

---

## Offensive vs Defensive Security

### 🔴 Offensive Security (Red Team)

Offensive Security ist es zu denken wie ein Hacker, um Schwächen im System oder Netzwerk zu finden, bevor ein echter Angreifer sie ausnutzt.

### 🔵 Defensive Security (Blue Team)

Defensive Security ist der Prozess, Geräte und Systeme mit Sicherheitsmaßnahmen zu schützen.

---

## Karrierewege in Cyber Security

| Rolle | Beschreibung |
|------|-------------|
| **Security Analyst** | Security Analysten überwachen, untersuchen und reagieren auf Aktivitäten, welche im System und auf Geräten von Organisationen bzw. Unternehmen auftauchen, um Sicherheit zu gewährleisten |
| **Security Engineer** | Security Engineers entwickeln und warten Systeme und Prozesse, die das Netzwerk und die Geräte einer Organisation schützen |
| **Pentester** | Pentester sind dafür zuständig, die Sicherheit der Systeme und Software eines Unternehmens zu überprüfen, indem sie versuchen auf sichere Weise in diese einzudringen |

---

# 2. 🌐 Network Fundamentals

## Was ist ein Netzwerk?

Ein Netzwerk bedeutet die „Dinge die miteinander verknüpft sind“.  
Im Computing bedeutet es einfach die Verknüpfung technischer Geräte wie z. B. Computer oder Smartphones.

---

## Was ist das Internet?

Das Internet ist ein riesiges Netzwerk, worin weitere kleinere Netzwerke eingegliedert sind.

- Kleine Netzwerke = **private Netzwerke**
- Netzwerke, welche diese miteinander verbinden = **öffentliche Netzwerke**

---

## IP- und MAC-Adresse

### IP Adresse

Eine **IP-Adresse (Internet Protocol)** ist ein Set von Nummern, welches in **4 Oktets (0–255)** unterteilt ist.

Die Nummer wird durch eine Technik namens **IP Addressing & Subnetting** berechnet.

- **Public IP** → identifiziert ein Gerät im Internet  
- **Private IP** → identifiziert Geräte innerhalb eines lokalen Netzwerks

### MAC Adresse

Eine **MAC-Adresse (Media Access Control)** ist eine **12-stellige Hexadezimalzahl**.

Sie besteht aus zwei Teilen:

| Teil | Bedeutung |
|-----|----------|
| Erster Teil | Hersteller des Network Interfaces |
| Zweiter Teil | Einzigartige Adresse des Network Interfaces |

---

## Spoofing (MAC Adresse)

Spoofing bedeutet, dass ein Gerät vortäuscht ein anderes Gerät zu sein, indem es dessen MAC-Adresse benutzt.

---

## Ping

Der **Ping** benutzt **ICMP-Pakete**, um die Performance zwischen Geräten zu messen.

Die Zeit wird in **Millisekunden (ms)** gemessen.

---

## LAN Topologien und Geräte

**LAN-Topologie = Aufbau oder Design eines Netzwerks**

### Netzwerk-Topologien

| Topologie | Beschreibung |
|----------|-------------|
| **Star Topology** | Alle Geräte über ein zentrales Gerät (Switch/Hub) verbunden → zuverlässig und leicht erweiterbar, aber teurer |
| **Bus Topology** | Alle Geräte an einem Hauptkabel → billig und einfach, aber langsam bei viel Traffic |
| **Ring Topology** | Geräte in einem Kreis verbunden → Daten laufen durch Geräte weiter |

---

### Netzwerkgeräte

| Gerät | Funktion |
|------|----------|
| **Switch** | Verbindet viele Geräte im Netzwerk und schickt Daten nur an das richtige Gerät |
| **Router** | Verbindet verschiedene Netzwerke miteinander und leitet Daten zwischen ihnen weiter |

---

## Subnetting

Subnetting bedeutet, Netzwerke in kleinere Netzwerke aufzuteilen.

Es benutzt drei Arten von Adressen:

| Typ | Bedeutung |
|----|-----------|
| **Network Address** | Identifiziert den Start eines Netzwerkes |
| **Host Address** | Identifiziert ein Gerät im Subnetz |
| **Default Gateway** | Adresse eines Geräts, das Daten aus dem lokalen Netzwerk in andere Netzwerke weiterleitet |

---

## ARP (Address Resolution Protocol)

ARP verbindet eine **IP-Adresse mit der passenden MAC-Adresse** im Netzwerk.

Geräte speichern diese Zuordnung in einer **ARP-Tabelle**.

| Prozess | Beschreibung |
|-------|-------------|
| **ARP Request** | Gerät fragt: „Welche MAC-Adresse gehört zu dieser IP?“ |
| **ARP Reply** | Gerät mit dieser IP antwortet mit seiner MAC-Adresse |

---

## DHCP (Dynamic Host Configuration Protocol)

IP-Adressen können **manuell** oder **automatisch** vergeben werden.

Dafür ist **DHCP** zuständig.

### DHCP Ablauf

1. **Discover** → Gerät sucht einen DHCP Server  
2. **Offer** → Server bietet eine IP-Adresse an  
3. **Request** → Gerät akzeptiert die IP  
4. **ACK** → Server bestätigt die IP

---

## OSI Modell (Open Systems Interconnection Model)

Das Modell liefert ein Framework, das beschreibt, wie Geräte Daten senden, empfangen und interpretieren.

Es besteht aus **7 Layern**:

| Layer | Funktion |
|------|----------|
| **Physical** | Physische Hardware Komponenten |
| **Data Link** | Physische Adressierung über MAC-Adressen |
| **Network** | Routing und IP-Adressen |
| **Transport** | Datenübertragung über TCP oder UDP |
| **Session** | Aufbau und Verwaltung von Verbindungen |
| **Presentation** | Datenübersetzung und Verschlüsselung |
| **Application** | Schnittstelle zwischen Benutzer und Netzwerk |

---

### Transport Layer Protokolle

#### TCP (Transmission Control Protocol)

- zuverlässig  
- garantiert korrekte Reihenfolge  
- Fehlerprüfung integriert  
- langsamer aber sicher

#### UDP (User Datagram Protocol)

- schnell  
- keine Garantie für Zustellung  
- geeignet für Streaming oder Echtzeit-Anwendungen

---

# 3. 🌍 How The Web Works

*(wird ergänzt)*

---

# 4. 🐧 Linux Fundamentals

*(wird ergänzt)*

---

# 5. 🪟 Windows Fundamentals

*(wird ergänzt)*

---

# ✅ Fortschritt – TryHackMe Pre-Security Path

| Modul | Status | Abgeschlossen am |
|------|--------|----------------|
| Introduction to Cyber Security | ✅ | 02.04.2026 |
| Network Fundamentals | ✅ | 03.04.2026 |
| How The Web Works | ⬜ | – |
| Linux Fundamentals Part 1 | ⬜ | – |
| Linux Fundamentals Part 2 | ⬜ | – |
| Linux Fundamentals Part 3 | ⬜ | – |
| Windows Fundamentals Part 1 | ⬜ | – |
| Windows Fundamentals Part 2 | ⬜ | – |
| Windows Fundamentals Part 3 | ⬜ | – |

⬜ Offen  
🟡 In Bearbeitung  
✅ Fertig

---

*Zuletzt aktualisiert: –*
