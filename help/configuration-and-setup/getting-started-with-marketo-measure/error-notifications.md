---
description: Fehlerbenachrichtigungen - [!DNL Marketo Measure]
title: Fehlerbenachrichtigungen
feature: Fundamentals
exl-id: ed07eed6-ddeb-4856-a1ac-ea3d571283f6
source-git-commit: 2b13a518d1be768a5c312ea4abdf2039aa22cf08
workflow-type: tm+mt
source-wordcount: '1675'
ht-degree: 30%

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
      <td>CANNOT_EXECUTE_FLOW_TRIGGER</td>
      <td>Fehler beim CRM-Export: CANNOT_EXECUTE_FLOW_TRIGGER : Entitätstyp "Kontakt"Geben Sie Ihrem Salesforce-Administrator diese Informationen.
Die Beschränkung hat überschritten Sie oder Ihr Unternehmen hat die Höchstgrenze für diese Funktion überschritten. Fehler-ID: 123456</td>
      <td>Der Datensatz kann nicht gespeichert werden, da er keine Trigger-Flow-Regel erfüllt, die in der Salesforce-Organisation eingerichtet ist.</td>
      <td>Überprüfen Sie die vollständigen Details der Benachrichtigungsmeldung und überprüfen Sie die Fluss-Trigger in der Salesforce-Organisation.
