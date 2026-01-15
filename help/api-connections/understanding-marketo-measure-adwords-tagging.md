---
description: Grundlegendes  [!DNL Marketo Measure]  AdWords-Tagging-Anleitung für Marketo Measure-Benutzende
title: Grundlagen [!DNL Marketo Measure] AdWords-Tagging
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
feature: APIs, Integration, UTM Parameters
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 6%

---

# Grundlegendes [!DNL Marketo Measure] AdWords-Tagging {#understanding-marketo-measure-adwords-tagging}

Um Ihre Anzeigen auf einer sehr granularen Ebene zu verfolgen, müssen die Anzeigenziel-URLs eindeutig sein. Dazu fügt [!DNL Marketo Measure] automatisches Tagging automatisch Tracking-Parameter zu den Werbeziel-URLs Ihrer [!DNL AdWords]-Anzeigen hinzu. Sehen wir uns ein Beispiel unten an.

Die folgende URL liefert keine granularen Daten:

* `http://example.com/landing-page?myParam=foo`

Dieselbe URL liefert jedoch aufgrund der [!DNL Marketo Measure] Parameter granulare Daten:

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Funktionsweise [!DNL Marketo Measure] automatischen Tagging {#how-marketo-measure-auto-tagging-works}

**Wenn [!DNL Marketo Measure] eine Tracking-Vorlage findet:**

* [!DNL Marketo Measure] fügt seine Parameter zur Tracking-Vorlage hinzu.
* Wenn in einer Tracking-Vorlage eine Weiterleitung eines Drittanbieters wie Kenshoo oder Marin gefunden wird, führt [!DNL Marketo Measure] keine Maßnahmen durch. Stattdessen müssen Sie [Parameter  [!DNL Marketo Measure]  dem Drittanbieter-Tool in Ihrem Konto hinzufügen](/help/api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

Wenn jedoch keine Tracking-Vorlage gefunden wird, werden [!DNL Marketo Measure]:

* Überprüfen Sie alle Werbeziel-URLs auf Ihre [!DNL Marketo Measure].
* Wenn du gefunden wirst, bist du bereit zu gehen.
* Wenn er nicht gefunden wird, hängen [!DNL Marketo Measure] seine Parameter an das Ende der Werbeziel-URLs an. Bei neuen Anzeigen hängen [!DNL Marketo Measure] ihre Parameter innerhalb von zwei Stunden nach der Erstellung an die Anzeigenziel-URL an.
* Es ist wichtig, eine Tracking-Vorlage einzurichten, bevor das automatische Tagging aktiviert wird, damit [!DNL Marketo Measure] sie anhängen können und ein Zurücksetzen des Anzeigenverlaufs verhindert wird.

[!DNL Marketo Measure] empfiehlt, eine Tracking-Vorlage auf Konto-, Kampagnen- oder Werbeanzeigengruppen-Ebene zu verwenden, damit die Parameter aller Werbeanzeigen hinzugefügt oder entfernt werden können, ohne Risiko einer Unterbrechung oder Löschung des Werbeverlaufs.

## Tracking-Vorlagen {#tracking-templates}

Wie von [!DNL Google AdWords] erläutert, ist eine Tracking-Vorlage die URL, über die eine Landingpage erreicht wird. Die erfassten Tracking-Informationen werden zum Verständnis Ihres Anzeigen-Traffics verwendet. [Klicken Sie hier](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"} um weitere Informationen von Google zu erhalten.

[!DNL Marketo Measure] empfiehlt die Verwendung einer Tracking-Vorlage auf Konto-, Kampagnen- oder Anzeigengruppenebene, da sie das Hinzufügen und Subtrahieren von Parametern für alle Anzeigen ermöglicht, ohne das Risiko einer Unterbrechung oder Löschung des Anzeigenverlaufs zu bergen.

Es gibt zwei Tracking-Vorlagen, deren Verwendung [!DNL Marketo Measure] empfiehlt. Verwenden Sie Folgendes, um zu bestimmen, welche Version für Sie geeignet ist:

* Wenn alle Ihre Anzeigen-URLs ein &quot;?“ Verwenden Sie in ihnen diese URL:

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* Wenn keine Ihrer Anzeigen-URLs ein &quot;?“ aufweist, Verwenden Sie in ihnen diese URL:

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Einrichten einer Tracking-Vorlage auf Kontoebene {#setting-up-a-tracking-template-at-the-account-level}

1. Melden Sie sich bei Ihrem [!DNL Google AdWords] an.

1. Klicken Sie auf **[!UICONTROL Alle Kampagnen]** und dann **[!UICONTROL Einstellungen]** im sich erweiternden Fenster.

   ![1. Klicken Sie auf Alle Kampagnen und dann auf Einstellungen im sich erweiternden ](assets/utilizing-connections-13.png)

1. Klicken Sie **[!UICONTROL oben auf]** Kontoeinstellungen“ und dann **[!UICONTROL Tracking-Vorlage]**. Geben Sie die [!DNL Marketo Measure] Tracking-Vorlage ein.

   ![1. Klicken Sie oben auf Kontoeinstellungen und dann auf Tracking](assets/bizible-guide-1.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

## Einrichten einer Tracking-Vorlage auf Kampagnenebene {#setting-up-a-tracking-template-at-the-campaign-level}

1. Klicken Sie **[!UICONTROL Alle Kampagnen]** und dann **[!UICONTROL Kampagnen]** im sich erweiternden Fenster.

   ![1. Klicken Sie auf Alle Kampagnen und dann auf Kampagnen in der erweiternden ](assets/utilizing-connections-12.png)

1. Wählen Sie alle entsprechenden Kampagnen oder **[!UICONTROL Alle auswählen]**, klicken Sie auf **[!UICONTROL Bearbeiten]** und klicken Sie dann auf **[!UICONTROL Tracking-Vorlagen ändern]**.

   ![1. Wählen Sie alle entsprechenden Kampagnen aus oder wählen Sie „Alle“ und klicken Sie auf „Bearbeiten“](../assets/marketo-engage-activities-05.png)

1. Geben Sie die [!DNL Marketo Measure] Tracking-Vorlage ein und klicken Sie auf **[!UICONTROL Anwenden]**.

## Einrichten einer Tracking-Vorlage auf Anzeigengruppenebene: {#setting-up-a-tracking-template-at-the-ad-group-level}

1. Klicken Sie **[!UICONTROL Alle Kampagnen]** und dann **[!UICONTROL Anzeigengruppen]** im sich erweiternden Fenster.

   ![1. Klicken Sie auf Alle Kampagnen und dann auf Anzeigengruppen in der](assets/api-connections-01.png)

1. Wählen Sie alle anwendbaren Anzeigengruppen aus oder wählen Sie „Alle“, klicken Sie **[!UICONTROL Bearbeiten]** und klicken Sie dann auf **[!UICONTROL Tracking-Vorlagen ändern]**.

1. Geben Sie die [!DNL Marketo Measure] Tracking-Vorlage ein und klicken Sie auf **[!UICONTROL Anwenden]**.

   ![1. Geben Sie die Marketo Measure-Tracking-Vorlage ein und klicken Sie auf Anwenden.](../assets/marketo-engage-activities-01.png)

## FAQs {#faq}

**F: Welche Berechtigungen benötigt der verbundene Benutzer?**

A: userinfo.email

**F: Wie lange kann es dauern, Ausgabendaten zu importieren?**

A: 6 Stunden

**F: Wie lange kann es dauern, um Anzeigendaten zu importieren?**

A: 4 Stunden

**F: Können wir für dynamische Suchanzeigen die Kombination aus Überschrift, Beschreibung usw. in der bereitgestellten Kreativwerbung verfolgen?**

A.: Wir können keine individuellen kreativen Details für dynamische Suchanzeigen abrufen, aber wenn das automatische Tagging aktiviert ist, können wir trotzdem die kreative ID und den Umsatz des Attributs abrufen.

>[!NOTE]
>
>Sobald die Änderungen vorgenommen wurden, sind Sie fertig. Wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} wenn während des Setups Fragen auftreten.

[Klicken Sie hier](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"} um Anweisungen von Google zum Erstellen von Tracking-Vorlagen auf Kontoebene zu erhalten.
