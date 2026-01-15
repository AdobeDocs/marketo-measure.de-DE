---
description: Anleitung zu Fehlerbenachrichtigungen für Benutzende von Marketo Measure
title: Fehlerbenachrichtigungen
feature: Fundamentals
exl-id: ed07eed6-ddeb-4856-a1ac-ea3d571283f6
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '1717'
ht-degree: 29%

---

# Fehlerbenachrichtigungen {#error-notifications}

Nachfolgend finden Sie eine Liste mit Fehlern, die Sie möglicherweise über In-App-Benachrichtigungen oder E-Mails erhalten. Wenn Sie eine dieser Optionen erhalten, führen Sie die entsprechenden Schritte zur Fehlerbehebung aus. Falls das Problem durch diese Schritte nicht gelöst werden kann, wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support).

Um die vollständige Benachrichtigung in [!DNL Marketo Measure] anzuzeigen, klicken **unten auf der Registerkarte** auf „Alle anzeigen“.

![Um die vollständige Benachrichtigung in Marketo Measure anzuzeigen, klicken Sie auf Anzeigen](assets/adobe-setup-1.png)

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
      <td>Weitere Informationen finden Sie in der Salesforce-Dokumentation zum Thema <a href="https://help.salesforce.com/s/articleView?language=en_US&id=sf.branded_apps_commun_api_permset.htm&type=5">Aktivieren des API-Zugriffs</a>.</td>
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
          &lt;img alt=„error notifications 3“ src="assets/error-notifications-3.png"
          </p>
      </td>
    </tr>
    <tr>
      <td>CANNOT_EXECUTE_FLOW_TRIGGER</td>
      <td>Fehler beim CRM-Export: CANNOT_EXECUTE_FLOW_TRIGGER : Entitätstyp „Kontakt“ Geben Sie Ihrem Salesforce-Administrator diese Details.
Limit überschritten
Sie oder Ihr Unternehmen haben die Höchstgrenze für diese Funktion überschritten. Fehler-ID: 123456</td>
      <td>Der Datensatz kann nicht gespeichert werden, da er keiner in der Salesforce-Organisation eingerichteten Trigger-Flussregel entspricht.</td>
      <td>Überprüfen Sie die vollständigen Details der Benachrichtigung und die Fluss-Trigger in der Salesforce-Organisation.