Salesforce-Dokumentation zu Fluss-Triggern <a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">finden Sie hier .</a>.
      </td>
    </tr>
    <tr>
      <td>CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY</td>
      <td>Fehler beim CRM-Export: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY : Entitätstyp 'Lead': CRM ErrorCode: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY, CRM ErrorMessage: System.LimitException: Apex CPU timelimit exceeded, RecordId: 0123456
      <p>
      Fehler beim CRM-Export: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY : Entitätstyp 'Konto': CRM ErrorCode: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY, CRM ErrorMessage: Entitätstyp kann nicht aktualisiert werden: Konto, RecordId: 0123456</td>
      <td>Trigger verhindern die Aktualisierung oder das Einfügen eines Objekts.
      <p>
      ODER
      <p>
      Fehlende Berechtigungen für das Objekt.</td>
      <td>Überprüfen Sie den Trigger-Code, der dazu führt, dass das Einfügen/Aktualisieren fehlschlägt. Weitere Informationen zu Triggern finden Sie in der folgenden Salesforce-Dokumentation .
        <ul>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.code_manage_triggers.htm&amp;type=5">Apex-Trigger</a>
          </li>
          <li><a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">Fluss-Trigger</a>
          </li>
        </ul>
        <p>
        Stellen Sie alle erforderlichen Berechtigungen für die <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Marketo Measure-Benutzer</a>.
      </td>
    </tr>
    <tr>
      <td>DUPLICATES_DETECTED</td>
      <td>Fehler beim CRM-Export: DUPLICATES_DETECTED : Entitätstyp 'Contact': CRM ErrorCode: DUPLICATES_DETECTED, CRM ErrorMessage: Sie erstellen einen doppelten Datensatz. Wir empfehlen stattdessen die Verwendung eines vorhandenen Datensatzes. RecordId: 0123456</td>
      <td>Der in die Salesforce-Org importierte Datensatz ist bereits vorhanden.</td>
      <td>
        <ul>
          <li><a href="https://help.salesforce.com/s/articleView?id=000390009&amp;type=1">Die Einstellung "Regel duplizieren"deaktivieren</a> , um Duplikate zuzulassen.
          </li>
          <li>Ausschluss des dedizierten Marketo Measure-Benutzers von <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierte Validierungsregeln</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>DUPLICATE_VALUE</td>
      <td>Fehler während CRM-Export: DUPLICATE_VALUE : Entitätstyp 'Lead': CRM ErrorCode: DUPLICATE_VALUE, CRM ErrorMessage: duplicate value found: Email_Unique__c dupliziert Wert auf Datensatz mit ID: 123, RecordId: 456</td>
      <td>Das in die Salesforce-Organisation importierte Feld erlaubt keine doppelten Werte.</td>
      <td>
        <ul>
          <li>Deaktivieren Sie die <a href="https://help.salesforce.com/s/articleView?id=000390009&amp;type=1">"Eindeutiges Kontrollkästchen"</a> in Salesforce.
          </li>
          <li>Ausschluss des dedizierten Marketo Measure-Benutzers von <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierte Validierungsregeln</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>ENTITY_IS_LOCKED</td>
      <td>Fehler beim CRM-Export: ENTITY_IS_LOCKED : Entitätstyp 'Konto': CRM ErrorCode: ENTITY_IS_LOCKED, CRM ErrorMessage: Dieser Datensatz ist gesperrt. Wenn Sie sie bearbeiten müssen, wenden Sie sich an Ihren Administrator. RecordId: 0123456</td>
      <td>Wenn sich ein Datensatz in einem Genehmigungsprozess befindet und ein Benutzer, der nicht der aktuelle Genehmiger oder Systemadministrator ist, versucht, den Datensatz zu bearbeiten.</td>
      <td>
        <ul>
          <li>Lösen Sie den ausstehenden Genehmigungsprozess für diesen Datensatz in der Salesforce-Organisation.</li>
          <li>Ausschluss des dedizierten Marketo Measure-Benutzers von <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierte Validierungsregeln</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>FIELD_FILTER_VALIDATION_EXCEPTION</td>
      <td>Fehler beim CRM-Export: FIELD_FILTER_VALIDATION_EXCEPTION : Entitätstyp 'Lead': CRM ErrorCode: FIELD_FILTER_VALIDATION_EXCEPTION, Field(s): User__C, CRM ErrorMessage: Wert ist nicht vorhanden oder entspricht nicht den Filterkriterien. Bitte wählen Sie einen Benutzer mit der Rolle "Account Executive, Inside Sales"; RecordId: 0123456</td>
      <td>Geänderter Datensatz erfüllt keine Nachschlagefilter mehr, die für das Objekt definiert sind.</td>
      <td>Suchen Sie nach Filtern für das Objekt, das Marketo Measure zu ändern versucht. Siehe <a href="https://help.salesforce.com/s/articleView?id=000384756&amp;type=1">dieser Salesforce-Artikel</a> , um zu erfahren, wie Sie nach Filtern für ein Objekt suchen.</td>
    </tr>
    <tr>
      <td>FIELD_INTEGRITY_EXCEPTION</td>
      <td>Fehler beim CRM-Export: FIELD_INTEGRITY_EXCEPTION : Entitätstyp 'Lead': CRM ErrorCode: FIELD_INTEGRITY_EXCEPTION, Field(s): Country, CRM ErrorMessage: Es gibt ein Problem mit diesem Land, auch wenn es korrekt angezeigt wird. Bitte wählen Sie ein Land/Gebiet aus der Liste der gültigen Länder aus.: Land, RecordId: 0123456</td>
      <td>Der erwartete Typ des Datensatzes stimmt nicht überein.</td>
      <td>Der häufigste Fall dabei ist, dass nicht die in der Salesforce-Organisation festgelegten Benennungsstandards für Bundesstaaten/Länder eingehalten werden, da die Felder Bundesland/Land so standardisiert wurden, dass nur bestimmte Werte der Auswahlliste akzeptiert werden. Um dieses Problem zu beheben, können Sie:
        <ul>
          <li>Aktualisieren Sie den Datensatz, um den für dieses Feld akzeptierten Werten der Organisation zu folgen. Wenden Sie sich an Ihren SFDC-Administrator, um die Liste der akzeptierten Werte zu erhalten.</li>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.admin_state_country_picklist_enable.htm&amp;type=5">Deaktivieren Sie die Auswahl-Listen "Bundesland"und "Land"</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INACTIVE_OWNER_OR_USER</td>
      <td>Fehler beim CRM-Export: INACTIVE_OWNER_OR_USER : Entitätstyp 'Contact': CRM ErrorCode: INACTIVE_OWNER_OR_USER, CRM ErrorMessage: Vorgang ausgeführt mit inaktivem Benutzer [1234] als Inhaber des Kontakts, RecordId: 0123456</td>
      <td>Marketo Measure fehlt die Berechtigung "Datensätze mit inaktiven Eigentümern aktualisieren".</td>
      <td>Gewähren Sie Marketo Measure die "<a href="https://help.salesforce.com/s/articleView?id=000386699&amp;type=1">Aktualisieren von Datensätzen mit inaktiven Inhabern</a>".</td>
    </tr>
    <tr>
      <td>INSUFFICIENT_ACCESS_OR_READONLY</td>
      <td>Fehler beim CRM-Export: INSUFFICIENT_ACCESS_OR_READONLY : Entitätstyp 'Konto': CRM ErrorCode: INSUFFICIENT_ACCESS_OR_READONLY, CRM ErrorMessage: Ungenügende Zugriffsrechte auf Objekt-ID: [123], RecordId: 456</td>
      <td>Marketo Measure fehlt Berechtigungen für ein Objekt/Feld oder das Objekt ist schreibgeschützt.</td>
      <td>Siehe Folgendes <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Experience League-Artikel</a> für Anleitungen zu den Berechtigungen, die Marketo Measure benötigt.</td>
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
      <td>MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS</td>
      <td>Fehler beim CRM-Export: MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS : Entitätstyp 'Campaign': CRM ErrorCode: INVALID_FIELD_FOR_INSERT_UPDATE, Field(s): bizible2__UniqueId__c, CRM ErrorMessage: Felder können nicht erstellt/aktualisiert werden: bizible2_ UniqueId__c. Überprüfen Sie die Sicherheitseinstellungen dieses Felds und stellen Sie sicher, dass es für Ihr Profil oder Ihren Berechtigungssatz gelesen/geschrieben wird.</td>
      <td>Marketo Measure fehlt Berechtigungen für bizible Felder.</td>
      <td>Wir benötigen Lese- und Schreibberechtigungen für alle Felder mit dem Präfix "bizible2__". Eine vollständige Liste dieser Felder finden Sie <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">in diesem Artikel</a>.</td>
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
      <td>MISSING_RECORD_OBJECT_PERMISSIONS</td>
      <td>Fehler beim CRM-Export: MISSING_RECORD_OBJECT_PERMISSIONS : Entitätstyp 'bizible2__Bizible_Touchpoint__c': CRM ErrorCode: INSUFFICIENT_ACCESS_ON_CROSS_REFERENCE_ENTITY, Field(s): Account, CRM ErrorMessage: Ungenügende Zugriffsrechte auf Cross-Reference ID: 01 23456</td>
      <td>Marketo Measure fehlt Berechtigungen.</td>
      <td>Es gibt mehrere Gründe für diesen Fehler, die speziell für die Salesforce-Organisation gelten. Im Folgenden finden Sie einige gängige Schritte zur Fehlerbehebung, die das Problem beheben können:
        <ul>
          <li>Überprüfen Sie alle Berechtigungen, die wir für jede <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Objekt und Feld</a>.</li>
          <li>Ausschluss des dedizierten Marketo Measure-Benutzers von <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierte Validierungsregeln</a>.</li>
          <li>Marketo Measure gewähren "<a href="https://developer.salesforce.com/docs/atlas.de-DE.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">Alle ändern</a>".</li>
        </ul>
      </td>
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
      <td>RECORD_NONCOMPLIANT_WITH_VALIDATION_RULES</td>
      <td>Fehler beim CRM-Export: RECORD_NONCOMPLIANT_WITH_VALIDATION_RULES : Entitätstyp 'Lead': CRM ErrorCode: FIELD_CUSTOM_VALIDATION_EXCEPTION, Field(s): Lead_Status_Reason__c, CRM ErrorMessage: Sie müssen den Lead-Status-Grund, RecordId: 0123 auswählen. 456</td>
      <td>Der zu aktualisierende Datensatz entspricht nicht einem Überprüfungsregelsatz in der Salesforce-Organisation.</td>
      <td>Ausschluss des dedizierten Marketo Measure-Benutzers von <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierte Validierungsregeln</a>.
      <p>
      Aktualisieren Sie Ihre <a href="https://help.salesforce.com/s/articleView?id=sf.fields_about_field_validation.htm&amp;type=5">Validierungsregeln</a>.</td>
    </tr>
    <tr>
      <td>RESTRICT_PICKLIST_VALUES_ENABLED</td>
      <td>Fehler beim CRM-Export: RESTRICT_PICKLIST_VALUES_ENABLED : Entitätstyp 'Campaign': CRM ErrorCode: INVALID_OR_NULL_FOR_RESTRICTED_PICKLIST, Field(s): Areas_of_Interest__c, CRM ErrorMessage: bad value for restricted picklist field: Unknown</td>
      <td>Wenn die Option "Auswahlliste auf die in der Wertesatz definierten Werte beschränken"in der Einrichtung des Picklist-Felds aktiviert ist oder der in das Feld eingefügte Wert im Datensatztyp des Objekts nicht verfügbar ist.</td>
      <td>Deaktivieren Sie die Einstellung "Auswahlliste einschränken"in der Salesforce-Organisation.
          <p>
          Ausschluss des dedizierten Marketo Measure-Benutzers von <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierte Validierungsregeln</a>.
      </td>
    </tr>
    <tr>
      <td>REQUIRED_FIELD_MISSING</td>
      <td>Fehler beim CRM-Export: MISSING_REQUIRED_FIELD : Entitätstyp 'Lead': CRM ErrorCode: REQUIRED_FIELD_MISSING, Field(s): Product_Type__c, CRM ErrorMessage: Erforderliche Felder fehlen: [Product_Type__c], RecordId: 0123456</td>
      <td>Wenn eine Validierungsregel Pflichtfelder für Objekte angibt.</td>
      <td>Ausschluss des dedizierten Marketo Measure-Benutzers von <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierte Validierungsregeln</a>.
      </td>
    </tr>
    <tr>
      <td>UNKNOWN_EXCEPTION</td>
      <td>Fehler während CRM-Export: UNKNOWN_EXCEPTION : Entitätstyp 'Contact': CRM ErrorCode: UNKNOWN_EXCEPTION, CRM ErrorMessage: Portal-Benutzer können keine Partnerkonten besitzen, RecordId: 0123456</td>
      <td>In Salesforce trat eine unbehandelte Ausnahme auf.</td>
      <td>Wenn das Problem weiterhin besteht, schreiben Sie eine Groß-/Kleinschreibung mit Salesforce ein und kopieren Sie die numerischen Werte in die Fehlermeldung.</td>
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
