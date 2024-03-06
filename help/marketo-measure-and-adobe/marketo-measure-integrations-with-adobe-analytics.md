---
description: "[!DNL Marketo Measure] Integrationen mit Adobe Analytics - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Integrationen mit [!DNL Adobe Analytics]"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 1%

---

# [!DNL Marketo Measure]-Integrationen mit Adobe Analytics {#marketo-measure-integrations-with-adobe-analytics}

Die Integration von B2B-Kundenattributen ermöglicht die gegenseitige Nutzung von [!DNL Marketo Measure] und Adobe Analytics ihre [!DNL Adobe Analytics] Benutzerprofile mit wertvollen Metadaten aus [!DNL Marketo Measure] Attribution-Engine und ihre Synchronisierungsfunktion mit CRMs ([!DNL Microsoft Dynamics] und [!DNL Salesforce]). Sie steht allen Kunden, die [!DNL Adobe Analytics] und [!DNL Marketo Measure].

>[!PREREQUISITES]
>
>Sie müssen über aktive Abonnements für beide verfügen [!DNL Marketo Measure] und [!DNL Adobe Analytics].

## Konfigurieren der Integration {#configuring-the-integration}

1. Erstellen Sie eine neue Datenquelle für Kundenattribute in Ihrer Experience Cloud-Konsole. Detaillierte Anweisungen [finden Sie hier .](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=de).

   Beachten Sie die folgenden Informationen, die in den späteren Schritten benötigt werden:

   * Die Alias-ID, bei der es sich um einen beliebigen Wert handeln kann, den Sie benötigen. Wir empfehlen &quot;marketomeasure_id&quot;

   * Der Hostname und die Anmeldeinformationen des FTP-Servers (Benutzername und Kennwort)

1. Nachdem die Datenquelle &quot;Kundenattribute&quot;erstellt wurde, fahren Sie mit dem Konfigurationsprozess fort, indem Sie zur **[!UICONTROL Integrationen]** > **[!UICONTROL Verbindungen]** im Bildschirm [!DNL Marketo Measure] Administratormenü.

1. Klicken Sie auf **[!UICONTROL Einrichten einer neuen Kundenattributverbindung]** und befolgen Sie die Anweisungen zum Konfigurieren der Integration von Kundenattributen . In der Benutzeroberfläche werden Sie zur Eingabe der Alias-ID und FTP-Verbindungsinformationen aufgefordert, die Sie beim Erstellen der Kundenattributquelle in Ihrer Core Services Console erhalten haben. Wählen Sie den Satz von Kontoattributen aus, die Sie mit Ihrer [!DNL Adobe Analytics] -Konto.

   Geben Sie Ihre Adobe IMS-Organisations-ID ein. Diese ID wird in der rechten unteren Ecke der Adobe Experience Cloud-Admin Console angezeigt. Weitere Informationen zum Auffinden dieser ID erhalten Sie vom Adobe Account Team (Ihrem Kundenbetreuer).

1. Nachdem Sie die Verbindung in Ihrem [!DNL Marketo Measure] -Konto, müssen Sie zurück zu Ihrer Experience Cloud-Konsole wechseln, um [Prüfen des Schemas](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/validate-schema.html?lang=en). Sie müssen sich keine Gedanken über den FTP-Datei-Upload machen. [!DNL Marketo Measure] hat diesen Teil für Sie automatisiert. Navigieren Sie zum Bildschirm &quot;Schema anzeigen/bearbeiten&quot;für die Kundenattributquelle, die Sie in Schritt 1 erstellt haben, und teilen Sie Adobe mit, welche Datentypen für die einzelnen Attribute gelten, die [!DNL Marketo Measure] in Ihrem Namen hochgeladen hat. Sie können bei Bedarf auch neue Anzeigenamen für die hochgeladenen Attribute erstellen.

   Wenn Sie sich für die Synchronisierung von Attributen aus Ihrem CRM-Kontoobjekt entschieden haben, wird dringend empfohlen, neue Anzeigenamen zu wählen, wie [!DNL Marketo Measure] füllt nur die Namen auf API-Ebene für diese Attribute, die normalerweise nicht berichterstellungsfreundlich sind.

1. Der letzte Schritt besteht darin, Attributanmeldungen für die Experience Cloud-Anwendungen zu konfigurieren, in denen Sie die Attribute verwenden möchten. Sie können Abonnements für [!DNL Adobe Analytics] oder [!DNL Adobe Target].  Weitere Informationen dazu [finden Sie hier .](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/subscription.html).

## Attributbeschreibungen {#attribute-descriptions}

Wenn Sie eine B2B-Kundenattributverbindung erstellen, [!DNL Marketo Measure] erstellt automatisch einen Standardsatz von B2B-Kundenattributen für Sie. Diese Attribute werden in der folgenden Tabelle beschrieben.

