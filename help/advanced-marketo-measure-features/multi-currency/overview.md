---
unique-page-id: 27656735
description: Übersicht - [!DNL Marketo Measure] - Produktdokumentation
title: Überblick
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 2%

---

# Überblick {#overview}

Heute [!DNL Marketo Measure] Die Anwendung unterstützt nur eine einheitliche Währung (vorausgesetzt, dass sie USD ist), während wir wissen und wissen, dass wir Kunden auf der ganzen Welt haben, die über ihre eigenen Unternehmens- und Benutzerwährungen berichten müssen. Diese Funktion bietet Benutzern die Möglichkeit, zwischen verschiedenen Währungen zu wechseln, wenn sie entweder die gemeldeten Ausgaben oder Umsätze betrachten.

## Verfügbarkeit {#availability}

Ebene 2 und höher.

## Anforderungen {#requirements}

In [!DNL Salesforce]muss für den Kunden &quot;Mehrere Währungen aktivieren&quot;aktiviert sein. Optional kann der Kunde auch &quot;Ja, ich möchte die erweiterte Währungsverwaltung aktivieren&quot;auswählen.

In Dynamics kann der Kunde in seinen Einstellungen statische Wechselkurse für mehrere Währungen festlegen. In Dynamics gibt es kein Konzept der &quot;erweiterten Währungsverwaltung&quot;.

## Bedingungen {#terms}

| **Begriff** | Beschreibung |
|---|---|
| **Erweiterte Währung** | Für den Kunden sind erweitertes Währungsmanagement und mehrere Währungen aktiviert, was bedeutet, dass er für verschiedene Zeiträume unterschiedliche Konversionsraten haben kann. |
| **Unternehmenswährung** | Dies sind die verschiedenen Währungen, die von einer Organisation im CRM-System aufgeführt und deklariert werden, alle mit Konversionsraten. [!DNL Marketo Measure] werden diese Werte importieren und diese Währungen für Benutzer in unserem Produkt verfügbar machen. |
| **Währungsgebietsschema** | Die für eine Organisation verwendete einheitliche Währung, die auf der Seite Unternehmensinformationen festgelegt wird. |
| **Lokale Währung (oder Benutzerwährung)** | Die für einen einzelnen Benutzer im Benutzerprofil festgelegte Währung, sodass er jeden Betrag in seiner eigenen Landeswährung anzeigen kann. Die Organisation muss die Währung deklarieren und einrichten, bevor ein Benutzer seine Landeswährung auswählen kann. |
| **Einheitliche Währung** | Wird für Kunden verwendet, die nicht mehrere Währungen im CRM verwenden, deren Organisation jedoch in einer anderen Währung ausgeführt wird, sodass sie über ein &quot;Währungs-Gebietsschema&quot;verfügen. Dies ist weiterhin eine einheitliche Währung für die Organisation, jedoch ohne Konvertierung. |
| **Einfache Währung** | Für den Kunden ist &quot;Mehrere Währungen&quot;aktiviert, er hat jedoch eine statische Konversionsrate pro Währung. |
