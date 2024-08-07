---
unique-page-id: 37356030
description: E-Mail-Tracking-Parameter - [!DNL Marketo Measure]
title: E-Mail-Verfolgungsparameter
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
feature: Tracking
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 4%

---

# E-Mail-Verfolgungsparameter {#email-tracking-parameter}

Der Parameter [!DNL Marketo Measure] E-Mail-Tracking ermöglicht es Marketing-Experten, E-Mail-Klicks als Formularübermittlungen zu behandeln, sodass für diese Aktionen Touchpoints generiert werden. Ohne Verwendung eines E-Mail-Tracking-Parameters werden Clickthroughs aus einer E-Mail nur als &quot;Webbesuche&quot;behandelt, bis der Benutzer tatsächlich über eine Formularübermittlung oder einen Webchat mit der Site interagiert.

## Anwendungsfälle  {#use-cases}

**Webinar-Registrierung**: Das Marketing-Team sendet eine E-Mail-Einladung mit einer einzigen Schaltfläche, um sich für ein Webinar zu registrieren. Da die E-Mail bereits über die Informationen der Person verfügt, werden sie durch einen Klick automatisch registriert. Die Landingpage enthält den E-Mail-Tracking-Parameter. Wenn der Besucher durch die Seite klickt und auf die Bestätigungsseite gelangt, kann [!DNL Marketo Measure] die E-Mail-Adresse erfassen und den Clickthrough als Formularausfüllung behandeln, wodurch ein Touchpoint generiert wird.

**Herunterladen von Inhalten**: Das Content Marketing-Team möchte ein aktuelles eBook bewerben, das es mit einem direkten Download-Link aus einer E-Mail veröffentlicht hat. Wenn die E-Mail-Vorlage erstellt wurde, enthält die Seite zur Download-Bestätigung den E-Mail-Tracking-Parameter, sodass [!DNL Marketo Measure] die E-Mail-Adresse erfassen kann, wenn der Benutzer durch die E-Mail-Vorlage klickt. Ohne ein Formular auf der Site ausfüllen zu müssen, kann [!DNL Marketo Measure] einen Touchpoint für den Inhaltsdownload generieren. Dies liegt daran, dass die E-Mail sie mit dem E-Mail-Tracking-Parameter auf der Bestätigungsseite landet.

## Funktionsweise {#how-it-works}

Wenn ein Besucher auf Ihre Site gelangt, erwartet [!DNL Marketo Measure] eine Landingpage mit einer E-Mail-Adresse oder einer [!DNL Salesforce]-ID, damit wir diesen Besuch mit einer &quot;Formularübermittlung&quot;verknüpfen und einen Touchpoint für diese Aktivität generieren können.

Als Kunde erstellen Sie wie gewohnt eine E-Mail-Vorlage. Sobald es Zeit ist, die Landingpage für die Aktion hinzuzufügen, die Sie verfolgen möchten, müssen Sie entweder das Token, das Variablentag oder Makro bestimmen, das Ihre Marketing Automation-Plattform akzeptiert, um den Wert für jede Person dynamisch anzuzeigen.

Marketo Measure akzeptiert die folgenden Werte: E-Mail-Adresse, Salesforce-Lead-ID oder Salesforce-Kontakt-ID.

## Tag-Beispiele {#tag-examples}

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p>Marketing-Automation</p></th> 
   <th><p>Token/Tag/Makro </p></th> 
   <th><p>Beispiel</p></th> 
   <th><p>unterstützendes Material</p></th> 
  </tr> 
  <tr> 
   <td><p>Marketo</p></td> 
   <td><p>{{lead.email address} </p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}</p></td> 
   <td><p>https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/personalizing-landing-pages/tokens-overview.html</p></td> 
  </tr> 
  <tr> 
   <td><p>Pardot</p></td> 
   <td><p>%%email%% </p><p>ODER</p><p>%%user_crm_id%%</p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%</p></td> 
   <td><p>https://help.salesforce.com/s/articleView?language=en_US&amp;id=pardot_variable_tags_reference.htm&amp;type=5</p></td> 
  </tr> 
  <tr> 
   <td><p>Hubspot</p></td> 
   <td><p>(über Editor eingefügt)</p></td> 
   <td><p>Nicht zutreffend</p></td> 
   <td><p>https://knowledge.hubspot.com/website-pages/personalize-your-content</p></td> 
  </tr> 
  <tr> 
   <td><p>Akt-on</p></td> 
   <td><p>(über Message Composer eingefügt)</p></td> 
   <td><p>Nicht zutreffend</p></td> 
   <td><p>https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data</p></td> 
  </tr> 
 </tbody> 
</table>

Und schließlich müssen Sie innerhalb von [!DNL Marketo Measure] den Tracking-Parameter angeben, damit [!DNL Marketo Measure] den E-Mail- oder ID-Wert finden kann. Der Standardwert ist &quot;mailId&quot;, wie in den Beispielen oben und im Screenshot unten dargestellt. Geben Sie den Wert in Ihre Einstellungen in [!DNL Marketo Measure] ein und klicken Sie dann auf **[!UICONTROL Speichern]**.

![](assets/one.png)
