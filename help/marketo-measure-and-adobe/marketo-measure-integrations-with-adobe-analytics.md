---
description: '[!DNL Marketo Measure] Integrationen mit Adobe Analytics - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Integrationen mit  [!DNL Adobe Analytics]'
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 1%

---

# [!DNL Marketo Measure]-Integrationen mit Adobe Analytics {#marketo-measure-integrations-with-adobe-analytics}

Durch die Integration von B2B-Kundenattributen können Benutzer von [!DNL Marketo Measure] und Adobe Analytics ihre [!DNL Adobe Analytics]-Benutzerprofile mit wertvollen Metadaten anreichern, die von der [!DNL Marketo Measure] -Attributionsmodul abgeleitet wurden, sowie über seine Synchronisierungsfunktion mit CRMs ([!DNL Microsoft Dynamics] und [!DNL Salesforce]). Sie steht allen Kunden, die [!DNL Adobe Analytics] und [!DNL Marketo Measure] verwenden, kostenlos zur Verfügung.

>[!PREREQUISITES]
>
>Sie müssen sowohl über aktive Abonnements für [!DNL Marketo Measure] als auch für [!DNL Adobe Analytics] verfügen.

## Konfigurieren der Integration {#configuring-the-integration}

1. Erstellen Sie eine neue Source für Kundenattributdaten in Ihrer Experience Cloud-Konsole. Detaillierte Anweisungen [finden Sie hier](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=de).

   Beachten Sie die folgenden Informationen, die in den späteren Schritten benötigt werden:

   * Die Alias-ID, bei der es sich um einen beliebigen Wert handeln kann, den Sie benötigen. Wir empfehlen &quot;marketomeasure_id&quot;

   * Der Hostname und die Anmeldeinformationen des FTP-Servers (Benutzername und Kennwort)

1. Nachdem die Source für Kundenattributdaten erstellt wurde, fahren Sie mit dem Konfigurationsprozess fort, indem Sie im Admin-Menü [!DNL Marketo Measure] zum Bildschirm **[!UICONTROL Integrationen]** > **[!UICONTROL Verbindungen]** navigieren.

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Neue Kundenattributverbindung einrichten]** und befolgen Sie die Anweisungen zum Konfigurieren der Kundenattributintegration. In der Benutzeroberfläche werden Sie zur Eingabe der Alias-ID und FTP-Verbindungsinformationen aufgefordert, die Sie beim Erstellen der Source-Kundenattribute in Ihrer Core Services-Konsole erhalten haben. Wählen Sie den Satz von Kontoattributen aus, die Sie mit Ihrem [!DNL Adobe Analytics]-Konto synchronisieren möchten.

   Geben Sie Ihre Adobe IMS-Organisations-ID ein. Diese ID wird in der rechten unteren Ecke der Adobe Experience Cloud-Admin Console angezeigt. Weitere Informationen zum Auffinden dieser ID erhalten Sie vom Adobe Account Team (Ihrem Kundenbetreuer).

1. Nachdem Sie die Verbindung in Ihrem [!DNL Marketo Measure] -Konto erstellt haben, müssen Sie zur Experience Cloud-Konsole zurückkehren, um [das Schema zu validieren](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/validate-schema.html?lang=en). Sie müssen sich keine Gedanken über den FTP-Datei-Upload machen. [!DNL Marketo Measure] hat diesen Teil für Sie automatisiert. Wechseln Sie zum Bildschirm &quot;Schema anzeigen/bearbeiten&quot;für das Kundenattribut Source, das Sie in Schritt 1 erstellt haben, und teilen Sie der Adobe mit, welche Datentypen für die einzelnen Attribute gelten, die [!DNL Marketo Measure] in Ihren Namen hochgeladen hat. Sie können bei Bedarf auch neue Anzeigenamen für die hochgeladenen Attribute erstellen.

   Wenn Sie sich für die Synchronisierung von Attributen aus Ihrem CRM-Kontoobjekt entschieden haben, empfiehlt es sich dringend, neue Anzeigenamen für diese Attribute zu wählen, da [!DNL Marketo Measure] nur die Namen auf API-Ebene für diese Attribute ausfüllt, die normalerweise nicht für die Berichterstellung geeignet sind.

1. Der letzte Schritt besteht darin, Attributanmeldungen für die Experience Cloud-Anwendungen zu konfigurieren, in denen Sie die Attribute verwenden möchten. Sie können Abonnements für [!DNL Adobe Analytics] oder [!DNL Adobe Target] konfigurieren.  Weitere Informationen dazu, wie Sie das [tun, finden Sie hier](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/subscription.html).

## Attributbeschreibungen {#attribute-descriptions}

Wenn Sie eine B2B-Kundenattributverbindung erstellen, erstellt [!DNL Marketo Measure] automatisch einen Standardsatz von B2B-Kundenattributen für Sie. Diese Attribute werden in der folgenden Tabelle beschrieben.

