---
description: Best Practices für die Implementierung [!DNL Marketo Measure] JavaScript-Anleitungen für Marketo Measure-Benutzer
title: Best Practices zur Implementierung von [!DNL Marketo Measure]-JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: dcbeff6e-0253-5a4b-9ac2-1b67cc4a6286
    internal-label: Tracking
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 97%
---

# Best Practices zur Implementierung von [!DNL Marketo Measure]-JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## Überblick {#overview}

[!DNL Marketo Measure]-JavaScript verfolgt die Digital-Marketing-Interaktionen Ihrer Web-Besuchenden nach und ist für die [!DNL Marketo Measure]-Funktionalität zum Erstellen von Online-Touchpoint-Daten von entscheidender Bedeutung. Durch eine ordnungsgemäße und umfassende [!DNL Marketo Measure]-JavaScript-Bereitstellung auf der gesamten Site wird sichergestellt, dass die erfassten Sitzungsdaten genaue Touchpoint-Daten erzeugen.

Inkonsistenzen bei der [!DNL Marketo Measure]-JavaScript-Bereitstellung führen zu Brüchen in den Sitzungsdaten und damit gegebenenfalls zu Folgendem:

* einer falschen Kanal-/Subkanalattribution
* Verlust von Quelldaten
* einem hohen Maß an fehlerhaftem Direct-Traffic
* inkonsistenten Berichten

[!DNL Marketo Measure]-JavaScript ist ein grundlegendes Element Ihres [!DNL Marketo Measure]-Kontos und der Schlüssel zu Ihrem Erfolg

## Best Practices {#best-practice}

Beachten Sie die folgenden Best Practices, wenn Sie [!DNL Marketo Measure]-JavaScript implementieren und verwalten.

* Vergewissern Sie sich, dass alle Ihre Domains in Ihrem [!DNL Marketo Measure]-Konto aufgeführt sind
  * Wenden Sie sich an den Support, wenn Sie Bedenken bezüglich Ihrer Domains haben
* Stellen Sie JavaScript auf ALLEN Seiten bereit.
  * Wenn Sie JavaScript nur auf bestimmten Seiten platzieren, treten in Ihren Sitzungsdaten Brüche auf, die zu falschen [!DNL Marketo Measure]-Daten führen
* Fügen Sie für ein Formular auf Ihrer Site, aus dem Sie keine Touchpoints erstellen möchten, das [!DNL Marketo Measure]-Ausschlussskript hinzu
  * Dieses Ausschlussskript stellt sicher, dass es in den [!DNL Marketo Measure]-Sitzungsdaten zu keinem Bruch kommt und die Quelldaten erhalten bleiben
    * Beispiele für Formulare, die häufig ausgeschlossen werden sollten, sind:
      * Kundenanmeldungen
      * „Passwort vergessen“-Formulare
      * Abmeldeformulare
      * Bewerbungsformulare
* Lesen Sie die Abschnitte „Zusätzliche Überlegungen“ und „Formulare, auf die besonders zu achten ist“ in der unten aufgeführten Ressource „Hinzufügen von [!DNL Marketo Measure]-Skript“, um sich über Szenarien zu informieren, die gegebenenfalls einer besonderen Behandlung bedürfen

## Best Practice für die Wartung {#best-practice-for-maintenance}

Während [!DNL Marketo Measure]-JavaScript bei der Erstimplementierung eingerichtet wird, können Änderungen an Ihrer Site oder im Team, das sie verwaltet, zu Störungen beim [!DNL Marketo Measure]-Tracking führen. Wir empfehlen Ihnen, einmal im Jahr zu überprüfen, ob das [!DNL Marketo Measure]-JavaScript korrekt und umfassend eingesetzt wird. Wenn Ihr Unternehmen außerdem über ein Änderungsprotokoll für die Website verfügt, stellen Sie sicher, dass darin ein Abschnitt enthalten ist, der erklärt, dass [!DNL Marketo Measure]-JavaScript auf allen neuen Seiten beibehalten/hinzugefügt werden sollte.

Andere mögliche Gründe für eine Überprüfung Ihres JavaScript-Setups:

* Wechsel in Ihrem Marketing-Team
* Änderungen und Aktualisierungen der Site-Struktur
* Site-Migrationen
* Änderungen an Ihrer Domain
* Übernahmen anderer Unternehmen und ihrer Web-Präsenzen
