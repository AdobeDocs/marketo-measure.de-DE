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

Für IMS-fähige Mandanten, die ausgeführt werden [!DNL Marketo Measure] in der Experience Cloud-Oberfläche, [!DNL Marketo Measure] bietet eine Benutzeroberfläche, über die Benutzer ihre eigene Domain-Liste verwalten können. [!DNL Marketo Measure] -Benutzer müssen zunächst alle Domänen überprüfen, die sie im [Adobe Admin Console](https://adminconsole.adobe.com/). Sobald Domänen in der Admin Console überprüft wurden, können Benutzer verwalten, ob [!DNL Marketo Measure] verwendet diese Domänen zur Verfolgung des Website-Traffics.

## Hinzufügen von Domänen in Admin Console {#adding-domains-in-admin-console}

IMS-Benutzer mit Zugriff auf Adobe Admin Console können eigene Domänen hinzufügen und validieren. Die Domänenvalidierung umfasst das Hinzufügen eines DNS-Eintrags für jede Domäne und die anschließende Überprüfung dieses Datensatzes durch die Admin Console.

![](assets/domain-management-1.png)

Anweisungen zum Hinzufügen von Domänen finden Sie im Abschnitt [Dokumentation zur Admin Console](https://helpx.adobe.com/enterprise/using/add-domains-directories.html). Nachdem eine Domäne hinzugefügt wurde, muss sie [mit einem Verzeichnis verknüpft ist](https://helpx.adobe.com/enterprise/using/add-domains-directories.html#link-domains-to-directoies).

## Verwalten von Domänen in [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Nachdem eine Domäne in der Admin Console hinzugefügt wurde, [!DNL Marketo Measure] synchronisiert diesen Datensatz regelmäßig in der Datenbank. Diese Synchronisierung findet nächtlich statt, und auch jedes Mal, wenn ein Benutzer die **[!UICONTROL Domänen]** in der [!DNL Marketo Measure] Benutzeroberfläche. Standardmäßig werden alle Datensätze, die [!DNL Marketo Measure] -Importe sind deaktiviert und der Mandant muss jede Domäne manuell aktivieren.

![](assets/domain-management-2.png)

Im **[!UICONTROL Integration]** > **[!UICONTROL Domänen]** angezeigt, werden dem Benutzer alle Domänen, die er in der Admin Console registriert hat, sowie ihr Status angezeigt. Jede Domäne kann aktiviert oder deaktiviert werden. Wenn eine Domäne aktiviert ist, [!DNL Marketo Measure] tracking erfasst sämtlichen Traffic, der in dieser Domäne angezeigt wird. Wenn eine Domäne deaktiviert ist, [!DNL Marketo Measure] ignoriert jeglichen Traffic, der von dieser Domäne stammt, und erstellt keine Touchpoints oder anderen Daten. [!DNL Marketo Measure] bestätigt die Deaktivierung einer Domäne und warnt vor etwaigen Auswirkungen:

![](assets/domain-management-3.png)

Die Auswirkungen des Umschalgens auf eine Domäne sind unmittelbar und die Änderungen sind nicht rückwirkend. Künftig [!DNL Marketo Measure] löscht Daten aus deaktivierten Domänen nach einem festgelegten Zeitraum.

## Status {#statuses}

Der Status der Admin Consolen wird wie folgt kategorisiert:

* **ÜBERPRÜFT**: Diese Domäne wird in Admin Console überprüft.
* **NICHT ÜBERPRÜFT**: Diese Domäne wurde in Admin Console nicht vollständig verifiziert und kann nicht in verfolgt werden. [!DNL Marketo Measure]
* **UNGÜLTIG**: Diese Domäne ist möglicherweise abgelaufen oder wurde aus der Admin Console entfernt. Tracking von Daten in [!DNL Marketo Measure] wird zum Löschen markiert
* **LEGACY**: Diese Domäne wurde in erstellt. [!DNL Marketo Measure] und nicht in der Admin Console vorhanden ist

Der Tracking-Status kann wie folgt lauten:

* **AKTIV**: [!DNL Marketo Measure] empfängt Daten von dieser Domäne
* **DISABLED**: Diese Domäne ist für das Tracking verfügbar, aber deaktiviert.
* **NICHT VERFÜGBAR**: Diese Domäne ist nicht für das Tracking verfügbar, da sie nicht verifiziert wurde.

Wenn Sie den Mauszeiger über ein einzelnes Statuselement bewegen, wird eine QuickInfo Trigger, in der dieser Status näher erläutert wird.

## FAQs {#faq}

**Was passiert, wenn eine Domäne in der Admin Console entfernt wird?**

Wenn eine Domäne in der Admin Console entfernt wird, [!DNL Marketo Measure] markiert die Domäne als gelöscht. [!DNL Marketo Measure] stoppt sofort das Traffic-Tracking in dieser Domäne, entfernt jedoch keine zuvor erfassten Daten.

**Warum kann ich eine Domäne nicht aktivieren?**

Es gibt verschiedene Gründe, warum eine Domäne auf dieser Seite möglicherweise nicht ausgewählt werden darf. Wenn die Domäne nicht in der Admin Console validiert wird, ist sie nicht verfügbar in [!DNL Marketo Measure]. Wenn die Domäne einer anderen Adobe-Org als der aktuellen gehört [!DNL Marketo Measure] -Mandanten nicht verfügbar sein.

**Wie kann ich eine Domäne aus dieser Liste entfernen?**

Wenn für eine Domäne der Schalter &quot;Aktiviert&quot;deaktiviert ist, [!DNL Marketo Measure] ignoriert sie und wird effektiv aus [!DNL Marketo Measure]. So entfernen Sie eine Domäne dauerhaft aus [!DNL Marketo Measure], müssen Sie sie in [!DNL Marketo Measure]und entfernen Sie sie dann aus der Admin Console.
