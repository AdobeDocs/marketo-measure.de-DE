---
description: '[!DNL Marketo Measure] Integrationen mit Adobe Analytics - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Integrationen mit [!DNL Adobe Analytics]'
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 1%

---


# [!DNL Marketo Measure]-Integrationen mit Adobe Analytics {#marketo-measure-integrations-with-adobe-analytics}

Die Integration von B2B-Kundenattributen ermöglicht es gemeinsamen Benutzenden von [!DNL Marketo Measure] und Adobe Analytics, ihre [!DNL Adobe Analytics] Benutzerprofile mit wertvollen Metadaten anzureichern, die von der [!DNL Marketo Measure] Attributions-Engine abgeleitet werden, und dies über ihre Synchronisierungsfunktionen mit CRMs ([!DNL Microsoft Dynamics] und [!DNL Salesforce]). Es steht allen Kunden, die [!DNL Adobe Analytics] und [!DNL Marketo Measure] verwenden, kostenlos zur Verfügung.

>[!PREREQUISITES]
>Sie müssen über aktive Abonnements für [!DNL Marketo Measure] und [!DNL Adobe Analytics] verfügen.

## Integration konfigurieren {#configuring-the-integration}

1. Erstellen Sie eine neue Kundenattribut-Daten-Source in Ihrer Experience Cloud-Konsole. Detaillierte Anweisungen [finden Sie hier](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=de).

   Notieren Sie sich die folgenden Informationen, die in den späteren Schritten benötigt werden:

   * Die Alias-ID. Dabei kann es sich um einen beliebigen Wert handeln. Wir empfehlen „marketomeasure_id“

   * Der Host-Name und die Anmeldeinformationen des FTP-Servers (Benutzername und Kennwort)

1. Nachdem die Source für Kundenattributdaten erstellt wurde, setzen Sie den Konfigurationsprozess fort, indem Sie im **[!UICONTROL Admin-Menü zum Bildschirm]** Integrationen **[!UICONTROL >]** Verbindungen[!DNL Marketo Measure] navigieren.

1. Klicken Sie auf **[!UICONTROL Schaltfläche „Verbindung für neue Kundenattribute einrichten]** und folgen Sie den Anweisungen zum Konfigurieren der Integration von Kundenattributen. Die Benutzeroberfläche fordert Sie auf, die Alias-ID und die FTP-Verbindungsinformationen einzugeben, die Sie beim Erstellen der Source für Kundenattribute in Ihrer Core Services Console erhalten haben. Wählen Sie die Gruppe von Kontoattributen aus, die Sie mit Ihrem [!DNL Adobe Analytics]-Konto synchronisieren möchten.

   Geben Sie Ihre Adobe IMS-Organisations-ID ein. Diese ID wird unten rechts in Ihrem Adobe Experience Cloud Admin Console angezeigt. Weitere Hilfe zum Auffinden dieser ID erhalten Sie beim Adobe Account Team (Ihrem Account Manager).