Zusätzlich zu den unten aufgeführten Attributen können Sie auch alle Attribute hochladen, die mit dem Kontoobjekt in Ihrem CRM-System verbunden sind. Wenn mehr als ein Konto an den angegebenen Benutzer gebunden ist, füllt [!DNL Marketo Measure] alle übereinstimmenden Kontoattributwerte in einer durch Semikolon getrennten Liste.

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
   <td>Die Kontonamen, die mit dem angegebenen Webbesucher verknüpft sind. Wenn mehr als ein Konto mit dem angegebenen Benutzer verknüpft ist, füllt [!DNL Marketo Measure] alle übereinstimmenden Kontonamen in einer durch Semikolon getrennten Liste auf.<br/>
   <strong>Hinweis: </strong> account.name ist der Name auf Salesforce-API-Ebene für das Attribut name des Kontoobjekts. Sie können während des Schritts zur Schemavalidierung der Integrationskonfiguration (Schritt 4) einen besseren Anzeigenamen (z. B. "Unternehmen") für dieses Attribut auswählen.</td>
  </tr>
  <tr> 
   <td>Zugewiesene Umsätze - MODEL›</td> 
   <td>Der Umsatz, der diesem Kunden aufgrund seiner Verbindung mit geschlossenen Angeboten in Ihrem CRM zugeordnet wurde, berechnet durch die Attributionsmodul [!DNL Marketo Measure].<br/>
   Es gibt eines dieser Attribute für jedes Attributionsmodell, das Ihre [!DNL Marketo Measure] -Abonnements zulassen (z. B. "Zugeordneter Umsatz - Vollständiger Pfad").</td>
  </tr>
  <tr> 
   <td>Tiefe Trichterphase</td> 
   <td>Die tiefste Trichterphase aller mit dem angegebenen Benutzer verbundenen Öffnungsmöglichkeiten.</td>
  </tr>
  <tr> 
   <td>Offene Chancen</td> 
   <td>Eine durch Semikolons getrennte Liste der Opportunity-IDs, an die der angegebene Benutzer gemäß Ihren CRM-Daten gebunden ist.</td>
  </tr> 
 </tbody> 
</table>

**Ein Hinweis zu den Attributbeschränkungen**

Die über diese Integration angezeigten Attribute werden mit Ihren vertraglichen Attributbeschränkungen in [!DNL Adobe Analytics] und [!DNL Adobe Target] angerechnet. Nur Attribute, die über ein Attributabonnement (Schritt 5 in [Konfigurieren der Integration](#configuring-the-integration)) angezeigt werden, werden Ihrer Beschränkung für die abonnierte Anwendung angerechnet.

## Häufig gestellte Fragen (FAQ) {#faqs}

**Wie ändere ich den Satz von Attributen, die ich über diese Integration freigeben möchte?**

Damit ein Attribut, das von [!DNL Marketo Measure] für Ihre Adobe IMS-Organisation über diese Integration freigegeben wird, sichtbar ist und in [!DNL Adobe Analytics] verwendet wird, muss es über eine in der Core Services-Konsole konfigurierte Attributanmeldung angezeigt werden. Wenn Sie also ein Attribut entfernen möchten, damit es nicht mehr in [!DNL Adobe Analytics] angezeigt wird, können Sie dies erreichen, indem Sie einfach das Attributabonnement löschen.

Sie können auch die B2B-Kundenattributverbindung in [!DNL Marketo Measure] löschen und mit dem Attribut neu erstellen, das Sie nicht mehr von der Verbindungskonfiguration freigeben möchten. Um der Integration Attribute hinzuzufügen, müssen Sie die vorhandene Verbindung löschen und eine neue Verbindung mit den gewünschten Attributen erstellen, die der Konfiguration hinzugefügt werden.

In Anbetracht der obigen Ausführungen wird dringend empfohlen, bei der erstmaligen Konfiguration der Attributverbindung bei der Auswahl von Attributen möglichst umfassend zu sein.

**Welche Anwendungsbeispiele gibt es für diese Integration?**

1. Kontobasierte Traffic-Metriken: Mithilfe des Kontonamenattributs können Sie Segmente eines oder mehrerer Zielkonten in Adobe Analytics erstellen und die Traffic-Metriken der Site nur für die Untergruppe des Traffics analysieren, der von Zielkonten stammt.
1. Content Analytics: Verwenden Sie die Umsatzmetrik, um zu analysieren, welcher Site-Inhalt für Kunden, die Ihr Produkt oder Ihren Service letztendlich erwerben, oder für Kunden, die eine bestimmte Trichterphase von Interesse erreichen, am interessantesten ist.
1. Live-Deal-Support: Ermöglichen Sie Ihrem Verkaufsteam umsetzbare Einblicke, indem Sie das Site-Verhalten für Benutzer analysieren, die mit einer bestimmten Opportunity in Ihrem CRM-System verbunden sind.
