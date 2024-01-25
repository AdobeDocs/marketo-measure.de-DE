---
description: Fehlerbenachrichtigungen - [!DNL Marketo Measure] - Produktdokumentation
title: Fehlerbenachrichtigungen
hide: true
hidefromtoc: true
feature: Fundamentals
source-git-commit: b4fadc6519761975736ce7a0e4f99a30c589c9af
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# Fehlerbenachrichtigungen {#error-notifications}

Im Folgenden finden Sie eine Liste von Fehlern, die Sie über In-App-Benachrichtigungen oder E-Mails erhalten können. Wenn Sie eines davon erhalten, führen Sie die entsprechenden Schritte zur Fehlerbehebung aus. Wenn das Problem durch diese Schritte nicht gelöst wird, wenden Sie sich an [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support).

<table>
  <tbody>
    <tr>
      <th style="width:31%">Fehlercode</th>
      <th style="width:23%">Benachrichtigungsbeispiel</th>
      <th style="width:23%">Beschreibung</th>
      <th style="width:23%">Schritte zur Fehlerbehebung</th>
    </tr>
    <tr>
      <td>API_DISABLED</td>
      <td>Fehler beim CRM-Import : API_DISABLED : API-Aufrufe wurden für diesen Benutzer deaktiviert.</td>
      <td>Die API-Berechtigung wurde für den Marketo Measure-Benutzer deaktiviert.</td>
      <td>Weitere Informationen finden Sie in der folgenden Salesforce-Dokumentation <a href="https://help.salesforce.com/s/articleView?id=sf.branded_apps_commun_api_permset.htm&amp;type=5">So aktivieren Sie den API-Zugriff</a>.</td>
    </tr>
    <tr>
      <td>API_LIMIT_EXCEEDED</td>
      <td>Fehler während CRM-Export : PI_LIMIT_EXCEEDED</td>
      <td>Die API-Grenze des CRM wurde überschritten (24 Stunden).</td>
      <td>Hilfe zur Anpassung der API-Kreditzuweisungen finden Sie in der folgenden Dokumentation für Ihr CRM:</p>
          <ul>
            <li><a href="https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/service-protection-monitoring">Dynamics</a>
            </li>
            <li><a href="https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm">Salesforce</a>
            </li>
          </ul>
          <p>Sie können die CRM-Gutschriften, die Marketo Measure verwendet, auch wie folgt anpassen:</p>
          <ul>
            <li>Navigieren Sie zu <b>Einstellungen</b> &gt; <b>CRM</b> &gt; <b>Allgemein</b></li>
            <li>Tägliche CRM-API-Beschränkung aktualisieren<br/>
              <ul>
                <li><b>Hinweis: Der Standardwert ist 100.000</b></li>
              </ul>
            </li>
          </ul>
          <p>
           <img src="assets/error-notifications-1.png">
          </p>
      </td>
    </tr>
    <tr>
      <td>INVALID_ADOBE_ANALYTICS_CONFIGURATION</td>
      <td>Fehler beim AdobeAnalytics-Export: INVALID_ADOBE_ANALYTICS_CONFIGURATION : Fehler: Upload nicht erlaubt. Bitte bestätigen Sie das Datenquellenschema vor dem Hochladen. Datenquellen-ID:1234</td>
      <td>Die Adobe Analytics-Integration ist nicht korrekt konfiguriert.</td>
      <td>Informationen zur korrekten Konfiguration finden Sie in den folgenden Hilfeartikeln:
        <ul>
          <li>
            <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Marketo Measure-Integrationen mit Adobe Analytics</a>
          </li>
          <li>
            <a href="https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html">Erstellen einer Kundenattributquelle und Hochladen der Datendatei</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INVALID_CURRENCY_ISO_CODE</td>
      <td>Fehler während des Anzeigenimports: INVALID_CURRENCY_ISO_CODE: Währung XXX wird von Marketo Measure nicht unterstützt.
      <p>
      Fehler beim Anzeigenimport: INVALID_CURRENCY_ISO_CODE : Währung XXX für Konto für 1234 wird von Marketo Measure nicht unterstützt.</td>
      <td>Es wurde eine nicht unterstützte Währung gefunden.</td>
      <td>Stellen Sie im in der Benachrichtigung angegebenen Quellsystem (Anzeige, CRM, Marketo) sicher, dass die dem Datensatz zugeordnete Währung eine unterstützte und gültige Währung aufweist. Unterstützte Währungen werden von ISO-Währungsstandards abgeleitet.</td>
    </tr>
    <tr>
      <td>MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Fehler beim CRM-Export: MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Marketo Measure fehlt die Berechtigung "Konvertierte Leads anzeigen/bearbeiten"</td>
      <td>Hilfe zur Aktivierung dieser Berechtigung in Ihrem CRM-System finden Sie im folgenden Experience League-Dokument .<br/>
          <a href="/help/marketo-measure-salesforce-reporting/additional-functionality/enabling-the-permission-to-edit-converted-leads.md">Aktivierung der Berechtigung zum Bearbeiten konvertierter Leads</a></td>
    </tr>
    <tr>
      <td>MISSING_FIELD_READ_PERMISSION</td>
      <td>Fehler beim CRM-Import: MISSING_FIELD_READ_PERMISSION : Entitätstyp "Event": INVALID_FIELD:<br/>
    SystemModstamp,IsDeleted,WHOId,bizible2__Bizible_Touchpoint_Date__c</td>
      <td>Marketo Measure fehlt Leseberechtigungen für ein erforderliches Feld.</td>
      <td>In den folgenden Hilfeartikeln finden Sie Anleitungen zu den Berechtigungen, die Marketo Measure erfordert:
        <ul>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Dynamics</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_ISREPLICATEABLE_PERMISSION</td>
      <td>Fehler beim CRM-Import: MISSING_ISREPLICATEABLE_PERMISSION : Es fehlt die Berechtigung IsReplicateable für Campaign</td>
      <td>Diese Berechtigung ist für Salesforce-Objekte erforderlich, damit wir Ihre Marketo Measure und Salesforce synchronisieren können.</td>
      <td>Wenden Sie sich an den Salesforce-Support , um Unterstützung beim Festlegen der replizierbaren Berechtigung für Objekte zu erhalten.</td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_READ_PERMISSION</td>
      <td>Fehler beim CRM-Import: MISSING_OBJECT_READ_PERMISSION : Entitätstyp Campaign': CRM ErrorCode: MISSING_PERMISSION</td>
      <td>Marketo Measure fehlt Leseberechtigungen für ein erforderliches Objekt.</td>
      <td rowspan="2">In den folgenden Hilfeartikeln finden Sie Anleitungen zu den Berechtigungen, die Marketo Measure erfordert:
          <ul>
            <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Dynamics</a>
            </li>
            <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
            </li>
          </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_WRITE_PERMISSION</td>
      <td>Fehler beim CRM-Export: MISSING_OBJECT_WRITE_PERMISSION : Entitätstyp "bizible2_Bizible_Attribution_Touchpoint": CRM ErrorCode: MISSING_PERMISSION</td>
      <td>Marketo Measure fehlt Schreibberechtigungen für ein erforderliches Objekt.</td>
    </tr>
    <tr>
      <td>NULL_EMPTY_CURRENCY_ISO_CODE</td>
      <td>
        <p>
          Fehler beim CRM-Import: NULL_EMPTY_CURRENCY_ISO_CODE: Währungs-ISO-Code ist NULL oder leer, wenn MultiCurrency für RecordId 1234 aktiviert ist
      </td>
      <td>Die Währung muss ein unterstützter ISO-Währungscode sein.</td>
      <td>Stellen Sie im in der Benachrichtigung angegebenen Quellsystem (Anzeige, CRM, Marketo) sicher, dass die dem Datensatz zugeordnete Währung eine unterstützte und gültige Währung aufweist. Unterstützte Währungen werden von ISO-Währungsstandards abgeleitet.</td>
    </tr>
    <tr>
      <td>OPERATION_TOO_LARGE</td>
      <td>Fehler beim CRM-Import: OPERATION_TOO_LARGE : Für eine erfolgreiche Abfrage von Aktivitäten ist die Berechtigung "Alle Daten anzeigen"erforderlich.</td>
      <td>Die CRM-Einstellungen ermöglichen es Marketo Measure nicht, eine ausreichend große Datenmenge abzufragen</td>
      <td>Erteilen Sie Marketo Measure die Berechtigung "Alle Daten anzeigen"für das angegebene Objekt.
      <p>
      Weitere Informationen zur Berechtigung "Alle Daten anzeigen" <a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">finden Sie hier .</a>.</td>
    </tr>
    <tr>
      <td>UNSUPPORTED_CRM_PACKAGE_VERSION</td>
      <td>Fehler beim CRM-Import: UNSUPPORTED_CRM_PACKAGE_VERSION : Bitte aktualisieren Sie Ihr CRM-Paket</td>
      <td>Das aktuell erkannte Paket wird nicht mehr unterstützt.</td>
      <td>Aktualisieren Sie Ihr Paket auf die neueste Version:
        <ul>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/best-practices-for-marketo-measure-crm-package.md">Best Practices</a>
          </li>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md">Dynamics</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