Zusätzlich zu den unten aufgeführten Attributen können Sie auch alle Attribute hochladen, die mit dem Kontoobjekt in Ihrem CRM-System verbunden sind. Wenn mehr als ein Konto an den jeweiligen Benutzer gebunden ist, [!DNL Marketo Measure] füllt alle übereinstimmenden Kontoattributwerte in einer durch Semikolon getrennten Liste.

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><b>Attributname</b></td> 
   <td><b>Beschreibung</b></td>
  </tr> 
  <tr> 
   <td>Account.Name</td> 
   <td>Die Kontonamen, die mit dem angegebenen Webbesucher verknüpft sind. Wenn mehr als ein Konto an den jeweiligen Benutzer gebunden ist, [!DNL Marketo Measure] füllt alle übereinstimmenden Kontonamen in einer durch Semikolon getrennten Liste auf.<br/>
   <strong>Hinweis:</strong> account.name ist der Name der Salesforce-API-Ebene für das Attribut name im Kontoobjekt. Sie können während des Schritts zur Schemavalidierung der Integrationskonfiguration (Schritt 4) einen besseren Anzeigenamen (z. B. "Unternehmen") für dieses Attribut auswählen.</td>
  </tr>
  <tr> 
   <td>Zugewiesene Umsätze - MODEL›</td> 
   <td>Der Umsatz, der diesem Kunden aufgrund seiner Verbindung mit geschlossenen Chancen in Ihrem CRM-System zugeordnet wurde, berechnet durch die [!DNL Marketo Measure] Attributionsmodul.<br/>
   Es gibt eines dieser Attribute für jedes Attributionsmodell, das Ihre [!DNL Marketo Measure] Abonnements ermöglichen (z. B. "Zugewiesener Umsatz - Vollständiger Pfad").</td>
  </tr>
  <tr> 
   <td>Tiefe Trichterphase</td> 
   <td>Die tiefste Trichterphase aller mit dem angegebenen Benutzer verbundenen Öffnungsmöglichkeiten.</td>
  </tr>
  <tr> 
   <td>Offene Opportunities</td> 
   <td>Eine durch Semikolons getrennte Liste der Opportunity-IDs, an die der angegebene Benutzer gemäß Ihren CRM-Daten gebunden ist.</td>
  </tr> 
 </tbody> 
</table>

**Ein Hinweis zu Attributbeschränkungen**

Die über diese Integration angezeigten Attribute werden mit Ihren vertraglichen Attributbeschränkungen in [!DNL Adobe Analytics] und [!DNL Adobe Target]. Nur Attribute, die über ein Attributabonnement angezeigt werden (Schritt 5 in [Konfigurieren der Integration](#configuring-the-integration)) gegen Ihre Beschränkung für die abonnierte Anwendung.

## Häufig gestellte Fragen {#faqs}

**Wie ändere ich den Satz von Attributen, die ich über diese Integration freigeben möchte?**

Für ein Attribut, das von [!DNL Marketo Measure] zu Ihrer Adobe IMS-Organisation über diese Integration hinzufügen, um in [!DNL Adobe Analytics]muss sie über ein in der Core Services-Konsole konfiguriertes Attributabonnement angezeigt werden. Wenn Sie daher ein Attribut entfernen möchten, damit es nicht mehr in [!DNL Adobe Analytics], können Sie dies einfach durch Löschen des Attributabonnements erreichen.

Sie können auch die B2B-Kundenattributverbindung in [!DNL Marketo Measure] und erstellen Sie es mit dem Attribut neu, das Sie nicht mehr von der Verbindungskonfiguration ausschließen möchten. Um der Integration Attribute hinzuzufügen, müssen Sie die vorhandene Verbindung löschen und eine neue Verbindung mit den gewünschten Attributen erstellen, die der Konfiguration hinzugefügt werden.

In Anbetracht der obigen Ausführungen wird dringend empfohlen, bei der erstmaligen Konfiguration der Attributverbindung bei der Auswahl von Attributen möglichst umfassend zu sein.

**Welche Anwendungsbeispiele gibt es für diese Integration?**

1. Kontobasierte Traffic-Metriken: Mithilfe des Kontonamenattributs können Sie Segmente eines oder mehrerer Zielkonten in Adobe Analytics erstellen und die Traffic-Metriken der Site nur für die Untergruppe des Traffics analysieren, der von Zielkonten stammt.
1. Content Analytics: Verwenden Sie die Umsatzmetrik, um zu analysieren, welcher Site-Inhalt für Kunden, die Ihr Produkt oder Ihren Service letztendlich erwerben, oder für Kunden, die eine bestimmte Trichterphase von Interesse erreichen, am interessantesten ist.
1. Live-Deal-Support: Ermöglichen Sie Ihrem Verkaufsteam umsetzbare Einblicke, indem Sie das Site-Verhalten für Benutzer analysieren, die mit einer bestimmten Opportunity in Ihrem CRM-System verbunden sind.
