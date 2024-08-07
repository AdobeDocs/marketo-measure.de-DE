---
unique-page-id: 27656735
description: Übersicht - [!DNL Marketo Measure]
title: Überblick
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
feature: Multi-Currency
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# Überblick {#overview}

Heute unterstützt die Anwendung [!DNL Marketo Measure] nur eine einzige Währung (vorausgesetzt, sie ist USD), während wir wissen und wissen, dass wir Kunden auf der ganzen Welt haben, die über ihre eigenen Unternehmens- und Benutzerwährungen berichten müssen. Mit dieser Funktion können Benutzer zwischen denselben Währungen wechseln, die in ihrem CRM-System verwendet werden, wenn sie die gemeldeten Ausgaben oder Umsätze in [!DNL Marketo Measure] anzeigen.

## Verfügbarkeit {#availability}

Ebene 2 und höher.

## Anforderungen {#requirements}

[!DNL Marketo Measure] ruft automatisch die Währungseinstellung aus dem CRM-System des Kunden ab. Eine manuelle Konfiguration in [!DNL Marketo Measure], die dem CRM-System entspricht, ist nicht mehr erforderlich. Die Währungseinstellung finden Sie auf der Seite &quot;Allgemein&quot;unter &quot;CRM&quot;.

In [!DNL Salesforce] muss für den Kunden &quot;Aktivieren mehrerer Währungen&quot;aktiviert sein. Optional kann der Kunde auch &quot;Ja, ich möchte die erweiterte Währungsverwaltung aktivieren&quot;auswählen.

In Dynamics kann der Kunde in seinen Einstellungen statische Wechselkurse für mehrere Währungen festlegen. In Dynamics gibt es kein Konzept der &quot;erweiterten Währungsverwaltung&quot;.

## Bedingungen {#terms}

| **Begriff** | Beschreibung |
|---|---|
| **Erweiterte Währung** | Für den Kunden sind erweitertes Währungsmanagement und mehrere Währungen aktiviert, was bedeutet, dass er für verschiedene Zeiträume unterschiedliche Konversionsraten haben kann. |
| **Firmenwährung** | Dies sind die verschiedenen Währungen, die von einer Organisation im CRM-System aufgeführt und deklariert werden, alle mit Konversionsraten. [!DNL Marketo Measure] importiert diese Werte und stellt diese Währungen Benutzern in unserem Produkt zur Verfügung. |
| **Währungsgebietsschema** | Die für eine Organisation verwendete einheitliche Währung, die auf der Seite Unternehmensinformationen festgelegt wird. |
| **Lokale Währung (oder Benutzerwährung)** | Die für einen einzelnen Benutzer im Benutzerprofil festgelegte Währung, sodass er jeden Betrag in seiner eigenen Landeswährung anzeigen kann. Die Organisation muss die Währung deklarieren und einrichten, bevor ein Benutzer seine Landeswährung auswählen kann. |
| **Einzelwährung** | Wird für Kunden verwendet, die nicht mehrere Währungen im CRM verwenden, deren Organisation jedoch in einer anderen Währung ausgeführt wird, sodass sie über ein &quot;Währungs-Gebietsschema&quot;verfügen. Dies ist weiterhin eine einheitliche Währung für die Organisation, jedoch ohne Konvertierung. |
| **Einfache Währung** | Für den Kunden ist &quot;Mehrere Währungen&quot;aktiviert, er hat jedoch eine statische Konversionsrate pro Währung. |
