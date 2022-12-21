---
description: Best Practices zur Implementierung [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure] - Produktdokumentation
title: Best Practices zur Implementierung [!DNL Marketo Measure] JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
source-git-commit: cf144eb4bc9282ae6a260acd3735f24644292a19
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# Best Practices zur Implementierung [!DNL Marketo Measure] JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## Überblick {#overview}

Die [!DNL Marketo Measure] JavaScript verfolgt die Interaktionen Ihrer Webbesucher mit dem digitalen Marketing und ist für die [!DNL Marketo Measure] Möglichkeit, Online-Touchpoint-Daten zu erstellen. Die [!DNL Marketo Measure] JavaScript, das ordnungsgemäß und umfassend auf Ihrer gesamten Site(s) bereitgestellt wird, stellt sicher, dass die erfassten Sitzungsdaten genaue Touchpoint-Daten erzeugen.

Inkonsistenzen bei der Implementierung der [!DNL Marketo Measure] JavaScript führt zu Umbrüchen in den Sitzungsdaten, die zu Folgendem führen können:

* Falsche Kanalzuordnung/Subkanalzuordnung
* Verlust von Quelldaten
* Hohe Höhe des fehlerhaften direkten Traffics
* Inkonsistente Berichterstattung

[!DNL Marketo Measure] JavaScript ist ein grundlegendes Element Ihrer [!DNL Marketo Measure] und der Schlüssel zu Ihrem Erfolg!

## Best Practice {#best-practice}

Bei der Implementierung und Verwaltung Ihrer [!DNL Marketo Measure] Beachten Sie JavaScript die folgenden Best Practices.

* Vergewissern Sie sich, dass alle Ihre Domänen in Ihrer [!DNL Marketo Measure] account
   * Wenden Sie sich an den Support, wenn Sie Bedenken bezüglich Ihrer Domänen haben
* Bereitstellen von JavaScript auf allen Seiten.
   * Wenn Sie JavaScript nur auf bestimmten Seiten platzieren, treten in Ihren Sitzungsdaten Pausen auf, die zu falschen Werten führen [!DNL Marketo Measure] data
* Fügen Sie für ein Formular auf Ihrer Site, aus dem Sie keine Touchpoints erstellen möchten, die [!DNL Marketo Measure] Ausschlussskript
   * Dieses Ausschlussskript stellt sicher, dass die Variable [!DNL Marketo Measure] Sitzungsdaten werden nicht gestört und die Quelldaten bleiben vorhanden
      * Beispiele für häufig zu unterdrückende Formulare sind:
         * Kundenanmeldungen
         * Kennwortformulare vergessen
         * Formulare abmelden
         * Formulare für Karriere-Apps
* Lesen Sie die Abschnitte &quot;Weitere Aspekte&quot;und &quot;Forms, um besondere Aufmerksamkeit zu schenken&quot;unter Hinzufügen von [!DNL Marketo Measure] Unten aufgeführte Skript-Ressource, um nach Szenarien zu suchen, die eine besondere Behandlung erfordern könnten

## Best Practice für die Wartung {#best-practice-for-maintenance}

Während der Einrichtung der [!DNL Marketo Measure] JavaScript wird bei der ersten Implementierung behandelt. Änderungen an Ihrer Site oder dem Team, das sie verwaltet, können zu Störungen in [!DNL Marketo Measure] Tracking. Es wird empfohlen, die [!DNL Marketo Measure] JavaScript wird einmal jährlich korrekt und umfassend bereitgestellt. Wenn Ihr Unternehmen außerdem über eine Dokumentation zum Änderungsprotokoll für die Website verfügt, stellen Sie sicher, dass es einen Abschnitt gibt, der erklärt, dass [!DNL Marketo Measure] JavaScript sollte auf allen neuen Seiten beibehalten/hinzugefügt werden.

Andere Gründe dafür könnten Trigger für eine Überprüfung Ihres JavaScript-Setups sein...

* Umsatz in Ihrem Marketing-Team
* Änderungen und Aktualisierungen der Site-Struktur
* Site-Migrationen
* Änderungen an Ihrer Domain
* Acquisition von anderen Unternehmen und deren Webeigenschaften
