---
unique-page-id: 18874680
description: '[!DNL Facebook] API - [!DNL Marketo Measure]'
title: '[!DNL Facebook] API'
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
feature: APIs, Integration, UTM Parameters
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 3%

---

# [!DNL Facebook] API {#facebook-api}

## Einführung {#introduction}

Ähnlich wie bei unseren AdWords- und [!DNL Bing Ads]-Integrationen führt unsere [!DNL Facebook]-Integration zwei grundlegende Aktionen aus:

* Alle [!DNL Facebook] Anzeigen automatisch mit einem [!DNL Marketo Measure] -Parameter (_bf) versehen
* Informationen zu Anzeigenkosten für alle aktiven Facebook-Anzeigen herunterladen

## Konfigurieren der [!DNL Facebook]-Integration {#how-to-configure-the-facebook-integration}

Was die Einrichtung anbelangt, so müssen in der [!DNL Marketo Measure]-App sieben Schritte ausgeführt werden.

1. Navigieren Sie zu [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} und melden Sie sich an.
1. Wählen Sie unter Mein Konto die Option **[!UICONTROL Einstellungen]** aus.
1. Wählen Sie unter &quot;Integrationen&quot;die Option **[!UICONTROL Verbindungen]**.
1. Wählen Sie **[!UICONTROL Neue Werbeverbindung einrichten]** aus. Daraufhin wird ein Popup-Fenster angezeigt. Wählen Sie **[!UICONTROL Facebook]** aus und melden Sie sich mit Ihren Facebook-Anmeldedaten an.

   >[!NOTE]
   >
   >Die Person, die das [!DNL Facebook Ads] -Konto verbindet, muss ein Administrator innerhalb des [!DNL Facebook Ads] -Kontos sein.

1. Sobald [!DNL Marketo Measure] mit Ihrem Facebook-Konto verbunden ist, klicken Sie auf das Stiftsymbol neben dem Konto.
1. Verschieben Sie in dieser Ansicht das &quot;Auto-Tagging?&quot; auf &quot;Ja&quot;umschalten. Aktivieren Sie dann das Kontrollkästchen im Abschnitt [!UICONTROL Mehr erfahren] , um den Nutzungsbedingungen zuzustimmen. Stellen Sie sicher, dass der Umschalter [!UICONTROL Automatisches Tagging] weiterhin auf &quot;[!UICONTROL Ja]&quot;festgelegt ist.

## Konto verbinden {#connecting-the-account}

![](assets/1.gif)

## Aktivieren der Automatisierung {#enabling-autotagging}

>[!NOTE]
>
>Wenn Sie das automatische Tagging aktivieren, werden wir den Konversionsverlauf und den Social-Testversand aller Anzeigen zurücksetzen, die wir taggen. Es wird dringend empfohlen, [diese Daten als CSV](https://www.facebook.com/business/help/205067636197240) zu exportieren, bevor Sie das automatische Tagging aktivieren.

![](assets/2-2.png)

Sobald Sie die Integration aktiviert haben, beginnt [!DNL Marketo Measure] mit dem Herunterladen der Kosten auf Anzeigenebene in das [!DNL Marketo Measure Marketing ROI]-Dashboard.

Damit die Integration ordnungsgemäß funktioniert, müssen Sie das automatische Tagging in Ihrem [!DNL Facebook] -Konto aktivieren. Dadurch kann unser System einen _bf -Parameter für alle Anzeigenlinks hinzufügen. Dadurch wird der neue Parameter zusätzlich zu allen anderen Tracking-Parametern hinzugefügt, die Sie bereits zu Ihren [!DNL Facebook] -Anzeigen hinzugefügt haben.

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
   <td><p>Anzeigen-Kampagnen-ID</p></td> 
   <td><p>[[!DNL Facebook] Kampagnen-ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Name der Anzeigenkampagne </p></td> 
   <td><p>[[!DNL Facebook] Kampagnenname] oder [utm_campaign], falls angegeben</p></td> 
  </tr> 
  <tr> 
   <td><p>Anzeigengruppen-ID</p></td> 
   <td><p>[[!DNL Facebook] ID des Anzeigensets]</p></td> 
  </tr> 
  <tr> 
   <td><p>Werbegruppenname</p></td> 
   <td><p>[[!DNL Facebook] Name des Anzeigensets]</p></td> 
  </tr> 
  <tr> 
   <td><p>Touchpoint-Quelle</p></td> 
   <td><p>"[!DNL Facebook]" oder [utm_source] , falls angegeben</p></td> 
  </tr> 
  <tr> 
   <td><p>Medium</p></td> 
   <td><p>"Social"oder [utm_medium] , falls angegeben</p></td> 
  </tr> 
  <tr> 
   <td><p>Anzeigen-ID oder Creative_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[aus utm_content generierte benutzerdefinierte ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Anzeigeninhalt oder Creative_Name (Data Warehouse)</p></td> 
   <td><p>[utm_content] , falls angegeben</p></td> 
  </tr> 
  <tr> 
   <td><p>Schlüsselworttext oder Keyword_Name (Data Warehouse)</p></td> 
   <td><p>[utm_term] , falls angegeben</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Anzeigen-ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Anzeigenname]</p></td> 
  </tr> 
  <tr> 
   <td><p>keyword_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[aus utm_term generierte benutzerdefinierte ID]</p></td> 
  </tr> 
  <tr> 
   <td><p>Ad_Provider (Data Warehouse)</p></td> 
   <td><p>"[!DNL Facebook]"</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Unique_ID (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Kundennummer]</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Kontoname]</p></td> 
  </tr> 
 </tbody> 
</table>

## FAQs {#faq}

**Q: Welche [!DNL Facebook] Anzeigen werden von [!DNL Marketo Measure] unterstützt?**

A: Karussell, Einzelbild. Derzeit nicht Video, Bildschirmpräsentation oder Sammlung.

**Q: Was ist der soziale Schutz?**

A: Der soziale Beweis ist eine sichtbare Interaktion wie &quot;Gefällt mir&quot;-Klicks, Klicks, Kommentare und &quot;Teilen&quot;-Klicks.

**Q: Was passiert, wenn [!DNL Marketo Measure] die Anzeige markiert?**

A: [!DNL Facebook] lässt die Bearbeitung von Anzeigen nicht zu, sodass [!DNL Marketo Measure] die Kreativelemente, die die Ziel-URL enthalten, löschen und dann die Anzeige mit den neuen Parametern neu erstellen muss.

**Q: Warum aktualisiert [!DNL Marketo Measure] alle [!DNL Facebook] Anzeigen?**

A: Der [!DNL Marketo Measure]-Prozess besteht darin, alle Anzeigen für den Fall zu taggen, dass sie erneut aktiviert werden.

**Q: Welche Berechtigung benötigt der verbundene Benutzer?**

A: ads_management, email

**Q: Wie lange kann es dauern, Ausgabedaten zu importieren?**

A: 1 Stunde

**Q: Wie lange kann der Import von Anzeigendaten dauern?**

A: 4 Stunden
