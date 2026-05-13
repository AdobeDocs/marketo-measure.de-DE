---
unique-page-id: 18874732
description: Best Practices zum Einrichten von UTM-Parametern – [!DNL Marketo Measure]
title: Best Practices zum Einrichten von UTM-Parametern
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
feature: UTM Parameters
TQID: https://experienceleague.adobe.com/DtL-NA5HSr40pOEJ0iCge--9Aa-reP1PRyJIw3qfAqM
product_v2: id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 459
ht-degree: 83%

---

# Best Practices zum Einrichten von UTM-Parametern {#best-practices-for-setting-up-utm-parameters}

UTM-Parameter eignen sich hervorragend, um die Slice-and-Dice-Technik auf Ihre Marketing-Daten anzuwenden. [!DNL Marketo Measure] verwendet und erfasst alle UTM-Parameter, um Felder in Salesforce und in der [!DNL Marketo Measure]-App aufzufüllen. Mit diesen Informationen erhalten Sie ein genaues Verständnis dafür, woher Ihre Leads, Opportunitys und abgeschlossenen/gewonnenen Deals stammen.

Sie können den [Google URL Builder](https://support.google.com/analytics/answer/1033867?hl=de){target="_blank"} verwenden, um Ihre UTM-Parameter einzurichten und sie im Rahmen Ihrer Marketing-Maßnahmen Ihren Links hinzuzufügen. Verwenden Sie diese [Google](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"}Tabelle, wenn Sie alle UTM-Links leichter verfolgen möchten.

## Allgemeine Werte für jeden Parameter {#high-level-values-for-each-parameter}

**utm_medium**: Dieses Feld ist dem Feld „Medium“ zugeordnet. Verwenden Sie „utm_medium“, um den übergeordneten Kanal anzugeben.

Beispiel: [!UICONTROL Social], CPC, email, web, organic

Verwenden Sie dieses Feld nicht, um den Subkanal zu benennen.

**utm_source**: Dieses Feld ist dem Feld „Touchpoint-Quelle“ zugeordnet. Verwenden Sie „utm_source“, um den Subkanal zu definieren, aus dem der Lead stammt.

Beispiel: Facebook, Twitter, LinkedIn, Drip_email, Email_blast, newsletter.

Achten Sie auf Einfachheit. Verwenden Sie diesen Parameter nicht, um die Anzeigenart, z. B. „Retargeting“, „Gesponsert“, anzugeben. Fügen Sie kein „utm_source = homepage, webdirect, website“ hinzu. [!DNL Marketo Measure] trägt diese Informationen automatisch für Sie ein.

**utm_campaign**: Dieses Feld ist dem Anzeigenkampagnennamen zugeordnet. Verwenden Sie „utm_campaign“, um den Titel der Kampagne so wie auf der Anzeigenplattform oder intern referenziert anzugeben.

Dies ist auch ein guter Parameter, um Geolocation, Ad-Netzwerk-Typ (Anzeige v. search), und so weiter.

Es wird empfohlen, Unterstriche anstelle von Leerzeichen zu verwenden und Interpunktion zu vermeiden. Dadurch wird die Wahrscheinlichkeit von Codierungsfehlern durch Browser beim Lesen Ihrer Parameter verringert.

Beispiel: AU_Idee_zu_einer_App_50k

**utm_content**: Dieses Feld ist dem Anzeigeninhalt zugeordnet. Verwenden Sie den Anzeigentitel im Parameter „utm_content“. Wenn es sich um eine Bildanzeige handelt, verwenden Sie den Anzeigentitel und schließen Sie die Abmessungen der Anzeige ein.

Beispiel: [Anzeigentitel] 200x400px

**utm_term**: Dieses Feld ist dem Keyword-Text zugeordnet. Verwenden Sie diesen Parameter, um das Keyword im Zusammenhang mit der Auslösung der Anzeige anzugeben.

Wenn es kein Keyword für die Anzeige gibt, lassen Sie diesen Parameter leer.

Beispiel: iPhone App-Ideen

**Achten Sie auf Einfachheit und Prägnanz. Duplizieren Sie keine Maßnahmen, Begriffe und Kanäle.**

Wir stellen uns die UTM-Hierarchie wie folgt vor:

Medium > [!UICONTROL Quelle] > [!UICONTROL Kampagne] > [!UICONTROL Inhalt/Begriff]

Beispiel: Wenn eine [!UICONTROL Display]-Anzeige auf Facebook platziert wird, empfehlen wir Folgendes:

fakewebsite.com/

?utm_medium=social

&amp;utm_source=facebook

&amp;utm_campaign=Display_campaign_ID

&amp;utm_content=content_of_campaign

Beachten Sie, dass Begriffe/Kanäle nicht dupliziert werden und in diesem Fall „utm_term“ nicht verwendet wird.

Bei Fragen wenden Sie sich an das Adobe Account Team (Ihren Account Manager) oder an den [Marketo Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
