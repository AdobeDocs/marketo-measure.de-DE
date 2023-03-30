---
unique-page-id: 18874732
description: Best Practices zum Einrichten von UTM-Parametern - [!DNL Marketo Measure] - Produktdokumentation
title: Best Practices zum Einrichten von UTM-Parametern
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
source-git-commit: 51397a02872035fef41d308c1f855bcaecc29c4e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 3%

---

# Best Practices zum Einrichten von UTM-Parametern {#best-practices-for-setting-up-utm-parameters}

UTM-Parameter eignen sich hervorragend, um Ihre Marketing-Daten zu zerteilen und zu würzen. [!DNL Marketo Measure] verwendet und erfasst alle UTM-Parameter, um Felder in Salesforce und in der [!DNL Marketo Measure] App. Mit diesen Informationen erhalten Sie ein detailliertes Verständnis davon, woher Ihre Leads, Chancen und geschlossenen/gewachten Angebote kommen.

Sie können die [Google URL Builder](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"} to set up your UTM parameters and add them to your links within your marketing efforts. Use this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} , wenn Sie eine einfachere Möglichkeit wünschen, alle UTM-Links zu verfolgen.

## Hohe Werte für jeden Parameter {#high-level-values-for-each-parameter}

**utm_medium**: Dieses Feld wird dem Feld Medium zugeordnet. Verwenden Sie utm_medium, um den Kanal auf hoher Ebene zu kennzeichnen.

z. B. [!UICONTROL Social], CPC, E-Mail, Web, organisch

Verwenden Sie dieses Feld nicht, um den Unterkanal aufzurufen.

**utm_source**: Dieses Feld wird dem Feld &quot;Touchpoint-Quelle&quot;zugeordnet. Verwenden Sie utm_source , um den Unterkanal zu definieren, aus dem der Lead stammt.

z. B. Facebook, Twitter, LinkedIn, Drip_email, Email_blast, Newsletter.

Halten Sie es einfach. Verwenden Sie diesen Parameter nicht, um den Anzeigentyp wie Retargeting, Sponsored usw. zu kennzeichnen. Fügen Sie kein utm_source = homepage, webdirect, website hinzu. [!DNL Marketo Measure] werden diese Informationen automatisch für Sie ausfüllen.

**utm_campaign**: Dieses Feld wird dem Anzeigenkampagnennamen zugeordnet. Verwenden Sie utm_campaign, um den Titel der Kampagne so zu kennzeichnen, wie er in der Anzeigenplattform vorhanden ist oder wie er intern referenziert wird.

Dies ist auch ein guter Parameter, um Geolocation, Netzwerk-Typ der Anzeige (Display v. search) usw. anzugeben.

Es wird empfohlen, Unterstriche anstelle von Leerzeichen zu verwenden und Interpunktion zu vermeiden. Dadurch wird die Wahrscheinlichkeit von Kodierungsfehlern durch Browser beim Lesen Ihrer Parameter verringert.

z. B. AU_Idea_for_an_App_50k

**utm_content**: Diese Zuordnung erfolgt auf Anzeigeninhalt. Verwenden Sie den Anzeigentitel im Parameter utm_content . Wenn es sich um eine Bildanzeige handelt, verwenden Sie den Anzeigentitel und schließen Sie die Anzeigendimensionen ein.

z. B. [Anzeigentitel] 200x400px

**utm_term**: Diese Zuordnung erfolgt über Suchbegrifftext. Verwenden Sie diesen Parameter, um den Suchbegriff im Zusammenhang mit der Auslösung der Anzeige zu kennzeichnen.

Wenn es keinen Suchbegriff für die Anzeige gibt, lassen Sie diesen Parameter leer.

z. B. iPhone App-Ideen

**Halten Sie es einfach und prägnant. Duplizieren Sie keine Bemühungen, Begriffe und Kanäle.**

Wir stellen uns die UTM-Hierarchie wie folgt vor:

Mittel > [!UICONTROL Quelle] > [!UICONTROL Kampagne] > [!UICONTROL Inhalt/Begriff]

z. B. Wenn eine [!UICONTROL display] Werbeanzeigen werden in Facebook platziert. Wir empfehlen Folgendes:

fakewebsite.com/

?utm_medium=social

&amp;utm_source=facebook

&amp;utm_campaign=Display_campaign_ID

&amp;utm_content=content_of_campaign

Beachten Sie, dass Begriffe/Kanäle nicht dupliziert werden und in diesem Fall utm_term nicht verwendet wird.

Wenden Sie sich bei Fragen an das Adobe Account Team (Ihren Kundenbetreuer) oder [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
