---
description: Domänenverwaltung - [!DNL Marketo Measure]
title: Domänenverwaltung
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
feature: Integration, Tracking
source-git-commit: 4c68fa08797c252a89ba097c723fb8afee82451f
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 1%

---

# Domänenverwaltung {#domain-management}

Für IMS-fähige Mandanten, die [!DNL Marketo Measure] in der Experience Cloud-Oberfläche ausführen, stellt [!DNL Marketo Measure] eine Schnittstelle bereit, über die Benutzer ihre eigene Domänenliste verwalten können. [!DNL Marketo Measure] -Benutzer müssen zunächst alle Domänen überprüfen, die sie in der [Adobe Admin Console](https://adminconsole.adobe.com/) verfolgen möchten. Sobald Domänen in der Admin Console verifiziert sind, können Benutzer verwalten, ob [!DNL Marketo Measure] diese Domänen zur Verfolgung des Website-Traffics verwendet.

## Hinzufügen von Domänen in Admin Console {#adding-domains-in-admin-console}

IMS-Benutzer mit Zugriff auf Adobe Admin Console können eigene Domänen hinzufügen und validieren. Die Domänenvalidierung umfasst das Hinzufügen eines DNS-Eintrags für jede Domäne und die anschließende Überprüfung dieses Datensatzes durch die Admin Console.

![](assets/domain-management-1.png)

Anweisungen zum Hinzufügen von Domänen finden Sie in der [Dokumentation zur Admin Console](https://helpx.adobe.com/enterprise/using/add-domains-directories.html). Nachdem eine Domäne hinzugefügt wurde, muss sie [mit einem Verzeichnis](https://helpx.adobe.com/enterprise/using/add-domains-directories.html#link-domains-to-directoies) verknüpft sein.

## Verwalten von Domänen in [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Nachdem der Admin Console eine Domäne hinzugefügt wurde, synchronisiert [!DNL Marketo Measure] diesen Datensatz regelmäßig mit der Datenbank. Diese Synchronisierung findet nächtlich statt, und auch jedes Mal, wenn ein Benutzer die Seite **[!UICONTROL Domänen]** in der Benutzeroberfläche von [!DNL Marketo Measure] besucht. Standardmäßig sind alle von [!DNL Marketo Measure] importierten Datensätze deaktiviert und der Mandant muss jede Domäne manuell aktivieren.

![](assets/domain-management-2.png)

Auf der Seite **[!UICONTROL Integration]** > **[!UICONTROL Domänen]** werden dem Benutzer alle Domänen angezeigt, die er in der Admin Console registriert hat, sowie ihr Status. Jede Domäne kann aktiviert oder deaktiviert werden. Wenn eine Domäne aktiviert ist, erfasst das [!DNL Marketo Measure]-Tracking sämtlichen Traffic, der in dieser Domäne angezeigt wird. Wenn eine Domäne deaktiviert ist, ignoriert [!DNL Marketo Measure] jeglichen Traffic, der von dieser Domäne stammt, und erstellt keine Touchpoints oder anderen Daten. [!DNL Marketo Measure] bestätigt die Deaktivierung einer Domäne und warnt vor möglichen Auswirkungen:

![](assets/domain-management-3.png)

Die Auswirkungen des Umschalgens auf eine Domäne sind unmittelbar und die Änderungen sind nicht rückwirkend. In Zukunft löscht [!DNL Marketo Measure] nach einem bestimmten Zeitraum Daten aus deaktivierten Domänen.

## Status {#statuses}

Der Status der Admin Consolen wird wie folgt kategorisiert:

* **VALIDATED**: Diese Domäne wird in Admin Console überprüft.
* **UNVERIFIED**: Diese Domäne ist in Admin Console nicht vollständig verifiziert und kann in [!DNL Marketo Measure] nicht verfolgt werden.
* **UNGÜLTIG**: Diese Domäne ist möglicherweise abgelaufen oder wurde aus der Admin Console entfernt. Tracking-Daten in [!DNL Marketo Measure] werden zum Löschen markiert
* **LEGACY**: Diese Domäne wurde in [!DNL Marketo Measure] erstellt und ist nicht in der Admin Console vorhanden

Der Tracking-Status kann wie folgt lauten:

* **AKTIV**: [!DNL Marketo Measure] erhält Daten von dieser Domäne
* **DEABLED**: Diese Domäne kann verfolgt werden, ist jedoch deaktiviert.
* **UNAVAILABLE**: Diese Domäne ist nicht für das Tracking verfügbar, da sie nicht verifiziert wurde.

Wenn Sie den Mauszeiger über ein einzelnes Statuselement bewegen, wird eine QuickInfo Trigger, in der dieser Status näher erläutert wird.

## FAQs {#faq}

**Was passiert, wenn eine Domäne in der Admin Console entfernt wird?**

Wenn eine Domäne in der Admin Console entfernt wird, markiert [!DNL Marketo Measure] die Domäne als gelöscht. [!DNL Marketo Measure] stoppt sofort das Traffic-Tracking in dieser Domäne, entfernt jedoch keine zuvor erfassten Daten.

**Warum kann ich eine Domäne nicht aktivieren?**

Es gibt verschiedene Gründe, warum eine Domäne auf dieser Seite möglicherweise nicht ausgewählt werden darf. Wenn die Domäne nicht in der Admin Console validiert wird, ist sie in [!DNL Marketo Measure] nicht verfügbar. Wenn die Domäne einer anderen Adobe-Org als dem aktuellen [!DNL Marketo Measure] -Mandanten gehört, kann sie nicht ausgewählt werden.

**Wie kann ich eine Domäne aus dieser Liste entfernen?**

Wenn für eine Domäne der Schalter &quot;Aktiviert&quot;deaktiviert ist, ignoriert [!DNL Marketo Measure] sie und wird effektiv aus [!DNL Marketo Measure] entfernt. Um eine Domäne dauerhaft aus [!DNL Marketo Measure] zu entfernen, müssen Sie sie in [!DNL Marketo Measure] deaktivieren und sie dann aus der Admin Console entfernen.