Die Salesforce-Dokumentation zu Flow Trigger <a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">finden Sie hier</a>.
      </td>
    </tr>
    <tr>
      <td>CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY</td>
      <td>Fehler beim CRM-Export: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY : Entitätstyp 'Lead': CRM-Fehlercode: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY, CRM-Fehlermeldung: System.LimitException: Apex CPU-Zeitlimit überschritten, RecordId: 0123456
      <p>
      Fehler beim CRM-Export: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY : Entitätstyp 'Konto': CRM-Fehlercode: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY, CRM-Fehlermeldung: Entitätstyp kann nicht aktualisiert werden: Konto, Datensatz-ID: 0123456</td>
      <td>Trigger verhindern das Aktualisieren oder Einfügen eines Objekts.
      <p>
      ODER
      <p>
      Fehlende Berechtigungen für das Objekt.</td>
      <td>Überprüfen Sie den Trigger-Code, der zum Fehlschlagen des Einfüge-/Aktualisierungsprozesses führt. In der folgenden Salesforce-Dokumentation finden Sie weitere Informationen zu Trigger:
        <ul>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.code_manage_triggers.htm&type=5">Apex-Trigger </a>
          </li>
          <li><a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">Fluss-Trigger </a>
          </li>
        </ul>
        <p>
        Geben Sie dem <a href="/help/configuration-and-setup/how-marketo-measure-and-salesforce-interact.md">Marketo Measure-Benutzer alle erforderlichen Berechtigungen</a>.
      </td>
    </tr>
    <tr>
      <td>DUPLICATES_DETECTED</td>
      <td>Fehler beim CRM-Export: DUPLICATES_DETECTED : Entitätstyp „Kontakt“: CRM-Fehlercode: DUPLICATES_DETECTED, CRM-Fehlermeldung: Es wird ein doppelter Eintrag erstellt. Es wird empfohlen, stattdessen einen vorhandenen Datensatz zu verwenden., RecordId: 0123456</td>
      <td>Der in die Salesforce-Organisation importierte Datensatz existiert bereits.</td>
      <td><a href="https://help.salesforce.com/s/articleView?id=000390009&type=1">Deaktivieren Sie die Einstellung „Regel duplizieren</a>, um Duplikate zuzulassen.
          <p>
          Schließen Sie den dedizierten Marketo Measure-Benutzer aus <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierten Validierungsregeln</a> aus.</td>
    </tr>
    <tr>
      <td>DUPLICATE_VALUE</td>
      <td>Fehler beim CRM-Export: DUPLICATE_VALUE : Entitätstyp „Lead“: CRM-Fehlercode: DUPLICATE_VALUE, CRM-Fehlermeldung: Doppelter Wert gefunden: E-Mail_Unique__c dupliziert Wert im Datensatz mit ID: 123, RecordId: 456</td>
      <td>Das in die Salesforce-Organisation importierte Feld lässt keine doppelten Werte zu.</td>
      <td>Deaktivieren Sie das <a href="https://help.salesforce.com/s/articleView?id=000390009&type=1"> „Eindeutiges Kontrollkästchen</a> in Salesforce.
          <p>
          Schließen Sie den dedizierten Marketo Measure-Benutzer aus <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierten Validierungsregeln</a> aus.</td>
    </tr>
    <tr>
      <td>ENTITY_IS_LOCKED</td>
      <td>Fehler beim CRM-Export: ENTITY_IS_LOCKED : Entitätstyp 'Konto': CRM-Fehlercode: ENTITY_IS_LOCKED, CRM-Fehlermeldung: Dieser Datensatz ist gesperrt. Wenn Sie sie bearbeiten müssen, wenden Sie sich an Ihren Administrator, RecordId: 0123456</td>
      <td>Wenn sich ein Datensatz in einem Genehmigungsprozess befindet und ein Benutzer, der nicht der aktuelle Genehmiger oder Systemadministrator ist, versucht, den Datensatz zu bearbeiten.</td>
      <td>
        <ul>
          <li>Lösen Sie den ausstehenden Genehmigungsprozess für diesen Datensatz in der Salesforce-Organisation auf.</li>
          <li>Schließen Sie den dedizierten Marketo Measure-Benutzer aus <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierten Validierungsregeln</a> aus.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>FIELD_FILTER_VALIDATION_EXCEPTION</td>
      <td>Fehler beim CRM-Export: FIELD_FILTER_VALIDATION_EXCEPTION : Entitätstyp 'Lead': CRM-Fehlercode: FIELD_FILTER_VALIDATION_EXCEPTION, Feld(er): Benutzer__C, CRM-Fehlermeldung: Wert existiert nicht oder entspricht nicht den Filterkriterien. Wählen Sie einen Benutzer mit der Rolle „Account Executive, Inside Sales“; RecordId: 0123456</td>
      <td>Der geänderte Datensatz erfüllt nicht mehr die für das Objekt definierten Suchfilter.</td>
      <td>Suchen Sie nach Filtern für das Objekt, das Marketo Measure ändern möchte. Siehe <a href="https://help.salesforce.com/s/articleView?id=000384756&type=1">diesen Artikel zu Salesforce</a>, um zu erfahren, wie Sie nach Filtern für ein Objekt suchen können.</td>
    </tr>
    <tr>
      <td>FIELD_INTEGRITY_EXCEPTION</td>
      <td>Fehler beim CRM-Export: FIELD_INTEGRITY_EXCEPTION : Entitätstyp 'Lead': CRM-Fehlercode: FIELD_INTEGRITY_EXCEPTION, Feld(er): Land, CRM-Fehlermeldung: Es gibt ein Problem mit diesem Land, auch wenn es korrekt erscheinen mag. Wählen Sie ein Land/eine Region aus der Liste der gültigen Länder aus.: Land, RecordId: 0123456</td>
      <td>Der erwartete Typ des Datensatzes stimmt nicht überein.</td>
      <td>Der häufigste Fall hierfür ist, dass die in der Salesforce-Organisation festgelegten Benennungsstandards für Bundesländer/Länder nicht eingehalten werden, da die Felder für Bundesland/Land so standardisiert wurden, dass nur bestimmte Werte der Auswahlliste akzeptiert werden. Um dieses Problem zu beheben, haben Sie folgende Möglichkeiten:
        <ul>
          <li>Aktualisieren Sie den Datensatz so, dass er den von der Organisation für dieses Feld akzeptierten Werten entspricht. Wenden Sie sich an Ihren SFDC-Administrator, um die Liste der akzeptierten Werte zu erhalten.</li>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.admin_state_country_picklist_enable.htm&type=5">Deaktivieren Sie die Auswahllisten Bundesland/</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INACTIVE_OWNER_OR_USER</td>
      <td>Fehler beim CRM-Export: INACTIVE_OWNER_OR_USER : Entitätstyp 'Kontakt': CRM-Fehlercode: INACTIVE_OWNER_OR_USER, CRM-Fehlermeldung: Vorgang mit inaktivem Benutzer [1234] als Kontaktbesitzer ausgeführt, RecordId: 0123456</td>
      <td>In Marketo Measure fehlt die Berechtigung zum Aktualisieren von Datensätzen mit inaktiven Inhabern.</td>
      <td>Erteilen Sie Marketo Measure die Berechtigung <a href="https://help.salesforce.com/s/articleView?id=000386699&type=1">Aktualisieren von Datensätzen mit inaktiven </a>".</td>
    </tr>
    <tr>
      <td>INSUFFICIENT_ACCESS_OR_READONLY</td>
      <td>Fehler beim CRM-Export: INSUFFICIENT_ACCESS_OR_READONLY : Entitätstyp 'Konto': CRM-Fehlercode: INSUFFICIENT_ACCESS_OR_READONLY, CRM-Fehlermeldung: Unzureichende Zugriffsrechte für Objekt-ID: [123], RecordId: 456</td>
      <td>Marketo Measure fehlen Berechtigungen für ein Objekt/Feld oder das Objekt ist schreibgeschützt.</td>
      <td>Anleitungen zu den Berechtigungen, die Marketo Measure erfordert, finden <a href="/help/configuration-and-setup/how-marketo-measure-and-salesforce-interact.md"> im folgenden Artikel zu </a>Experience League .</td>
    </tr>
    <tr>
      <td>INVALID_ADOBE_ANALYTICS_CONFIGURATION</td>
      <td>Fehler beim Adobe Analytics-Export: INVALID_ADOBE_ANALYTICS_CONFIGURATION : Fehler: Hochladen nicht zulässig. Bestätigen Sie das Datenquellenschema vor dem Hochladen. Datenquellen-ID:1234</td>
      <td>Die Adobe Analytics-Integration ist nicht korrekt konfiguriert.</td>
      <td>Lesen Sie die folgenden Hilfeartikel, um eine korrekte Konfiguration sicherzustellen:
        <ul>
          <li>
            <a href="/help/adobe-analytics.md">Marketo Measure-Integrationen mit Adobe Analytics</a>
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
      <td>Im in der Benachrichtigung angegebenen Quellsystem (Ad, CRM, Marketo) wird sichergestellt, dass die mit dem Datensatz verknüpfte Währung eine unterstützte und gültige Währung hat. Unterstützte Währungen werden von ISO-Währungsstandards abgeleitet.</td>
    </tr>
    <tr>
      <td>MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS</td>
      <td>Fehler beim CRM-Export: MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS : Entitätstyp 'Kampagne': CRM-Fehlercode: INVALID_FIELD_FOR_INSERT_UPDATE, Feld(er): bizible2__UniqueId__c, CRM-Fehlermeldung: Felder können nicht erstellt/aktualisiert werden: bizible2__UniqueId__c. Überprüfen Sie die Sicherheitseinstellungen dieses Felds und stellen Sie sicher, dass es für Ihr Profil oder Ihren Berechtigungssatz Lese-/Schreibzugriff hat.</td>
      <td>Marketo Measure fehlen Berechtigungen für Bizible-Felder.</td>
      <td>Wir benötigen Lese- und Schreibberechtigungen für alle Felder mit dem Präfix „bizible2__“. Eine vollständige Liste dieser Felder finden Sie <a href="/help/configuration-and-setup/how-marketo-measure-and-salesforce-interact.md">in diesem Artikel</a>.</td>
    </tr>
    <tr>
      <td>MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Fehler beim CRM-Export: MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Marketo Measure hat keine Berechtigung zum Anzeigen/Bearbeiten konvertierter Leads</td>
      <td>Hilfe zur Aktivierung dieser Berechtigung in Ihrem CRM-System finden Sie im folgenden Experience League-Dokument<br/>
