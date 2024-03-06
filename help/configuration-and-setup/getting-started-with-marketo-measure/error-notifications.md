---
description: Fehlerbenachrichtigungen - [!DNL Marketo Measure]
title: Fehlerbenachrichtigungen
feature: Fundamentals
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 83%

---

# Fehlerbenachrichtigungen {#error-notifications}

Im Folgenden finden Sie eine Liste von Fehlern, die Sie möglicherweise per In-App-Benachrichtigung oder E-Mail erhalten. Wenn Sie eines davon erhalten, führen Sie die entsprechenden Schritte zur Fehlerbehebung aus. Falls das Problem durch diese Schritte nicht gelöst werden kann, wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support).

<table>
  <tbody>
    <tr>
      <th style="width:31%">Fehler-Code</th>
      <th style="width:23%">Benachrichtigungsbeispiel</th>
      <th style="width:23%">Beschreibung</th>
      <th style="width:23%">Schritte zur Fehlerbehebung</th>
    </tr>
    <tr>
      <td>API_DISABLED</td>
      <td>Fehler beim CRM-Import : API_DISABLED : API-Aufrufe wurden für diese Benutzerin bzw. diesen Benutzer deaktiviert</td>
      <td>Die API-Berechtigung wurde für die Marketo Measure-Benutzerin bzw. den -Benutzer deaktiviert.</td>
      <td>Weitere Informationen finden Sie in der Salesforce-Dokumentation zum Thema <a href="https://help.salesforce.com/s/articleView?language=en_US&amp;id=sf.branded_apps_commun_api_permset.htm&amp;type=5">Aktivieren des API-Zugriffs</a>.</td>
    </tr>
    <tr>
      <td>API_LIMIT_EXCEEDED</td>
      <td>Fehler beim CRM-Export : API_LIMIT_EXCEEDED</td>
      <td>Die API-Grenze des CRM wurde überschritten (24 Stunden).</td>
      <td>Hilfe zur Anpassung der API-Credits-Zuweisungen finden Sie in der folgenden Dokumentation für Ihr CRM:</p>
          <ul>
            <li><a href="https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/service-protection-monitoring">Dynamics</a>
            </li>
            <li><a href="https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm">Salesforce</a>
            </li>
          </ul>
          <p>Sie können die CRM-Credits, die Marketo Measure verwendet, auch wie folgt anpassen:</p>
          <ul>
            <li>Navigieren Sie zu <b>Einstellungen</b> &gt; <b>CRM</b> &gt; <b>Allgemein</b></li>
            <li>Aktualisieren Sie das tägliche CRM-API-Limit<br/>
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
      <td>Fehler beim Adobe Analytics-Export: INVALID_ADOBE_ANALYTICS_CONFIGURATION : Fehler: Upload nicht erlaubt. Validieren Sie das Datenquellenschema vor dem Hochladen. Datenquellen-ID:1234</td>
      <td>Die Adobe Analytics-Integration ist nicht korrekt konfiguriert.</td>
      <td>Lesen Sie die folgenden Hilfeartikel, um eine korrekte Konfiguration sicherzustellen:
        <ul>
          <li>
            <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Marketo Measure-Integrationen mit Adobe Analytics</a>
          </li>
          <li>
            <a href="https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=de">Erstellen einer Kundenattributquelle und Hochladen der Datendatei</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INVALID_CURRENCY_ISO_CODE</td>
      <td>Fehler beim Anzeigenimport: INVALID_CURRENCY_ISO_CODE: Die Währung XXX wird von Marketo Measure nicht unterstützt.
      <p>
      Fehler beim Anzeigenimport: INVALID_CURRENCY_ISO_CODE : Die Währung XXX für das Konto für 1234 wird von Marketo Measure nicht unterstützt.</td>
      <td>Es wurde eine nicht unterstützte Währung gefunden.</td>
      <td>Im in der Benachrichtigung angegebenen Quellsystem (Anzeige, CRM, Marketo) stellt sicher, dass die dem Datensatz zugeordnete Währung eine unterstützte und gültige Währung aufweist. Unterstützte Währungen werden von ISO-Währungsstandards abgeleitet.</td>
    </tr>
    <tr>
      <td>MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Fehler beim CRM-Export: MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Marketo Measure hat keine Berechtigung zum Anzeigen/Bearbeiten konvertierter Leads</td>
      <td>Hilfe zur Aktivierung dieser Berechtigung in Ihrem CRM-System finden Sie im folgenden Experience League-Dokument<br/>