1. Nachdem Sie die Verbindung in Ihrem [!DNL Marketo Measure]-Konto erstellt haben, müssen Sie zu Ihrer Experience Cloud-Konsole zurückkehren, um [&#x200B; Schema zu &#x200B;](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/validate-schema.html?lang=en). Sie müssen sich keine Gedanken über das Hochladen der FTP-Datei machen, [!DNL Marketo Measure] diesen Teil für Sie automatisiert hat. Gehen Sie zum Bildschirm „Schema anzeigen/bearbeiten“ für die Kundenattribut-Source, die Sie in Schritt 1 erstellt haben, und teilen Sie Adobe mit, welche Datentypen für die einzelnen Attribute gelten, die [!DNL Marketo Measure] in Ihrem Namen hochgeladen hat. Sie können bei Bedarf auch neue Anzeigenamen für die hochgeladenen Attribute erstellen.

   Wenn Sie Attribute aus Ihrem CRM-Kontoobjekt synchronisieren möchten, wird dringend empfohlen, neue Anzeigenamen für sie auszuwählen, da [!DNL Marketo Measure] nur die Namen auf API-Ebene für diese Attribute ausfüllt, was in der Regel nicht berichterstellungsfreundlich ist.

1. Der letzte Schritt besteht darin, Attributabonnements für die Experience Cloud-Programme zu konfigurieren, in denen Sie die Attribute verwenden möchten. Sie können Abonnements für [!DNL Adobe Analytics] oder [!DNL Adobe Target] konfigurieren.  Weitere Informationen dazu finden [&#x200B; hier](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/subscription.html).

## Attributbeschreibungen {#attribute-descriptions}

Wenn Sie eine B2B-Kundenattributverbindung erstellen, erstellt [!DNL Marketo Measure] automatisch einen Standardsatz von B2B-Kundenattributen für Sie. Diese Attribute werden in der folgenden Tabelle beschrieben.

Zusätzlich zu den unten aufgeführten können Sie auch alle Attribute hochladen, die an das Kontoobjekt in Ihrem CRM angehängt sind. Wenn mehr als ein Konto mit dem angegebenen Benutzer verknüpft ist, füllt [!DNL Marketo Measure] alle übereinstimmenden Kontoattributwerte in einer durch Semikolon getrennten Liste.

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
   <td>Die Kontonamen, die mit dem angegebenen Web-Besucher verknüpft sind. Wenn mehr als ein Konto mit dem angegebenen Benutzer verknüpft ist, füllt [!DNL Marketo Measure] alle übereinstimmenden Kontonamen in einer durch Semikolon getrennten Liste.<br/>
   <strong>Hinweis:</strong> account.name ist der Name auf Salesforce-API-Ebene für das Namensattribut im Kontoobjekt. Sie können während des Schritts zur Schemavalidierung der Integrationskonfiguration für dieses Attribut einen besseren Anzeigenamen (z. B. „Unternehmen„) auswählen (Schritt 4).</td>
  </tr>
  <tr>
   <td>Attributierter Umsatz - ‹MODEL›</td>
   <td>Der Umsatz, der diesem Kunden aufgrund seiner Verknüpfung mit abgeschlossenen Opportunitys in Ihrem CRM zugewiesen wird, wie von der [!DNL Marketo Measure] Attributions-Engine berechnet.<br/>
   Es gibt eines dieser Attribute für jedes Attributionsmodell, das Ihre [!DNL Marketo Measure]-Abonnements zulassen (z. B. „Attributierter Umsatz - Vollständiger Pfad„).</td>
  </tr>
  <tr>
   <td>Tiefste Funnel-Phase</td>
   <td>Das tiefste funnel-Stadium einer offenen Opportunity, die mit dem jeweiligen Benutzer verknüpft ist.</td>
  </tr>
  <tr>
   <td>Offene Chancen</td>
   <td>Eine durch Semikolon getrennte Liste der Opportunity-IDs, mit denen der angegebene Benutzer gemäß Ihren CRM-Daten verknüpft ist.</td>
  </tr>
 </tbody>
</table>

**Ein Hinweis zu Attributbeschränkungen**

Die Attribute, die über diese Integration angezeigt werden, werden anhand Ihrer vertraglichen Attributbeschränkungen in [!DNL Adobe Analytics] und [!DNL Adobe Target] gezählt. Nur Attribute, die über ein Attributabonnement (Schritt 5 in [Integration konfigurieren](#configuring-the-integration)) angezeigt werden, werden auf Ihrem Limit für die abonnierte Anwendung gezählt.

## Häufig gestellte Fragen (FAQ) {#faqs}

**Wie ändere ich den Satz von Attributen, die ich über diese Integration freigeben möchte?**

Damit ein Attribut, das von [!DNL Marketo Measure] über diese Integration für Ihre Adobe IMS-Organisation freigegeben wird, in [!DNL Adobe Analytics] sichtbar ist und verwendet wird, muss es über ein Attributabonnement angezeigt werden, das in der Core Services Console konfiguriert ist. Wenn Sie also ein Attribut entfernen möchten, sodass es nicht mehr in [!DNL Adobe Analytics] angezeigt wird, können Sie dies einfach erreichen, indem Sie das Attributabonnement löschen.

Sie können die B2B-Kundenattributverbindung auch in [!DNL Marketo Measure] löschen und mit dem Attribut neu erstellen, das nicht mehr freigegeben oder von der Verbindungskonfiguration ausgeschlossen werden soll. Entsprechend müssen Sie zum Hinzufügen von Attributen zur Integration die vorhandene Verbindung löschen und eine neue Verbindung mit den gewünschten Attributen erstellen, die der Konfiguration hinzugefügt werden.

Daher wird dringend empfohlen, bei der erstmaligen Konfiguration der Attributverbindung bei der Auswahl von Attributen so inklusiv wie möglich zu sein.

**Welche Anwendungsfälle gibt es für diese Integration?**

1. Account-basierte Traffic-Metriken: Mithilfe des Attributs „Kontoname“ können Sie Segmente eines oder mehrerer Zielkonten in Adobe Analytics erstellen und Site-Traffic-Metriken für nur die Untergruppe des Traffics analysieren, der von Zielkonten stammt.
1. Content Analytics: Verwenden Sie die Umsatzmetrik, um zu analysieren, welche Site-Inhalte für Kundinnen und Kunden am interessantesten sind, die letztendlich Ihr Produkt oder Ihre Dienstleistung erwerben, oder für diejenigen, die eine bestimmte Phase des funnel-Interesses erreichen.
1. Live-Deal-Support: Rüsten Sie Ihr Vertriebsteam mit umsetzbarem insight auf, indem Sie das Site-Verhalten für Benutzer analysieren, die mit einer bestimmten offenen Opportunity in Ihrem CRM verbunden sind.
