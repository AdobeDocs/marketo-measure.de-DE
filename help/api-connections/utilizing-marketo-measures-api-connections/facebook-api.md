---
unique-page-id: 18874680
description: '[!DNL Facebook] API - [!DNL Marketo Measure]'
title: '[!DNL Facebook] API'
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
feature: APIs, Integration, UTM Parameters
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 3%

---

# [!DNL Facebook] API {#facebook-api}

## Einführung {#introduction}

Ähnlich wie bei unseren AdWords- und [!DNL Bing Ads]-Integrationen führt auch unsere [!DNL Facebook]-Integration zwei grundlegende Aktionen durch:

* Alle [!DNL Facebook] Anzeigen automatisch mit einem [!DNL Marketo Measure] (_bf) taggen
* Informationen zu Werbekosten für alle aktiven Facebook-Anzeigen herunterladen

## Konfigurieren der [!DNL Facebook] Integration {#how-to-configure-the-facebook-integration}

Was die Einrichtung betrifft, müssen in der [!DNL Marketo Measure]-App sieben Schritte ausgeführt werden.

1. Navigieren Sie zu [experience.adobe.com/marketo-measure ](https://experience.adobe.com/marketo-measure){target="_blank"} melden Sie sich an.
1. Wählen Sie unter Mein Konto **[!UICONTROL Einstellungen]** aus.
1. Wählen Sie unter Integrationen **[!UICONTROL Verbindungen]** aus.
1. Wählen Sie **[!UICONTROL Neue Anzeigenverbindung einrichten]** und ein Popup wird angezeigt. Wählen Sie **[!UICONTROL Facebook]** aus und melden Sie sich mit Ihren Facebook-Anmeldeinformationen an.

   >[!NOTE]
   >
   >Die Person, die das [!DNL Facebook Ads]-Konto verbindet, muss Administrator des [!DNL Facebook Ads]-Kontos sein.

1. Sobald [!DNL Marketo Measure] mit Ihrem Facebook-Konto verbunden ist, klicken Sie auf das Stiftsymbol neben dem Konto.
1. Verschieben Sie in dieser Ansicht das Feld „Automatisches Tagging?“ auf „Ja“ umschalten. Aktivieren Sie dann das Kontrollkästchen im Abschnitt [!UICONTROL Weitere Informationen], um den Nutzungsbedingungen zuzustimmen. Stellen Sie sicher[!UICONTROL  dass der Umschalter für ]Automatisches Tagging“ weiterhin auf &quot;[!UICONTROL Ja] eingestellt ist.

## Verbinden des Kontos {#connecting-the-account}

![](assets/1.gif)

## Aktivieren von automatischem Tagging {#enabling-autotagging}

>[!NOTE]
>
>Wenn Sie das automatische Tagging aktivieren, setzen wir den Konversionsverlauf und den Social Proof aller Anzeigen zurück, die wir taggen. Es wird dringend empfohlen[ diese Daten als CSV zu exportieren](https://www.facebook.com/business/help/205067636197240) bevor Sie das automatische Tagging aktivieren.

![](assets/2-2.png)

Sobald Sie die Integration aktiviert haben, beginnen [!DNL Marketo Measure], Kosten auf Anzeigenebene in das [!DNL Marketo Measure Marketing ROI] Dashboard herunterzuladen.

Damit die Integration ordnungsgemäß funktioniert, müssen Sie das automatische Tagging für Ihr [!DNL Facebook]-Konto aktivieren. Dadurch kann unser System einen _bf-Parameter über alle Werbelinks hinweg hinzufügen. Dieser Prozess fügt den neuen Parameter zu allen anderen Tracking-Parametern hinzu, die Sie Ihren [!DNL Facebook] bereits hinzugefügt haben.

![](assets/3.gif)

## Feldzuordnung {#field-mapping}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>Touchpoint-Feld</strong></p></th> 
   <th><p><strong>Wert</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>Anzeigenkampagnen-ID</p></td> 
   <td><p>[Kampagnen-ID [!DNL Facebook]]</p></td> 
  </tr> 
  <tr> 
   <td><p>Name der Anzeigenkampagne </p></td> 
   <td><p>[[!DNL Facebook] Kampagnenname] oder [utm_campaign], falls angegeben</p></td> 
  </tr> 
  <tr> 
   <td><p>Anzeigengruppen-ID</p></td> 
   <td><p>[Kennung des [!DNL Facebook]]</p></td> 
  </tr> 
  <tr> 
   <td><p>Werbegruppenname</p></td> 
   <td><p>[Name des [!DNL Facebook]]</p></td> 
  </tr> 
  <tr> 
   <td><p>Touchpoint-Quelle</p></td> 
   <td><p>"[!DNL Facebook]" oder [UTM_SOURCE], falls angegeben</p></td> 
  </tr> 
  <tr> 
   <td><p>Medium</p></td> 
   <td><p>„Social“ oder [utm_medium], falls angegeben</p></td> 
  </tr> 
  <tr> 
   <td><p>Anzeigen-ID oder Creative_UNIQUE_ID (Data Warehouse)</p></td> 
   <td><p>[aus utm_content generierte benutzerdefinierte ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Anzeigeninhalt oder Creative_Name (Data Warehouse)</p></td> 
   <td><p>[UTM_CONTENT], falls angegeben</p></td> 
  </tr> 
  <tr> 
   <td><p>Keyword-Text oder Keyword_Name (Data Warehouse)</p></td> 
   <td><p>[UTM_TERM], falls angegeben</p></td> 
  </tr> 
  <tr> 
   <td><p>ad_unique_id (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook]-ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>ad_name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Anzeigenname]</p></td> 
  </tr> 
  <tr> 
   <td><p>KEYWORD_UNIQUE_ID (Data Warehouse)</p></td> 
   <td><p>[aus utm_term generierte benutzerdefinierte ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>ad_provider (Data Warehouse)</p></td> 
   <td><p>[!DNL Facebook]"</p></td> 
  </tr> 
  <tr> 
   <td><p>account_unique_id (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Kontonummer]</p></td> 
  </tr> 
  <tr> 
   <td><p>Kontoname (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Kontoname]</p></td> 
  </tr> 
 </tbody> 
</table>

## FAQs {#faq}

**F: Welche [!DNL Facebook] werden von [!DNL Marketo Measure] unterstützt?**

A: Karussell, Einzelbild. Derzeit weder Video noch Diashow oder Sammlung.

**F: Was ist ein sozialer Beweis?**

A: Der Social-Proof ist sichtbare Interaktion wie Likes, Klicks, Kommentare und Shares.

**F: Was passiert, wenn [!DNL Marketo Measure] die Anzeige taggt?**

A: [!DNL Facebook] lässt die Bearbeitung von Anzeigen nicht zu. Daher muss [!DNL Marketo Measure] das Kreativ löschen, das die Ziel-URL enthält, und dann die Anzeige mit den neuen Parametern neu erstellen.

**F: Warum aktualisiert [!DNL Marketo Measure] alle [!DNL Facebook] Anzeigen?**

A: Der [!DNL Marketo Measure] besteht darin, alle Anzeigen zu taggen, falls sie wieder aktiviert werden.

**F: Welche Berechtigung benötigt der verbundene Benutzer?**

A: ads_management, E-Mail

**F: Wie lange kann es dauern, Ausgabendaten zu importieren?**

A: 1 Stunde

**F: Wie lange kann es dauern, um Anzeigendaten zu importieren?**

A: 4 Stunden
