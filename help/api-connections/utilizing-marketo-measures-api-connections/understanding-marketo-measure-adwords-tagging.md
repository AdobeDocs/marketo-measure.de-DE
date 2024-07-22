---
unique-page-id: 18874678
description: Grundlegendes zum [!DNL Marketo Measure] AdWords-Tagging - [!DNL Marketo Measure]
title: Grundlagen [!DNL Marketo Measure] AdWords-Tagging
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
feature: APIs, Integration, UTM Parameters
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 6%

---

# Grundlegendes zu [!DNL Marketo Measure] AdWords-Tagging {#understanding-marketo-measure-adwords-tagging}

Damit Ihre Anzeigen auf einer sehr detaillierten Ebene verfolgt werden können, müssen die Anzeigenziel-URLs eindeutig sein. Um dies zu erreichen, fügt das automatische Tagging von [!DNL Marketo Measure] den Anzeigenziel-URLs Ihrer [!DNL AdWords] -Anzeigen automatisch Tracking-Parameter hinzu. Sehen wir uns ein Beispiel unten an.

Die folgende URL stellt keine granularen Daten bereit:

* `http://example.com/landing-page?myParam=foo`

Dieselbe URL bietet jedoch aufgrund der Parameter [!DNL Marketo Measure] granulare Daten:

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Funktionsweise von [!DNL Marketo Measure] automatischem Tagging {#how-marketo-measure-auto-tagging-works}

**Wenn [!DNL Marketo Measure] eine Tracking-Vorlage findet:**

* [!DNL Marketo Measure] fügt seine Parameter zur Tracking-Vorlage hinzu.
* Wenn eine Umleitung eines Drittanbieters in einer Tracking-Vorlage wie Kenshoo oder Marin gefunden wird, wird [!DNL Marketo Measure] keine Aktion ausführen. Stattdessen müssen Sie [Parameter  [!DNL Marketo Measure] zum Tool eines Drittanbieters in Ihrem Konto hinzufügen](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

Wenn jedoch keine Tracking-Vorlage gefunden wird, führt [!DNL Marketo Measure] Folgendes durch:

* Durchsuchen Sie alle Anzeigen-Ziel-URLs nach unseren [!DNL Marketo Measure] -Parametern.
* Wenn du gefunden hast, kannst du gut gehen.
* Wenn nicht gefunden, hängt [!DNL Marketo Measure] seine Parameter an das Ende der Anzeigenziel-URLs an. Bei neuen Anzeigen hängt [!DNL Marketo Measure] seine Parameter innerhalb von zwei Stunden nach der Erstellung an die Anzeigenziel-URL an.
* Es ist wichtig, dass eine Tracking-Vorlage vorhanden ist, bevor das automatische Tagging aktiviert wird, damit [!DNL Marketo Measure] daran angehängt werden kann und ein Zurücksetzen des Anzeigenverlaufs verhindert wird.

[!DNL Marketo Measure] empfiehlt, eine Tracking-Vorlage auf Konto-, Kampagnen- oder Werbeanzeigengruppen-Ebene zu verwenden, damit die Parameter aller Werbeanzeigen hinzugefügt oder entfernt werden können, ohne Risiko einer Unterbrechung oder Löschung des Werbeverlaufs.

## Tracking-Vorlagen {#tracking-templates}

Wie durch [!DNL Google AdWords] erläutert, ist eine Tracking-Vorlage die URL, die zum Erreichen einer Landingpage verwendet wird. Die erfassten Tracking-Informationen werden verwendet, um Ihren Anzeigen-Traffic zu verstehen. [Klicken Sie hier](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"} , um weitere Informationen aus Google zu erhalten.

[!DNL Marketo Measure] empfiehlt die Verwendung einer Tracking-Vorlage auf Kontoebene, Kampagnenebene oder Anzeigengruppenebene, da sie das Hinzufügen und Abziehen von Parametern für alle Anzeigen ermöglicht, ohne dass das Risiko von Unterbrechungen oder Löschungen des Anzeigenverlaufs besteht.

Es werden zwei Tracking-Vorlagen empfohlen, [!DNL Marketo Measure] zu verwenden. Verwenden Sie Folgendes, um zu bestimmen, welche Version für Sie geeignet ist:

* Wenn alle Ihre Anzeigen-URLs ein &quot;?&quot; in ihnen diese URL verwenden:

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* Wenn keine Ihrer Anzeigen-URLs ein &quot;?&quot; in ihnen diese URL verwenden:

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Einrichten einer Tracking-Vorlage auf Kontoebene {#setting-up-a-tracking-template-at-the-account-level}

1. Melden Sie sich bei Ihrem [!DNL Google AdWords] -Konto an.

1. Klicken Sie im erweiterten Fenster auf **[!UICONTROL Alle Kampagnen]** und dann auf **[!UICONTROL Einstellungen]** .

   ![](assets/1.png)

1. Klicken Sie oben auf **[!UICONTROL Kontoeinstellungen]** und dann auf **[!UICONTROL Tracking-Vorlage]**. Geben Sie die Tracking-Vorlage [!DNL Marketo Measure] ein.

   ![](assets/2-1.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

## Einrichten einer Tracking-Vorlage auf Kampagnenebene {#setting-up-a-tracking-template-at-the-campaign-level}

1. Klicken Sie im erweiterten Fenster auf **[!UICONTROL Alle Kampagnen]** und dann auf **[!UICONTROL Kampagnen]** .

   ![](assets/3.png)

1. Wählen Sie alle zutreffenden Kampagnen oder **[!UICONTROL Alle auswählen]** aus, klicken Sie auf **[!UICONTROL Bearbeiten]** und dann auf **[!UICONTROL Tracking-Vorlagen ändern]**.

   ![](assets/4-1.png)

1. Geben Sie die [!DNL Marketo Measure] Tracking-Vorlage ein und klicken Sie auf **[!UICONTROL Apply]**.

## Einrichten einer Tracking-Vorlage auf Anzeigengruppenebene: {#setting-up-a-tracking-template-at-the-ad-group-level}

1. Klicken Sie im sich öffnenden Fenster auf **[!UICONTROL Alle Kampagnen]** und dann auf **[!UICONTROL Anzeigengruppen]** .

   ![](assets/5-1.png)

1. Wählen Sie alle zutreffenden Anzeigengruppen oder Alle auswählen aus, klicken Sie auf **[!UICONTROL Bearbeiten]** und dann auf **[!UICONTROL Tracking-Vorlagen ändern]**.

1. Geben Sie die [!DNL Marketo Measure] Tracking-Vorlage ein und klicken Sie auf **[!UICONTROL Apply]**.

   ![](assets/6-1.png)

## FAQs {#faq}

**Q: Welche Berechtigungen benötigt der verbundene Benutzer?**

A: userinfo.email

**Q: Wie lange kann es dauern, Ausgabedaten zu importieren?**

A: 6 Stunden

**Q: Wie lange kann der Import von Anzeigendaten dauern?**

A: 4 Stunden

**Q: Können wir bei dynamischen Suchanzeigen die Kombination aus Überschrift, Beschreibung usw. im bereitgestellten Kreativ verfolgen?**

A: Wir können keine individuellen kreativen Details für dynamische Suchanzeigen abrufen, aber wenn das automatische Tagging aktiviert ist, können wir trotzdem die kreative ID abrufen und den Umsatz zuordnen.

>[!NOTE]
>
>Sobald die Änderungen vorgenommen wurden, sind Sie fertig. Wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} , wenn Sie während des Setups Fragen haben.

[Klicken Sie hier](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"} , um Anweisungen von Google zum Erstellen von Tracking-Vorlagen auf Kontoebene zu erhalten.
