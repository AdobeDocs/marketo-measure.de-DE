---
description: Domain-Verwaltung - [!DNL Marketo Measure]
title: Domänenverwaltung
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
feature: Integration, Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 1%

---

# Domänenverwaltung {#domain-management}

Für IMS-aktivierte Mandanten, die [!DNL Marketo Measure] in der Experience Cloud-Benutzeroberfläche ausführen, bietet [!DNL Marketo Measure] eine Benutzeroberfläche, über die Benutzende ihre eigene Liste von Domains verwalten können. [!DNL Marketo Measure] Benutzer müssen zunächst alle Domains überprüfen, die sie in der [Adobe Admin Console verfolgen ](https://adminconsole.adobe.com/). Sobald die Domains in der Admin Console verifiziert wurden, können Benutzer verwalten, ob [!DNL Marketo Measure] diese Domains zum Tracking des Website-Traffics verwendet.

## Hinzufügen von Domains in Admin Console {#adding-domains-in-admin-console}

IMS-Benutzende mit Zugriff auf die Adobe Admin Console können Domains hinzufügen und validieren, deren Inhaber sie sind. Die Domain-Validierung umfasst das Hinzufügen eines DNS-Eintrags für jede Domain und die anschließende Überprüfung dieses Eintrags durch die Admin Console.

![](assets/domain-management-1.png)

Anweisungen zum Hinzufügen von Domains finden Sie in der Dokumentation zu [Admin Console](https://helpx.adobe.com/enterprise/using/add-domains-directories.html). Nachdem eine Domain hinzugefügt wurde, muss sie [mit einem Verzeichnis verknüpft](https://helpx.adobe.com/enterprise/using/add-domains-directories.html#link-domains-to-directoies).

## Verwalten von Domains in [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Nachdem eine Domain in der Admin Console hinzugefügt wurde, synchronisiert [!DNL Marketo Measure] diesen Datensatz regelmäßig mit der Datenbank. Diese Synchronisierung erfolgt nächtlich und auch jedes Mal, wenn ein Benutzer die Seite **[!UICONTROL Domains]** in der [!DNL Marketo Measure]-Benutzeroberfläche besucht. Standardmäßig sind alle Datensätze, die importiert [!DNL Marketo Measure], deaktiviert, und der Mandant muss jede Domain manuell aktivieren.

![](assets/domain-management-2.png)

Auf der Seite **[!UICONTROL Integration]** > **[!UICONTROL Domains]** werden alle Domains, die sie in der Admin Console registriert haben, zusammen mit ihrem Status angezeigt. Jede Domain kann aktiviert oder deaktiviert werden. Wenn eine Domain aktiviert ist, erfasst [!DNL Marketo Measure] Tracking sämtlichen Traffic, der in dieser Domain angezeigt wird. Wenn eine Domain deaktiviert ist, ignoriert [!DNL Marketo Measure] jeglichen Traffic von dieser Domain und erstellt keine Touchpoints oder anderen Daten. [!DNL Marketo Measure] bestätigt die Deaktivierung einer Domain und warnt vor etwaigen Auswirkungen:

![](assets/domain-management-3.png)

Das Umschalten einer Domain hat sofortige Auswirkungen, und Änderungen sind nicht rückwirkend. In Zukunft werden [!DNL Marketo Measure] nach einem festgelegten Zeitraum Daten aus deaktivierten Domains löschen.

## Status {#statuses}

Admin Console-Status werden wie folgt kategorisiert:

* **VALIDIERT**: Diese Domain wird in Admin Console verifiziert
* **UNVERIFIED**: Diese Domain ist in Admin Console nicht vollständig verifiziert und kann in [!DNL Marketo Measure] nicht verfolgt werden
* **UNGÜLTIG**: Diese Domain ist möglicherweise abgelaufen oder wurde aus Admin Console entfernt. Tracking-Daten in [!DNL Marketo Measure] sind zum Löschen gekennzeichnet
* **LEGACY**: Diese Domain wurde in [!DNL Marketo Measure] erstellt und existiert nicht in der Admin Console

Tracking-Status können wie folgt lauten:

* **ACTIVE**: [!DNL Marketo Measure] empfängt Daten von dieser Domain
* **DEAKTIVIERT**: Diese Domäne ist für das Tracking verfügbar, aber deaktiviert
* **NICHT VERFÜGBAR**: Diese Domain steht für das Tracking nicht zur Verfügung, da sie nicht verifiziert ist

Wenn Sie den Mauszeiger über ein einzelnes Statuselement bewegen, wird eine QuickInfo angezeigt, in der dieser Trigger näher erläutert wird.

## FAQs {#faq}

**Was passiert, wenn eine Domain in der Admin Console entfernt wird?**

Wenn eine Domain in der Admin Console entfernt wird, markiert [!DNL Marketo Measure] die Domain als gelöscht. [!DNL Marketo Measure] stoppt sofort die Verfolgung des Traffics auf dieser Domain, entfernt jedoch keine zuvor erfassten Daten.

**Warum kann ich eine Domain nicht aktivieren?**

Es gibt verschiedene Gründe, warum eine Domain auf dieser Seite nicht ausgewählt werden kann. Wenn die Domain in der Admin Console nicht validiert wurde, ist sie in [!DNL Marketo Measure] nicht verfügbar. Wenn die Domain einer anderen Adobe-Organisation als der aktuelle [!DNL Marketo Measure]-Mandant gehört, kann sie ebenfalls nicht ausgewählt werden.

**Wie entferne ich eine Domain aus dieser Liste?**

Wenn für eine Domain der Schalter „enabled“ deaktiviert ist, ignoriert [!DNL Marketo Measure] ihn und er wird effektiv aus [!DNL Marketo Measure] entfernt. Um eine Domain dauerhaft aus [!DNL Marketo Measure] zu entfernen, müssen Sie sie in [!DNL Marketo Measure] deaktivieren und dann aus der Admin Console entfernen.
