---
description: Übersichtsleitfaden für Marketo Measure-Benutzende
title: Überblick
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
feature: Multi-Currency
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 1%

---

# Überblick {#overview}

Heute unterstützt die [!DNL Marketo Measure]-Anwendung nur eine einzige Währung (angenommen USD), während wir wissen und wissen, dass wir Kunden auf der ganzen Welt haben, die über ihre eigenen Unternehmens- und Benutzerwährungen berichten müssen. Diese Funktion ermöglicht es Benutzenden, bei der Anzeige der gemeldeten Ausgaben oder Umsatzerlöse in [!DNL Marketo Measure] zwischen den gleichen Währungen zu wechseln, die auch in ihrem CRM verwendet werden.

## Verfügbarkeit {#availability}

Stufe 2 und höher.

## Anforderungen {#requirements}

[!DNL Marketo Measure] ruft die Währungseinstellung automatisch aus dem CRM des Kunden ab. Eine manuelle Konfiguration in [!DNL Marketo Measure], die dem CRM-System entspricht, ist nicht mehr erforderlich. Die Währungseinstellung befindet sich auf der Seite „Allgemein“ unter „CRM“.

In [!DNL Salesforce] muss für den Kunden „Mehrere Währungen aktivieren“ aktiviert sein. Optional kann der Kunde auch „Ja, ich möchte die erweiterte Währungsverwaltung aktivieren“ auswählen.

In Dynamics kann der Kunde in seinen Einstellungen statische Wechselkurse für mehrere Währungen festlegen. Es gibt in Dynamics kein Konzept für „erweitertes Währungsmanagement“.

## Bedingungen {#terms}

| **Begriff** | Beschreibung |
|---|---|
| **Erweiterte Währung** | Der Kunde verfügt über eine erweiterte Währungsverwaltung und mehrere Währungen aktiviert, was bedeutet, dass er für verschiedene Zeiträume unterschiedliche Konversionsraten haben kann. |
| **Unternehmenswährung** | Dies sind die verschiedenen Währungen, die von einer Organisation im CRM aufgelistet und deklariert werden, alle mit Konversionsraten. [!DNL Marketo Measure] importieren diese Werte und stellen diese Währungen den Benutzern in unserem Produkt zur Verfügung. |
| **Währungsgebietsschema** | Die einheitliche Währung, die für eine Organisation verwendet wird, wird auf der Seite „Unternehmensinformationen“ festgelegt. |
| **Lokale Währung (oder Benutzerwährung)** | Die Währung, die für einen einzelnen Benutzer im Benutzerprofil festgelegt wurde, sodass er einen beliebigen Betrag in seiner eigenen lokalen Währung anzeigen kann. Das Unternehmen muss die Währung deklarieren und einrichten, bevor ein Benutzer seine lokale Währung auswählen kann. |
| **Einheitswährung** | Wird für Kunden verwendet, die nicht mehrere Währungen im CRM verwenden, deren Organisation jedoch in einer anderen Währung läuft, sodass sie ein „Währungsgebietsschema“ haben. Dies ist immer noch eine einheitliche Währung für die Organisation, aber ohne jede Umrechnung. |
| **Einfache Währung** | Für den Kunden sind mehrere Währungen aktiviert, aber er hat einen statischen Konversionskurs pro Währung. |