<a href="/help/marketo-measure-salesforce-reporting/additional-functionality/enabling-the-permission-to-edit-converted-leads.md">Aktivieren der Berechtigung zum Bearbeiten konvertierter Leads</a></td>
    </tr>
    <tr>
      <td>MISSING_FIELD_READ_PERMISSION</td>
      <td>Fehler beim CRM-Import: MISSING_FIELD_READ_PERMISSION : Entitätstyp 'Ereignis': INVALID_FIELD:<br/>
    SystemModstamp,IsDeleted,WhoId,bizible2__Bizible_Touchpoint_Date__c</td>
      <td>Marketo Measure hat für ein erforderliches Feld keine Leseberechtigungen.</td>
      <td>In den folgenden Hilfeartikeln finden Sie Anleitungen zu den erforderlichen Berechtigungen für Marketo Measure:
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
      <td>Zur Synchronisierung von Marketo Measure und Salesforce ist diese Berechtigung für Salesforce-Objekte erforderlich.</td>
      <td>Der Salesforce-Support hilft Ihnen gerne dabei, die replizierbare Berechtigung für Objekte festzulegen.</td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_READ_PERMISSION</td>
      <td>Fehler beim CRM-Import: MISSING_OBJECT_READ_PERMISSION : Entitätstyp Campaign': CRM-Fehler-Code: MISSING_PERMISSION</td>
      <td>Marketo Measure hat keine Leseberechtigungen für ein erforderliches Objekt.</td>
      <td rowspan="2">In den folgenden Hilfeartikeln finden Sie Anleitungen zu den erforderlichen Berechtigungen für Marketo Measure:
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
      <td>Fehler beim CRM-Export: MISSING_OBJECT_WRITE_PERMISSION : Entitätstyp 'bizible2_Bizible_Attribution_Touchpoint': CRM-Fehler-Code: MISSING_PERMISSION</td>
      <td>Marketo Measure hat keine Schreibberechtigungen für ein erforderliches Objekt.</td>
    </tr>
    <tr>
      <td>NULL_EMPTY_CURRENCY_ISO_CODE</td>
      <td>
        <p>
          Fehler beim CRM-Import: NULL_EMPTY_CURRENCY_ISO_CODE: ISO-Währungs-Code ist NULL oder leer, wenn MultiCurrency für RecordId 1234 aktiviert ist
      </td>
      <td>Die Währung muss ein unterstützter ISO-Währungs-Code sein.</td>
      <td>Im in der Benachrichtigung angegebenen Quellsystem (Anzeige, CRM, Marketo) stellt sicher, dass die dem Datensatz zugeordnete Währung eine unterstützte und gültige Währung aufweist. Unterstützte Währungen werden von ISO-Währungsstandards abgeleitet.</td>
    </tr>
    <tr>
      <td>OPERATION_TOO_LARGE</td>
      <td>Fehler beim CRM-Import: OPERATION_TOO_LARGE : Für eine erfolgreiche Abfrage von Aktivitäten ist die Berechtigung 'Alle Daten anzeigen' erforderlich.</td>
      <td>Mit den CRM-Einstellungen kann Marketo Measure keine ausreichend große Datenmenge abrufen</td>
      <td>Erteilen Sie Marketo Measure die Berechtigung 'Alle Daten anzeigen' für das angegebene Objekt.
      <p>
      Weitere Informationen zur Berechtigung 'Alle Daten anzeigen' <a href="https://developer.salesforce.com/docs/atlas.de-DE.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">sind hier zu finden</a>.</td>
    </tr>
    <tr>
      <td>UNSUPPORTED_CRM_PACKAGE_VERSION</td>
      <td>Fehler beim CRM-Import: UNSUPPORTED_CRM_PACKAGE_VERSION : Aktualisieren Sie Ihr CRM-Paket</td>
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