<a href="/help/marketo-measure-salesforce-reporting/enabling-the-permission-to-edit-converted-leads.md">Aktivieren der Berechtigung zum Bearbeiten konvertierter Leads</a></td>
    </tr>
    <tr>
      <td>MISSING_FIELD_READ_PERMISSION</td>
      <td>Fehler beim CRM-Import: MISSING_FIELD_READ_PERMISSION : Entitätstyp 'Ereignis': INVALID_FIELD:<br/>
    SystemModstamp,IsDeleted,WhoId,bizible2__Bizible_Touchpoint_Date__c</td>
      <td>Marketo Measure hat für ein erforderliches Feld keine Leseberechtigungen.</td>
      <td>In den folgenden Hilfeartikeln finden Sie Anleitungen zu den erforderlichen Berechtigungen für Marketo Measure:
        <ul>
          <li><a href="/help/marketo-measure-dynamics-schema.md">Dynamics</a>
          </li>
          <li><a href="/help/configuration-and-setup/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
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
            <li><a href="/help/marketo-measure-dynamics-schema.md">Dynamics</a>
            </li>
            <li><a href="/help/configuration-and-setup/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
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
      <td>Fehler beim CRM-Export: MISSING_RECORD_OBJECT_PERMISSIONS : Entitätstyp 'bizible2__Bizible_Touchpoint__c': CRM-Fehlercode: INSUFFICIENT_ACCESS_ON_CROSS_REFERENCE_ENTITY, Feld(er): Konto, CRM-Fehlermeldung: Unzureichende Zugriffsrechte für Querverweis-ID: 0123456</td>
      <td>Marketo Measure fehlen Berechtigungen.</td>
      <td>Es gibt mehrere Gründe für diesen Fehler, die spezifisch für die Salesforce-Organisation sind. Im Folgenden finden Sie einige gängige Schritte zur Fehlerbehebung, mit denen das Problem behoben werden kann:
        <ul>
          <li>Überprüfen Sie alle erforderlichen Berechtigungen für jedes <a href="/help/configuration-and-setup/how-marketo-measure-and-salesforce-interact.md">Objekt und Feld</a>.</li>
          <li>Schließen Sie den dedizierten Marketo Measure-Benutzer aus <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierten Validierungsregeln</a> aus.</li>
          <li>Erteilen Sie Marketo Measure <a href="https://developer.salesforce.com/docs/atlas.de-DE.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">Alle ändern</a>-Berechtigungen.</li>
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
      <td>Im in der Benachrichtigung angegebenen Quellsystem (Ad, CRM, Marketo) wird sichergestellt, dass die mit dem Datensatz verknüpfte Währung eine unterstützte und gültige Währung hat. Unterstützte Währungen werden von ISO-Währungsstandards abgeleitet.</td>
    </tr>
    <tr>
      <td>OPERATION_TOO_LARGE</td>
      <td>Fehler beim CRM-Import: OPERATION_TOO_LARGE : Für eine erfolgreiche Abfrage von Aktivitäten ist die Berechtigung 'Alle Daten anzeigen' erforderlich.</td>
      <td>Mit den CRM-Einstellungen kann Marketo Measure keine ausreichend große Datenmenge abfragen</td>
      <td>Erteilen Sie Marketo Measure die Berechtigung 'Alle Daten anzeigen' für das angegebene Objekt.
      <p>
      Weitere Informationen zur Berechtigung 'Alle Daten anzeigen' <a href="https://developer.salesforce.com/docs/atlas.de-DE.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">sind hier zu finden</a>.</td>
    </tr>
    <tr>
      <td>RECORD_NONCOMPLIANT_WITH_VALIDATION_RULES</td>
      <td>Fehler beim CRM-Export: RECORD_NONCOMPLIANT_WITH_VALIDATION_RULES : Entitätstyp 'Lead': CRM-Fehlercode: FIELD_CUSTOM_VALIDATION_EXCEPTION, Feld(er): Lead_Status_Reason__c, CRM-Fehlermeldung: Sie müssen den Grund für den Lead-Status auswählen, RecordId: 0123456</td>
      <td>Der zu aktualisierende Datensatz erfüllt einen in der Salesforce-Organisation festgelegten Validierungsregelsatz nicht.</td>
      <td>Schließen Sie den dedizierten Marketo Measure-Benutzer aus <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierten Validierungsregeln</a> aus.
      <p>
      Aktualisieren Sie <a href="https://help.salesforce.com/s/articleView?id=sf.fields_about_field_validation.htm&type=5">Validierungsregeln</a>.</td>
    </tr>
    <tr>
      <td>RESTRICT_PICKLIST_VALUES_ENABLED</td>
      <td>Fehler beim CRM-Export: RESTRICT_PICKLIST_VALUES_ENABLED : Entitätstyp 'Kampagne': CRM-Fehlercode: INVALID_OR_NULL_FOR_RESTRICTED_PICKLIST, Feld(er): Areas_of_Interest__c, CRM-Fehlermeldung: ungültiger Wert für eingeschränktes Auswahllistenfeld: Unbekannt</td>
      <td>Wenn im Setup des Auswahllistenfelds die Option „Auswahlliste auf die im Wertesatz definierten Werte beschränken“ aktiviert ist oder der in das Feld eingefügte Wert im Datensatztyp des Objekts nicht verfügbar ist.</td>
      <td>Deaktivieren Sie die Einstellung Auswahlliste einschränken in der Salesforce-Organisation.
          <p>
          Schließen Sie den dedizierten Marketo Measure-Benutzer aus <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierten Validierungsregeln</a> aus.
      </td>
    </tr>
    <tr>
      <td>REQUIRED_FIELD_MISSING</td>
      <td>Fehler beim CRM-Export: MISSING_REQUIRED_FIELD : Entitätstyp 'Lead': CRM-Fehlercode: REQUIRED_FIELD_MISSING, Feld(er): Product_Type__c, CRM-Fehlermeldung: Erforderliche Felder fehlen: [Product_Type__c], RecordId: 0123456</td>
      <td>Wenn eine Validierungsregel Pflichtfelder für Objekte angibt.</td>
      <td>Schließen Sie den dedizierten Marketo Measure-Benutzer aus <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">benutzerdefinierten Validierungsregeln</a> aus.
      </td>
    </tr>
    <tr>
      <td>UNKNOWN_EXCEPTION</td>
      <td>Fehler beim CRM-Export: UNKNOWN_EXCEPTION : Entitätstyp „Kontakt“: CRM-Fehlercode: UNKNOWN_EXCEPTION, CRM-Fehlermeldung: Portalbenutzer können keine Partnerkonten besitzen, RecordId: 0123456</td>
      <td>In Salesforce ist ein Ausnahmefehler aufgetreten.</td>
      <td>Wenn das Problem weiterhin besteht, senden Sie eine Anfrage an Salesforce und kopieren Sie die numerischen Werte in der Fehlermeldung.</td>
    </tr>
    <tr>
      <td>UNSUPPORTED_CRM_PACKAGE_VERSION</td>
      <td>Fehler beim CRM-Import: UNSUPPORTED_CRM_PACKAGE_VERSION : Aktualisieren Sie Ihr CRM-Paket</td>
      <td>Das aktuell erkannte Paket wird nicht mehr unterstützt.</td>
      <td>Aktualisieren Sie Ihr Paket auf die neueste Version:
        <ul>
          <li><a href="/help/configuration-and-setup/best-practices-for-marketo-measure-crm-package.md">Best Practices</a>
          </li>
          <li><a href="/help/microsoft-dynamics-crm-installation-guide.md">Dynamics</a>
          </li>
          <li><a href="/help/configuration-and-setup/install-set-up.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
