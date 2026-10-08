---
unique-page-id: 27656735
description: Übersicht - [!DNL Marketo Measure]
title: Überblick
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
feature: Multi-Currency
TQID: 'https://experienceleague.adobe.com/x-CcPqcp3SXgSToNxdrLNnkYf5DA7Be9nPPwHTxA8pM'
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: 4df48d8c-59df-55ca-8ab7-225a5c35169b
    internal-label: Multi-Currency
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%
---
# Überblick {#overview}

Heutzutage unterstützt die [!DNL Marketo Measure]-Anwendung nur eine gemeinsame Währung (die als USD angenommen wird), während wir wissen und wissen, dass wir Kundinnen und Kunden auf der ganzen Welt haben, die über ihre eigenen Unternehmens- und Benutzerwährungen berichten müssen. Diese Funktion ermöglicht es Benutzenden, bei der Anzeige der gemeldeten Ausgaben oder Umsatzerlöse in [!DNL Marketo Measure] zwischen den gleichen Währungen zu wechseln, die auch in ihrem CRM verwendet werden.

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
