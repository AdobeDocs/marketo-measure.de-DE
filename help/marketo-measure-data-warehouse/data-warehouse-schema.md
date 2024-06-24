---
unique-page-id: 35586140
description: Data Warehouse-Schema - Marketo Measure - Produktdokumentation
title: Data Warehouse-Schema
exl-id: f1895eb1-a32d-4c43-93fb-0aa838527946
feature: Data Warehouse
source-git-commit: 9f374537dd3690b5c904e2ac1933ff460dc66282
workflow-type: ht
source-wordcount: '21110'
ht-degree: 100%

---

# Data Warehouse-Schema {#data-warehouse-schema}

Mit Data Warehouse können Sie beliebig viel verfolgen, Berichte zu Ihren Attributionsdaten erstellen, wo immer Sie möchten, und sie in andere Datensätze einbinden.

>[!IMPORTANT]
>
>* Zeilen mit dem Wert _DELETED_DATE werden 7 Tage lang beibehalten und dann aus Snowflake entfernt.
>* Die Zeitzonen, die in Snowflake verwendet werden, entsprechen der koordinierten Weltzeit (UTC).

>[!NOTE]
>
>[Klicken Sie hier](#sample-queries), um Beispielabfragen am Ende dieses Artikels zu sehen.

## Diagramme zur Entitätsbeziehung {#entity-relationship-diagrams}

Die _Data Warehouse-Datenmodell_-ERD zeigt an, wie Daten im Data Warehouse fließen und miteinander verknüpft werden sollen. Dieses Diagramm enthält nicht alle im Data Warehouse verfügbaren Tabellen, da einige davon Zuordnungstabellen, Ansichten anderer bereits vorhandener Tabellen oder veraltete Tabellen darstellen, deren Verwendung wir nicht mehr empfehlen. Die Tabellen und Spalten im Data Warehouse werden im Folgenden detailliert beschrieben. Viele dieser Tabellen enthalten denormalisierte Felder. Dieses Diagramm ist jedoch das empfohlene Datenmodell, das stattdessen Daten aus Dimensionstabellen nutzt.

Die zusätzliche _Ads Dimensional Data Model_-ERD zeigt, wie Tabellen für Anzeigen-spezifische Dimensionen am besten mit den Tabellen im Hauptdatenmodell verknüpft werden können. Obwohl Anzeigendimensionen auch in anderen Tabellen denormalisiert sind, stellt dies das empfohlene Modell für die Zusammenführung dieser Dimensionen dar.

_Klicken Sie auf ein Bild für die Vollbildversion_

<table style="table-layout:auto"> 
 <tbody> 
  <tr> 
   <th>Data Warehouse-Datenmodell</th> 
   <th>Ads Dimensional-Datenmodell</th> 
  </tr> 
  <tr> 
   <td><a href="assets/data-warehouse-data-model.pdf"><img src="assets/data-warehouse-data-model-thumb.png"></a></td>
   <td><a href="assets/ads-dimensional-data-model.pdf"><img src="assets/ads-dimensional-data-model-thumb.png"></a></td> 
  </tr> 
 </tbody> 
</table>

## Ansichten {#views}

### BIZ_ACCOUNTS {#biz-accounts}

Aus dem Quellsystem importierte Konten.

<table>
  <tbody>
    <tr>
      <th><strong>Spalte</strong></th>
      <th><strong>Datentyp</strong></th>
      <th><strong>Beschreibung</strong></th>
      <th><strong>Beispieldaten</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Die Konto-ID aus dem Quellsystem.</td>
      <td>0013100001kpAZxAAM</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Das Erstellungsdatum des Kontos aus dem Quellsystem.</td>
      <td>2016-08-28 00:32:55.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Das Datum der letzten Änderung des Kontos aus dem Quellsystem.</td>
      <td>2018-08-01 17:38:30.000</td>
    </tr>
    <tr>
      <td>NAME</td>
      <td>varchar</td>
      <td>Der Kontoname, aus dem Quellsystem.</td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>WEB_SITE</td>
      <td>varchar</td>
      <td>Website für das Konto, wie im Quellsystem aufgezeichnet, die für die Zuordnung von Lead zu Konto verwendet wird.</td>
      <td>www.adobe.com</td>
    </tr>
    <tr>
      <td>ENGAGEMENT_RATING</td>
      <td>varchar</td>
      <td>Eine Buchstabenbewertung (A, B, C, D, N/A), die aus dem [!DNL Marketo Measure]-Modell für maschinelles Lernen generiert wird. Dies ist null, wenn ABM deaktiviert ist.</td>
      <td>B</td>
    </tr>
    <tr>
      <td>ENGAGEMENT_SCORE</td>
      <td>number(38,19)</td>
      <td>Ein numerisches Ergebnis, berechnet durch das [!DNL Marketo Measure]-Machine Learning zum Generieren der prädiktiven Interaktionsbewertung (Engagement_Rating). Dies ist null, wenn ABM deaktiviert ist.</td>
      <td>0.1417350147058800000</td>
    </tr>
    <tr>
      <td>DOMAIN</td>
      <td>varchar</td>
      <td>Die heruntergeparste Version der Website, die nur die Domäne speichert.</td>
      <td>adobe</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Gibt an, ob der Datensatz im Quellsystem gelöscht wird.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Benutzerdefinierte Eigenschaften im JSON-Format, die [!DNL Marketo Measure] aus dem Quellsystem importiert hat.</td>
      <td>{"Account_Type__c": "Security", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td><b>∗</b> BRANCHE</td>
      <td>varchar</td>
      <td>Hauptgeschäft des Kontos.</td>
      <td>Einzelhandel, Telekommunikation</td>
    </tr>
    <tr>
      <td><b>∗</b> LAND</td>
      <td>varchar</td>
      <td>Länderbereich der Kontoadresse.</td>
      <td>USA, Kanada</td>
    </tr>
  </tbody>
</table>
<p>
<b>*</b> <i>Nur verfügbar in Marketo Measure Ultimate</i>
<p>

### BIZ_ACCOUNT_TO_EMAILS {#biz-account-to-emails}

Zuordnungstabelle zwischen bekannten Lead-/Kontakt-E-Mail-Adressen und Konten. Diese Tabelle ist leer, wenn ABM deaktiviert ist.

<table>
  <tbody>
    <tr>
    <th><strong>Spalte</strong></th>
      <th><strong>Datentyp</strong></th>
      <th><strong>Beschreibung</strong></th>
      <th><strong>Beispieldaten</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Eine eindeutige ID für den Datensatz.</td>
      <td>0013800001MMPPiAAP_person@adobe.com|2022-01-05 17:22:13 000</td>
    </tr>
    <tr>
      <td>ACCOUNT_ID</td>
      <td>varchar</td>
      <td>Kontokennung des Quellsystems.</td>
      <td>0013100001phrBAAAY</td>
    </tr>
    <tr>
      <td>EMAIL</td>
      <td>varchar</td>
      <td>E-Mail-Adresse, die dem Konto zugeordnet wurde, entweder durch Kontaktbeziehungen oder durch die Zuordnung "Lead to Account".</td>
      <td>person@adobe.com</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Das Datum der letzten Änderung des Kontos aus dem Quellsystem.</td>
      <td>2018-08-31 23:53:39.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Das Erstellungsdatum des Kontos aus dem Quellsystem.</td>
      <td>2018-08-18 22:01:32.000</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Gibt an, ob der Datensatz als gelöscht betrachtet wird.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ACTIVITIES {#biz-activities}

Aus einem Quellsystem oder verbundenen Anzeigenkonto importierte Aktivitäten.

<table>
  <tbody>
  <tr>
    <th><strong>Spalte</strong></th>
    <th><strong>Datentyp</strong></th>
    <th><strong>Beschreibung</strong></th>
    <th><strong>Beispieldaten</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Die Aktivitäts-ID aus dem Quellsystem.</td>
      <td>1678625515</td>
    </tr>
    <tr>
      <td>LEAD_ID</td>
      <td>varchar</td>
      <td>ID für den mit der Aktivität verknüpften Lead.</td>
      <td>15530482</td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>ID für den mit der Aktivität verknüpften Kontakt.
      </td>
      <td>13792552</td>
    </tr>
    <tr>
      <td>ACTIVITY_TYPE_ID</td>
      <td>varchar</td>
      <td>ID für den Aktivitätstyp aus dem Quellsystem.</td>
      <td>104</td>
    </tr>
    <tr>
      <td>ACTIVITY_TYPE_NAME</td>
      <td>varchar</td>
      <td>Der Aktivitätsname, aus dem Quellsystem.</td>
      <td>
        <p>Ändern des Status in der Progression</p>
      </td>
    </tr>
    <tr>
      <td>START_DATE</td>
      <td>timestamp_ntz</td>
      <td>Startdatum der Aktivität vom Quellsystem aus.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>END_DATE</td>
      <td>timestapm_ntz</td>
      <td>Enddatum der Aktivität vom Quellsystem aus.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>CAMPAIGN_ID</td>
      <td>varchar</td>
      <td>Kennung für die Kampagne, zu der die Aktivität gehört, aus dem Quellsystem.</td>
      <td>
        <p>li.508038570.147643566</p>
      </td>
    </tr>
    <tr>
      <td>SOURCE_SYSTEM</td>
      <td>varchar</td>
      <td>Gibt den Quellsystemtyp an.</td>
      <td>Marketo</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem die Zeile im Quellsystem erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung der Zeile im Quellsystem.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Gibt an, ob der Datensatz im Quellsystem als gelöscht betrachtet wird.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>AD_FORM_ID</td>
      <td>varchar</td>
      <td>ID für das Anzeigenformular, zu dem die Aktivität gehört, vom Quellsystem aus.</td>
      <td>li.507063119.3757704</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ADS {#biz-ads}

Aus einem verbundenen Anzeigenkonto importierte Anzeigen

<table>
  <tbody>
    <tr>
      <th><strong>Spalte</strong></th>
      <th><strong>Datentyp</strong></th>
      <th><strong>Beschreibung</strong></th>
      <th><strong>Beispieldaten</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Eine eindeutige ID für die Anzeige.</td>
      <td>fb.106851586409075.6052044288804.6052044290004.60534570 66804</td>
    </tr>
    <tr>
      <td>DISPLAY_ID</td>
      <td>varchar</td>
      <td>Die Anzeigen-ID aus dem Quellsystem.</td>
      <td>6053457066804</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_UNIQUE_ID</td>
      <td>varchar</td>
      <td>ID für das Anzeigenkonto, von dem aus die Anzeige importiert wurde.</td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_NAME</td>
      <td>varchar</td>
      <td>Name des Anzeigenkontos, von dem aus die Anzeige importiert wurde.</td>
      <td>[!DNL Marketo Measure] Konto</td>
    </tr>
    <tr>
      <td>ADVERTISER_UNIQUE_ID</td>
      <td>varchar</td>
      <td>ID des Advertisers für die Anzeige, insbesondere für Doubleclick.</td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>ADVERTISER_NAME</td>
      <td>varchar</td>
      <td>Name des Advertisers für die Anzeige, insbesondere für Doubleclick.</td>
      <td>Marketing Analytics</td>
    </tr>
    <tr>
      <td>AD_GROUP_UNIQUE_ID</td>
      <td>varchar</td>
      <td>ID der Anzeigengruppe für die Anzeige.</td>
      <td>fb.106851586409075.6052044288804.6052044290004</td>
    </tr>
    <tr>
      <td>AD_GROUP_NAME</td>
      <td>varchar</td>
      <td>Name der Anzeigengruppe für die Anzeige.</td>
      <td>Anzeigenset für Anzeige B</td>
    </tr>
    <tr>
      <td>AD_CAMPAIGN_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Kennung der Kampagne für die Anzeige.</td>
      <td>fb.106851586409075.6052044288804</td>
    </tr>
    <tr>
      <td>AD_CAMPAIGN_NAME</td>
      <td>varchar</td>
      <td>Name der Kampagne für die Anzeige.</td>
      <td>Kampagne zur Lead-Generierung</td>
    </tr>
    <tr>
      <td>IS_ACTIVE</td>
      <td>boolean</td>
      <td>Gibt an, ob die Anzeige im Quellsystem noch aktiv ist.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Gibt an, ob die Anzeige im Quellsystem gelöscht wurde.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes.</td>
      <td>2018-08-02 06:35:59.000</td>
    </tr>
    <tr>
      <td>FIRST_IMPORTED</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz zum ersten Mal aus dem Quellsystem importiert wurde.</td>
      <td>2018-08-02 06:35:59.000</td>
    </tr>
    <tr>
      <td>NAME</td>
      <td>varchar</td>
      <td>Name der Anzeige, aus dem Quellsystem.</td>
      <td>Anzeige 2</td>
    </tr>
    <tr>
      <td>NEEDS_UPDATE</td>
      <td>boolean</td>
      <td>Gibt an, ob die Anzeige für [!DNL Marketo Measure]-Tagging aktualisiert werden muss.
      <p>(Diagnostisches Feld, von interner Verarbeitung verwendet.)
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>GROUPING_KEY</td>
      <td>varchar</td>
      <td>Diagnostisches Feld für die interne Verarbeitung.</td>
      <td>fb.106851586409075.6052044288804.6052044290004</td>
    </tr>
    <tr>
      <td>ENTITY_TYPE</td>
      <td>varchar</td>
      <td>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "Anzeige".</td>
      <td>Werbung</td>
    </tr>
    <tr>
      <td>PROVIDER_TYPE</td>
      <td>varchar</td>
      <td>Name des Anzeigenanbieters für die Anzeige.</td>
      <td>Facebook</td>
    </tr>
    <tr>
      <td>URL_CURRENT</td>
      <td>varchar</td>
      <td>Die URL für die Landingpage.
        <p>(Diagnostisches Feld für die interne Verarbeitung.)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_OLD</td>
      <td>varchar</td>
      <td>Vorheriger Wert für URL_CURRENT.
      <p>(Diagnostisches Feld für die interne Verarbeitung.)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_REQUESTED</td>
      <td>varchar</td>
      <td>Die URL wird mit [!DNL Marketo Measure] Parameter.
      <p>(Diagnostisches Feld für die interne Verarbeitung.)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_ALTENATIVES</td>
      <td>varchar</td>
      <td>Aus dem Quellsystem importiert.
      <p>(Diagnostisches Feld für die interne Verarbeitung.)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>number(38,0)</td>
      <td>Fremdschlüssel zur Biz_Facts-Ansicht.</td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ADVERTISERS {#biz-advertisers}

Advertiser, die aus einem verbundenen Anzeigenkonto importiert wurden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Eine eindeutige ID für den Advertiser.</td>
      <td>dc.6114.9143143</td>
    </tr>
    <tr>
      <td>DISPLAY_ID</td>
      <td>varchar</td>
      <td>Die ID des Advertisers aus dem Quellsystem.</td>
      <td>9143143</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_UNIQUE_ID</td>
      <td>varchar</td>
      <td>ID für das Anzeigenkonto, von dem aus die Anzeige importiert wurde.</td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_NAME</td>
      <td>varchar</td>
      <td>Name des Anzeigenkontos, von dem aus die Anzeige importiert wurde.</td>
      <td>[!DNL Marketo Measure] Konto</td>
    </tr>
    <tr>
      <td>ADVERTISER_UNIQUE_ID</td>
      <td>varchar</td>
      <td>ID des Advertisers, insbesondere für Doubleclick.</td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>ADVERTISER_NAME</td>
      <td>varchar</td>
      <td>Name des Werbetreibenden, insbesondere für Doubleclick.</td>
      <td>[!DNL Marketo Measure] Marketing Analytics</td>
    </tr>
    <tr>
      <td>AD_GROUP_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie über dem Advertiser eine Anzeigengruppe gibt.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>AD_GROUP_NAME</td>
      <td>varchar</td>
      <td>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie über dem Advertiser eine Anzeigengruppe gibt.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>AD_CAMPAIGN_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie über dem Werbetreibenden eine Anzeigenkampagne gibt.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>AD_CAMPAIGN_NAME</td>
      <td>varchar</td>
      <td>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie über dem Advertiser eine Kampagne gibt.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>IS_ACTIVE</td>
      <td>boolean</td>
      <td>Gibt an, ob der Advertiser im Quellsystem noch aktiv ist.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Gibt an, ob der Advertiser im Quellsystem gelöscht wurde.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes.</td>
      <td>2018-08-02 06:35:59.000</td>
    </tr>
    <tr>
      <td>FIRST_IMPORTED</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz zum ersten Mal aus dem Quellsystem importiert wurde.</td>
      <td>2018-08-02 06:35:59.000</td>
    </tr>
    <tr>
      <td>NAME</td>
      <td>varchar</td>
      <td>Name des Advertisers aus dem Quellsystem.</td>
      <td>[!DNL Marketo Measure] Marketing Analytics</td>
    </tr>
    <tr>
      <td>NEEDS_UPDATE</td>
      <td>boolean</td>
      <td>Gibt an, ob der Advertiser für das [!DNL Marketo Measure]-Tagging aktualisiert werden muss.
      <p>(Diagnostisches Feld, von interner Verarbeitung verwendet.)
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>GROUPING_KEY</td>
      <td>varchar</td>
      <td>Diagnostisches Feld für die interne Verarbeitung.</td>
      <td></td>
    </tr>
    <tr>
      <td>ENTITY_TYPE</td>
      <td>varchar</td>
      <td>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "Advertiser".</td>
      <td>Advertiser</td>
    </tr>
    <tr>
      <td>PROVIDER_TYPE</td>
      <td>varchar</td>
      <td>Der Anzeigenanbieter für den Advertiser.</td>
      <td>Doubleclick</td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>number(38,0)</td>
      <td>Fremdschlüssel zur Biz_Facts-Ansicht.</td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_ACCOUNTS {#biz-ad-accounts}

Aus einem verbundenen Anzeigenkonto importierte Anzeigenkonten.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige Kennung für das Anzeigenkonto.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>Die Anzeigenkonto-ID aus dem Quellsystem.</td>
      <td>
        <p>6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>Wird als null erwartet, da dies der Datensatz für die Anzeigenkonten in der Anzeigen-Hierarchie ist.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>Wird als null erwartet, da dies der Datensatz für die Anzeigenkonten in der Anzeigen-Hierarchie ist.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Anzeigenkonten einen Advertiser gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Anzeigenkonten einen Advertiser gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Anzeigenkonten eine Anzeigengruppe gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Anzeigenkonten eine Anzeigengruppe gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Anzeigenkonten eine Anzeigenkampagne gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Anzeigenkonten eine Anzeigenkampagne gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob das Anzeigenkonto im Quellsystem noch aktiv ist.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob das Anzeigenkonto im Quellsystem gelöscht wurde.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-09-06 12:54:37.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Datensatz zum ersten Mal aus dem Quellsystem importiert wurde.</p>
      </td>
      <td>
        <p>2018-08-02 06:35:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>Name des Anzeigenkontos aus dem Quellsystem.</td>
      <td>
        <p>[!DNL Marketo Measure] Werbekonto</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Advertiser für das [!DNL Marketo Measure]-Tagging aktualisiert werden muss.</p>
        <p>(Diagnostisches Feld, von interner Verarbeitung verwendet.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisches Feld für die interne Verarbeitung.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "Konto".</p>
      </td>
      <td>
        <p>Konto</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name des Anzeigenanbieters für das Anzeigenkonto.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_CURRENCY_UNIT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Währungscode, der für das Anzeigenkonto aus dem Quellsystem verwendet wird.</p>
      </td>
      <td>
        <p>USD</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COMPANY_ID</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Verarbeitung verwendet.</td>
      <td>1933789</td>
    </tr>
    <tr>
      <td>
        <p>SOURCE</p>
      </td>
      <td>varchar</td>
      <td>Wird über die URL von utm_source analysiert.</td>
      <td>
        <p>Social</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>Wird über die URL von utm_medium analysiert.</td>
      <td>
        <p>lisu07261601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_COST</p>
      </td>
      <td>
        <p>number(38,19)</p>
      </td>
      <td>
        <p>Die Ausgabenmenge, die in den letzten 30 Tagen importiert wurde, gilt nur für AdWords.</p>
      </td>
      <td>
        <p>17260,000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_IMPRESSIONS</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Die Anzahl der Impressionen aus den letzten 30 Tagen, die nur für AdWords gelten.</p>
      </td>
      <td>
        <p>730060</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_CLICKS</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Die Anzahl der Klicks aus den letzten 30 Tagen, nur auf AdWords anwendbar.</p>
      </td>
      <td>
        <p>3400</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_CONVERSIONS</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Die Anzahl der Konversionen, die aus den letzten 30 Tagen gemeldet wurden, gilt nur für AdWords.</p>
      </td>
      <td>
        <p>180</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Tracking-Vorlage, die auf Anzeigenkontoebene für AdWords oder Bing zum Tagging von Landingpages hinzugefügt wurde.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>-4609512587744160000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_CAMPAIGNS {#biz-ad-campaigns}

Kampagnen, die aus verbundenen Anzeigenkonten, Quellsystemen, utm und Self-Reporting importiert wurden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eindeutige Kennung für die Kampagne.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>Die Kampagnen-ID aus dem Quellsystem.</td>
      <td>
        <p>285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Anzeigenkonto, von dem aus die Kampagne importiert wurde.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name für das Anzeigenkonto, von dem aus die Kampagne importiert wurde.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des Advertisers für die Kampagne, insbesondere für Doubleclick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Advertisers für die Kampagne, insbesondere für Doubleclick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie über der Kampagne eine Anzeigengruppe gibt.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie über der Kampagne eine Anzeigengruppe gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Eindeutige Kennung für die Kampagne, verwenden Sie stattdessen das Feld ID .</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne: Verwenden Sie stattdessen das Feld Name .</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Kampagne im Quellsystem noch aktiv ist.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Kampagne im Quellsystem gelöscht wurde.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-08-02 06:35:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Datensatz zum ersten Mal aus dem Quellsystem importiert wurde.</p>
      </td>
      <td>
        <p>2018-08-02 06:35:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne.</p>
      </td>
      <td>
        <p>Partner-Retargeting</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Kampagne für das [!DNL Marketo Measure]-Tagging aktualisiert werden muss.</p>
        <p>(Diagnostisches Feld, von interner Verarbeitung verwendet.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisches Feld für die interne Verarbeitung.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "Kampagne".</p>
      </td>
      <td>
        <p>Kampagne</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenanbieters für die Kampagne.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DAILY_BUDGET</p>
      </td>
      <td>
        <p>number(38,19)</p>
      </td>
      <td>
        <p>Das tägliche Budget, das in der Anzeigenplattform für die Kampagne festgelegt ist.</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Tracking-Vorlage, die auf Kampagnenebene für AdWords oder Bing zum Tagging von Landingpages hinzugefügt wurde.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>-6008900572523230000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_FORMS {#biz-ad-forms}

Ad Forms wurde aus einem beliebigen verbundenen Anzeigenkonto importiert.

<table>
  <tr>
    <th>
      <p>Spalte</p>
    </th>
    <th>
      <p>Datentyp</p>
    </th>
    <th>
      <p>Beschreibung</p>
    </th>
    <th>
      <p>Beispieldaten</p>
    </th>
  </tr>
  <tbody>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für das Anzeigenformular.</p>
      </td>
      <td>
        <p>li.507063119.3757704</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Anzeigenkonto, aus dem das Anzeigenformular importiert wurde.</p>
      </td>
      <td>
        <p>li.507063119</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenkontos, aus dem das Anzeigenformular importiert wurde.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Der Status wurde aus dem Quellsystem gelöscht. Wird auf gelöscht gesetzt, wenn der Status Entwurf, Archiviert oder Abgebrochen lautet.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-08-02 06:35:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Datensatz zum ersten Mal aus dem Quellsystem importiert wurde.</p>
      </td>
      <td>
        <p>2018-08-02 06:35:58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenformulars.</p>
      </td>
      <td>
        <p>NSPA Ebook LGF (Mai 2020)</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "AdForm".</p>
      </td>
      <td>
        <p>AdForm</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenanbieters für das Anzeigenformular.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DESCRIPTION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Beschreibung des Anzeigenformulars.</p>
      </td>
      <td>
        <p>Erfahren Sie, wie intelligente Automatisierung die Prozesseffizienz bei Kreditanträgen zur Refinanzierung von Hypothekendarlehen erhöhen kann.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HEADLINE</p>
      </td>
      <td>varchar</td>
      <td>Überschrift des Anzeigenformulars.</td>
      <td>
        <p>Es ist an der Zeit, den Refinanzierungsvorgang zu automatisieren</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_URL</p>
      </td>
      <td>varchar</td>
      <td>Einstiegs-URL des Anzeigenformulars.</td>
      <td>
        <p>https://adobe.com/blog/refinancing-application-process/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>QUESTIONS</p>
      </td>
      <td>varchar</td>
      <td>Liste der Fragen für das Anzeigenformular.</td>
      <td>
        <p>Vorname:Nachname:E-Mail-Adresse:Land/Region:Auftragstitel:Firmenname</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Status des Anzeigenformulars.</p>
      </td>
      <td>
        <p>gesendet</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>SOURCE_ID</td>
      <td>varchar</td>
      <td>ID für die Quelle, aus der der Datensatz stammt.</td>
      <td>aw.3284209</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_GROUPS {#biz-ad-groups}

Anzeigengruppen, die aus einem verbundenen Anzeigenkonto importiert wurden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Anzeigengruppe.</p>
      </td>
      <td>
        <p>aw.6601259029.317737955.23105326115</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>Die Anzeigengruppen-ID aus dem Quellsystem.</td>
      <td>
        <p>23105326115</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Anzeigenkonto, von dem aus die Anzeigengruppe importiert wurde.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name für das Anzeigenkonto, von dem aus die Anzeigengruppe importiert wurde.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doubleclick-Anzeigen-Hierarchie keine Anzeigengruppe gibt.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doubleclick-Anzeigen-Hierarchie keine Anzeigengruppe gibt.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da dies der Datensatz für die Anzeigengruppe in der Hierarchie ist.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da dies der Datensatz für die Anzeigengruppe in der Hierarchie ist.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne für die Anzeigengruppe.</p>
      </td>
      <td>
        <p>aw.6601259029.317737955</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne für die Anzeigengruppe.</p>
      </td>
      <td>
        <p>Umsatzzuordnung</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob das Anzeigenkonto im Quellsystem noch aktiv ist.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob das Anzeigenkonto im Quellsystem gelöscht wurde.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-08-02 06:36:14.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Datensatz zum ersten Mal aus dem Quellsystem importiert wurde.</p>
      </td>
      <td>
        <p>2018-08-02 06:36:14.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeigengruppe.</p>
      </td>
      <td>
        <p>Umsatzzuordnung - Kontobasiert</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Advertiser für das [!DNL Marketo Measure]-Tagging aktualisiert werden muss.</p>
        <p>(Diagnostisches Feld, von interner Verarbeitung verwendet.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisches Feld für die interne Verarbeitung.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "AdGroup".</p>
      </td>
      <td>
        <p>AdGroup</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenanbieters für die Anzeigengruppe.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NETWORK_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Medien, auf denen die Anzeigengruppe ausgeführt wird.</p>
      </td>
      <td>
        <p>Suchen, Anzeigen, YouTube_Search, YouTube_Watch</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Tracking-Vorlage, die auf Anzeigenkontoebene für AdWords oder Bing zum Tagging von Landingpages hinzugefügt wurde.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>-5594512713562690000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_PROVIDERS

<p>Anzeigenanbieter aus allen verbundenen Anzeigenkonten, einschließlich eines Eintrags für selbst gemeldete Nachrichten, falls zutreffend.</p>

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für den Anzeigenanbieter.</p>
      </td>
      <td>
        <p>Bing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenanbieters.</p>
      </td>
      <td>
        <p>Bing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>4783788151269206864</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ATTRIBUTION_TOUCHPOINTS {#biz-attribution-touchpoints}

<p>Buyer Attribution Touchpoints, alle Touchpoints, die einer Opportunity zugeordnet sind.</p>
<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für den Buyer Attribution Touchpoint (BAT).</p>
      </td>
      <td>
        <p>BAT2_0060Z00000lFHtOQAW_</p>
        <p>0030Z00003K5bpKQAR_2017-06-20:01-05-20-6193330.0b5c5678807c</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-09-01 04:53:53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung für die Chance, der die BVT zugeordnet wird.</p>
      </td>
      <td>
        <p>0060Z00000lFHtOQAW</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Kennung des mit der BVT verknüpften Kontakts.</p>
      </td>
      <td>
        <p>0030Z00003K5bpKQAR</p>
      </td>
    </tr>
    <tr>
      <td>EMAIL</td>
      <td>varchar</td>
      <td>E-Mail-Adresse, die mit dem BAT verknüpft ist.</td>
      <td>person@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Konto, dem das BAT zugeordnet wird.</p>
      </td>
      <td>
        <p>0013100001otbIAAAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für den Benutzer-Touchpoint, der die BVT generiert hat.</p>
      </td>
      <td>
        <p>person@adobe.com_00v1B00003ZbWzHQAV</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum des Touchpoints.</p>
      </td>
      <td>
        <p>2017-06-20 01:05:20.000</p>
      </td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>ID für den Besucher, der mit der BAT verknüpft ist.</td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Aktivitätstyp, Webbesuch, Webformular, Webchat, Telefonaufruf, [CRM]-Kampagne oder [CRM]-Aktivität. Im CRM als "Touchpoint-Typ" bezeichnet.</p>
      </td>
      <td>
        <p>Webformular</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Kanal, in den der Touchpoint fällt, wie in den benutzerdefinierten Kanaldefinitionen innerhalb der Variablen [!DNL Marketo Measure] App. Im CRM als "Marketingkanal - Pfad" bezeichnet.</p>
      </td>
      <td>
        <p>Social.LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die erste Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen im [!DNL Marketo Measure] App. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td>
        <p>ABC</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die zweite Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen im [!DNL Marketo Measure] App. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td>
        <p>Ja</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY3</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die dritte Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen im [!DNL Marketo Measure] App. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td>
        <p>KMU</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY4</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 4. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td>
        <p>Neues Unternehmen</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY5</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 5. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY6</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 6. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY7</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 7. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY8</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 8. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY9</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 9. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY10</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 10. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY11</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 11. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY12</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 12. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY13</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 13. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY14</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 14. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY15</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 15. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus der erkannte Browser, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Chrome</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Version des Browsers, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Plattform, auf der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Version der Plattform, auf der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Landingpage der Sitzung, die zu einem Touchpoint führte. Im CRM als "Landingpage" bezeichnet.</p>
      </td>
      <td>
        <p>http://www.adobe.com/blog/uncover- Truth-Behind-cost-per-lead</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Landingpage der Sitzung, die zu einem Touchpoint führte. Eine Raw-Landingpage enthält alle Abfrageparameter in der URL. Im CRM als "Landingpage - Roh" bezeichnet.</p>
      </td>
      <td>
        <p>http://www.adobe.com/blog/uncover-truth -behind-cost-per-lead?utm_content=27322869&amp;utm_ medium=social&amp;utm_source=linkedin</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In der Regel die externe Landingpage unmittelbar vor dem Besuch des Benutzers auf der Website. Im CRM als "Referrer-Seite" bezeichnet.</p>
      </td>
      <td>
        <p>https://www.linkedin.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In der Regel die externe Landingpage unmittelbar vor dem Besuch des Benutzers auf der Website. Eine Raw-Referrer-Seite kann Abfrageparameter in der URL enthalten. Im CRM als "Referrer Page - Raw" bezeichnet.</p>
      </td>
      <td>
        <p>https://www.linkedin.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das erste Formular, das in einer Sitzung aufgezeichnet wurde und zu einem Touchpoint führte. Nachfolgende Formularübermittlungen werden nicht in der Tabelle "Attribution_Touchpoints" angezeigt, sondern in der Tabelle "Form_Submissions". Im CRM als "Formular-URL" bezeichnet.</p>
      </td>
      <td>
        <p>http://info.adobe.com/intro-guide-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das erste Formular, das in einer Sitzung aufgezeichnet wurde und zu einem Touchpoint führte. Nachfolgende Formularübermittlungen werden nicht in der Tabelle "Attribution_Touchpoints" angezeigt, sondern in der Tabelle "Form_Submissions". Eine Formularrohseite kann Abfrageparameter in der URL enthalten. Im CRM als "Formular-URL - Roh" bezeichnet.</p>
      </td>
      <td>
        <p>http://info.adobe.com/intro-guide-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Übermittlung des Formulars.</p>
      </td>
      <td>
        <p>2017-06-20 01:06:41.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CITY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Stadt, in der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>San Francisco</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Region, in der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Kalifornien</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COUNTRY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus das erkannte Land, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Vereinigte Staaten</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird verwendet, um das Medium zu definieren, das zum Touchpoint führte. Dies kann entweder aus der URL von utm_medium herausgeparst werden. Oder wenn [!DNL Marketo Measure] eine Anzeige auflösen kann, kann es sich auch um Werte wie "cpc" oder "display" handeln.</p>
      </td>
      <td>
        <p>Social Media</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird verwendet, um die Quelle zu definieren, die zum Touchpoint führte. Dies kann aus der URL utm_source analysiert werden, die im Allgemeinen als "CRM-Kampagne" festgelegt ist, wenn sie aus dem CRM synchronisiert wurde. Wenn [!DNL Marketo Measure] eine Anzeige auflösen kann, kann es sich auch um Werte wie "Google AdWords" oder "Facebook" handeln. Im CRM als "Touchpoint-Quelle" bezeichnet.</p>
      </td>
      <td>
        <p>linkedin</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Wert, den der Benutzer in den Browser eingegeben hat, um danach zu suchen, wodurch er schließlich auf die Website gelang. Abhängig vom gekauften Suchbegriff stimmt dies möglicherweise nicht mit den von der Paid Search-Plattform erworbenen Suchbegriffen überein.</p>
      </td>
      <td>
        <p>google [!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Anzeigenplattform, über die [!DNL Marketo Measure] auflösen konnte, in der Regel einer unserer Integrationspartner.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Anzeigenkontos, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenkontos, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Advertisers aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Advertisers aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Site aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Site aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Platzierung aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Platzierung aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>Hindernis</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>aw.6601259029.317738075</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>Marketing-Zuordnung</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeigengruppe aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für Google Adwords.</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeigengruppe aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für Google AdWords.</p>
      </td>
      <td>
        <p>Marketing-Attribution - Allgemein</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeige aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für DoubleClick Campaign Manager und Facebook (Anzeige).</p>
      </td>
      <td>
        <p>dc.6114.8882972.25272734.492579576</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeige aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für DoubleClick Campaign Manager und Facebook (Anzeige).</p>
      </td>
      <td>
        <p>Budget-Webinar - Seitenleiste</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des Creative-Elements aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435.182716179597</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Creative-Elements aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>B2B-Marketing-Attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Zeile des Creative-Elements aus der Suchanzeige, die aus dem Anzeigenkonto abgerufen wurde, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>Anleitung für CMOs herunterladen</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die zweite Zeile des Creative-Elements aus der Suchanzeige, die aus dem Anzeigenkonto abgerufen wurde, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>Erfahren Sie, wie die Attribution den ROI misst, indem Marketingaktivitäten mit dem Umsatz verbunden werden.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Landingpage, auf die das Durchklicken von der Suchanzeige führt und die aus dem Anzeigenkonto abgerufen wird, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Anzeigename der URL, der in der Suchanzeige angezeigt wird und aus dem Anzeigenkonto abgerufen wird, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>http://info.adobe.com/CMOs-Guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des vom Paid Search-Kauf erworbenen Suchbegriffs, abgerufen aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435.4838421670</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des vom Paid Search-Kauf erworbenen Suchbegriffs, abgerufen aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche)</p>
      </td>
      <td>
        <p>"Marketing-Zuordnung"</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Art der Übereinstimmung, die zwischen dem Suchbegriff und dem gekauften Keyword gefunden wird.</p>
      </td>
      <td>
        <p>Exakt</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FIRST_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als Erstkontakt der Opportunity-Journey behandelt wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_LEAD_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als Touch zur Lead-Erstellung der Opportunity-Journey behandelt wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als Touch zur Opportunity-Erstellung der Opportunity-Journey behandelt wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als geschlossene Berührung des Opportunity-Journey behandelt wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGES_TOUCHED</p>
      </td>
      <td>varchar</td>
      <td>Dieses Feld ist veraltet. Informationen zur Phase finden Sie in den Tabellen Stage_Transitions .</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint während der Sitzung ein Formular ausgefüllt hat.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als erster Impression des Opportunity-Journey behandelt wird</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil es sich um einen Erstkontakt handelt (siehe Is_First_Touch).</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil es sich um einen Lead-Erstellungskontakt handelt (siehe Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugewiesen wird, weil er Teil eines U-förmigen Touchings ist (siehe Is_First_Touch und Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil er Teil eines W-förmigen Touchings ist (siehe Is_First_Touch, Is_Lead_Creation_Touch und Is_Opp_Creation_Touch).</p>
      </td>
      <td>
        <p>0,0153374234214425</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil er Teil eines vollständigen Pfadmodells ist (siehe Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch).</p>
      </td>
      <td>
        <p>0,0143061513081193</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CUSTOM_MODEL_PERCENTAGE</p>
      </td>
      <td>number(22,19)</td>
      <td>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil er Teil eines benutzerdefinierten Modells ist (siehe Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch).</td>
      <td>0,0143061513081193</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint gelöscht wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_ROW_KEY</p>
      </td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ATTRIBUTION_AI_TOUCHPOINTS {#biz-attribution-ai-touchpoints}

Aus der Integration der Attributions-KI generierte Daten. Diese Felder werden nur für Kundinnen und Kunden von Marketo Measure Ultimate ausgefüllt.

<table>
<thead>
  <tr>
    <th>Spalte</th>
    <th>Datentyp</th>
    <th>Beschreibung</th>
    <th>Beispieldaten</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>CONVERSION_DATE</td>
    <td>Timestamp_ntz</td>
    <td>Datum der Konversion.</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
  <tr>
    <td>CONVERSION_NAME</td>
    <td>varchar</td>
    <td>Name des Konversionsereignisses (wie von der Kundin bzw. dem Kunden in der Benutzeroberflächeneinstellung angegeben)</td>
    <td> </td>
  </tr>
  <tr>
    <td>CONVERSION_ID</td>
    <td>varchar</td>
    <td>ID für das Konversionsereignis (dies ist der ursprüngliche, eindeutige ID-Wert, der mit dem Ereignisdatensatz im Quelldatensatz gesendet wurde)</td>
    <td>0013100001b44aGAAQ</td>
  </tr>
  <tr>
    <td>CONVERSION_EVENT_ID</td>
    <td>varchar</td>
    <td>ursprüngliche MM-Ereignis-ID für das Konversionsereignis 
<br>einem Benutzer-Touchpoint oder einer Staging-Transition zugeordnet</td>
    <td>00U0Z00000pCZmyUAG</td>
  </tr>
  <tr>
    <td>CONVERSION_ACCOUNT_ID</td>
    <td>varchar</td>
    <td>ursprüngliche MM-Konto-ID für das Konversionsereignis</td>
    <td>0013100001kpAZxAAM</td>
  </tr>
  <tr>
    <td>CONVERSION_OPPORTUNITY_ID</td>
    <td>varchar</td>
    <td>ursprüngliche MM-Opportunity-ID für das Konversionsereignis</td>
    <td>0060Z00000lFHtOQAW</td>
  </tr>
  <tr>
    <td>CONVERSION_LEAD_ID</td>
    <td>varchar</td>
    <td>ursprüngliche MM-Lead-ID für das Konversionsereignis, <br>ist meistens null</td>
    <td>00Q0Z000013dw4GUAQ</td>
  </tr>
  <tr>
    <td>CONVERSION_CONTACT_ID</td>
    <td>varchar</td>
    <td>ursprüngliche MM-Kontakt-ID für das Konversionsereignis
<br>ist meistens null</td>
    <td>00331000032hMxRAAU</td>
  </tr>
  <tr>
    <td>CONVERSION_EVENT_TYPE</td>
    <td>varchar</td>
    <td>Typ des Konversionsereignisses (B2B = Lead-Konversion, B2C = Opportunity-Konversion)</td>
    <td>B2B</td>
  </tr>
  <tr>
    <td>SCORE_DATE</td>
    <td>Timestamp_ntz</td>
    <td>Datum der letzten Bewertung der Touchpoints</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
  <tr>
    <td>INFLUENCED_PERCENT</td>
    <td>number(38,35)</td>
    <td>der Teil der Konvertierung, für den jeder Touchpoint verantwortlich ist</td>
    <td>0,10</td>
  </tr>
  <tr>
    <td>INCREMENTAL_PERCENT</td>
    <td>number(38,35)</td>
    <td>die Höhe der direkt durch einen Touchpoint verursachten geringfügigen Auswirkungen</td>
    <td>0,25</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_DATE</td>
    <td>Timestamp_ntz</td>
    <td>das Touchpoint- oder Staging-Übergangsdatum</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_EVENT_ID</td>
    <td>varchar</td>
    <td>ID für das Ereignis, mit dem der Touchpoint erstellt wurde</td>
    <td>00U3100000VLUnEEAX</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_OPPORTUNITY_ID</td>
    <td>varchar</td>
    <td>ID für die mit dem Touchpoint verknüpfte Opportunity</td>
    <td>0060Z00000lFHtOQAW</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_ACCOUNT_ID</td>
    <td>varchar</td>
    <td>ID für das Konto, das mit dem Touchpoint verknüpft ist</td>
    <td>0013100001kpAZxAAM</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_LEAD_ID</td>
    <td>varchar</td>
    <td>ID für den mit dem Touchpoint verknüpften Lead</td>
    <td>00Q0Z000013dw4GUAQ</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_CONTACT_ID</td>
    <td>varchar</td>
    <td>ID für den mit dem Touchpoint verknüpften Kontakt</td>
    <td>00331000032hMxRAAU</td>
  </tr>
  <tr>
    <td>COUNT_TO_CONVERSION</td>
    <td>number(38,0)</td>
    <td>der Rang oder der ordinale Wert des Touchpoints in der Kette, der zum Konversionsereignis führt</td>
    <td>10000</td>
  </tr>
  <tr>
    <td>AAI_SOURCE_ID</td>
    <td>varchar</td>
    <td>Fremdschlüssel zur Attributions-KI-Quelltabelle</td>
    <td> </td>
  </tr>
  <tr>
    <td>_CREATED_DATE</td>
    <td>Timestamp_ntz</td>
    <td>Datum, an dem der Eintrag in Snowflake erstellt wurde</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
  <tr>
    <td>_MODIFIED_DATE</td>
    <td>Timestamp_ntz</td>
    <td>Datum, an dem der Eintrag zuletzt in Snowflake geändert wurde</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
  <tr>
    <td>_DELETED_DATE</td>
    <td>Timestamp_ntz</td>
    <td>Datum, an dem der Eintrag in Snowflake gelöscht wurde</td>
    <td>2020-01-01 01:01:00.000</td>
  </tr>
</tbody>
</table>

### BIZ_CAMPAIGN_MEMBERS {#biz-campaign-members}

Aus dem Quellsystem importierte Kampagnenmitglieder. Diese Tabelle ist leer, wenn die Kampagnensynchronisierung deaktiviert ist.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>Die Kennung des Kampagnenmitglieds aus dem Quellsystem.</td>
      <td>00v0Z00001VVzdLQAT</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Datum der letzten Änderung des Kampagnenmitglieds aus dem Quellsystem.</p>
      </td>
      <td>
        <p>2018-08-31 20:49:54.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Erstellungsdatum des Kampagnenmitglieds aus dem Quellsystem.</p>
      </td>
      <td>
        <p>2018-08-31 20:49:54.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_TOUCH_POINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum und Uhrzeit, die der Kunde einstellt, um das Kampagnendatum zu überschreiben, und diesen Wert stattdessen für das Touchpoint-Datum zu verwenden.</p>
      </td>
      <td>
        <p>2018-08-30 18:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für den Lead, an den das Kampagnenmitglied gebunden ist.</p>
      </td>
      <td>
        <p>00Q0Z000013dw4GUAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail für den Lead, an den das Kampagnenmitglied gebunden ist.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>ID für den Kontakt, an den das Kampagnenmitglied gebunden ist.</p>
      </td>
      <td>
        <p>00331000032hMxRAAU</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail für den Kontakt, an den das Kampagnenmitglied gebunden ist.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Status des Kampagnenmitglieds, in der Regel auf Gesendet oder Beantwortet oder einen anderen benutzerdefinierter Wert eingestellt. Dieser Status ist an den Campaign_Sync_Type gebunden, um zu bestimmen, für welche Kampagnenmitglieder Touchpoints erstellt werden sollen.</p>
      </td>
      <td>
        <p>Gesendet</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_RESPONDED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Teilt mit, ob das Kampagnenmitglied in der Statusauswahl als "Beantwortet" markiert wurde.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_RESPONDED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der ersten Antwort des Kampagnenmitglieds.</p>
      </td>
      <td>
        <p>2018-08-30 07:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne, zu der das Kampagnenmitglied gehört.</p>
      </td>
      <td>
        <p>Schnelle CMO-Interviews</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der zugehörigen Kampagne, zu der das Kampagnenmitglied gehört.</p>
      </td>
      <td>
        <p>7010Z000001TcKlQAK</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Typ, der für die Kampagne ausgewählt wird, zu der das Kampagnenmitglied gehört. Der Typ wird für die Zuordnung des Marketingkanals verwendet.</p>
      </td>
      <td>
        <p>Offline</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_SYNC_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Bestimmt, für welche Kampagnenmitglieder Touchpoints erstellt werden. Mögliche Werte sind: Include_All, Include_Responded, Exclude_All.</p>
      </td>
      <td>
        <p>Include_All</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SYNC_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Audit-Feld: Gibt an, ob ein Buyer Touchpoint für den Lead generiert wurde. Wenn kein Touchpoint erstellt wurde, wird der Grund angegeben, warum er sich nicht qualifiziert hat.</p>
      </td>
      <td>
        <p>Kein Touchpoint: Datum außerhalb des Modells</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_SYNC_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Audit-Feld: Gibt an, ob ein Buyer Touchpoint für den Kontakt generiert wurde. Wenn kein Touchpoint erstellt wurde, wird der Grund angegeben, warum er sich nicht qualifiziert hat.</p>
      </td>
      <td>
        <p>Touchpoint erstellt</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_SYNC_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Audit-Feld: Gibt an, ob ein Buyer Attribution Touchpoint für die Opportunity generiert wurde oder nicht. Wenn kein Touchpoint erstellt wurde, wird der Grund angegeben, warum er sich nicht qualifiziert hat.</p>
      </td>
      <td>
        <p>Touchpoint erstellt</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Datensatz im Quellsystem als gelöscht betrachtet wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Benutzerdefinierte Eigenschaften im JSON-Format, die [!DNL Marketo Measure] aus dem Quellsystem importiert hat.</td>
      <td>{"Campaign_Type__c":"Dinners","Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CHANNELS {#biz-channels}

Marketing-Kanäle, wie in der [!DNL Marketo Measure]-Anwendung erstellt.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für den Kanal.</p>
      </td>
      <td>
        <p>Organic Search.Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Kanals.</p>
      </td>
      <td>
        <p>Organic Search.Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>6008900572523230000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Das Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Das Datum, an dem der Datensatz zuletzt in Snowflake geändert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Das Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CONTACTS {#biz-contacts}

Aus dem Quellsystem importierte Kontakte.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Die Kontakt-ID aus dem Quellsystem.</p>
      </td>
      <td>
        <p>0030Z00003OzioeQAB</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Kontaktdatensatzes im Quellsystem.</p>
      </td>
      <td>
        <p>2018-09-05 05:17:53.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Erstellung des Kontaktdatensatzes, aus dem Quellsystem.</p>
      </td>
      <td>
        <p>2018-09-05 05:17:51.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail-Adresse des Kontakts vom Quellsystem.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNTID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Kontos, das mit dem Kontakt verknüpft ist.</p>
      </td>
      <td>
        <p>0013100001b44aGAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Quelle, in der der Lead erstellt wurde.</p>
      </td>
      <td>
        <p>Werbung</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Aktuelle Phase des Kontakts, die als benutzerdefinierte Phase erkannt wird und in der [!DNL Marketo Measure]-Anwendung erstellt werden kann.</p>
      </td>
      <td>
        <p>Demo geplant</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Alle vorherigen Phasen für den Kontakt, die als benutzerdefinierte Phasen erkannt werden, die in der [!DNL Marketo Measure]-Anwendung erstellt werden können.</p>
      </td>
      <td>
        <p>Offen - Kontakt</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>number(38,19)</p>
      </td>
      <td>
        <p>Diese Funktion ist veraltet. Verwenden Sie diese Spalte nicht.</p>
      </td>
      <td>
        <p>Nicht zutreffend</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die [!DNL Marketo Measure]-Cookie-ID, die zum Ausfüllen von einem Integrationspartner verwendet wird, um ein Offline-Ereignis einer Websitzung zuzuordnen. Anforderung: Anrufverfolgung aktivieren: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Datensatz im Quellsystem gelöscht wird.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>IS_DUPLICATE</td>
      <td>boolean</td>
      <td>Dient zum Deduplizieren von Datensätzen, wenn sowohl eine CRM- als auch eine Marketo-Integration eingerichtet sind. Bei Duplikaten wird der Marketo-Kontakt als "true"markiert.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>SOURCE_SYSTEM</td>
      <td>varchar</td>
      <td>Gibt an, ob der Datensatz aus einem CRM-System oder einer Marketo-Integration stammt.</td>
      <td>Crm</td>
    </tr>
    <tr>
      <td>OTHER_SYSTEM_ID</td>
      <td>varchar</td>
      <td>Ordnet eine Person aus einer Marketo-Integration einem Kontakt aus einer CRM-Integration zu. Wenn sowohl eine CRM- als auch eine Marketo-Integration vorhanden sind, ist der Wert die entsprechende ID.</td>
      <td>1234 / 00Q0Z00001OohgTUAR</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Benutzerdefinierte Eigenschaften im JSON-Format, die [!DNL Marketo Measure] aus dem Quellsystem importiert hat.</td>
      <td>{"Contact_Type__c":"CMO", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>number(38,0)</td>
      <td>Fremdschlüssel zur Biz_Facts-Ansicht.</td>
      <td>3263982503087870000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td><b>*</b> JOB_TITLE</td>
      <td>varchar</td>
      <td>Aufgabenbereich des Kontakts.</td>
      <td>CEO, Vizepräsidentin bzw. Vizepräsident</td>
    </tr>
  </tbody>
</table>
<p>
<b>*</b> <i>Nur verfügbar in Marketo Measure Ultimate</i>
<p>

### BIZ_CONVERSION_RATES {#biz-conversion-rates}

Aus dem Quellsystem importierte Währungskonversionsraten.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>number(38,0)</td>
      <td>Eine eindeutige ID für den Datensatz.</td>
      <td>-5942345438803054604</td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>number(38,0)</td>
      <td>ID-Wert für die Währung.</td>
      <td>7493833133899044458</td>
    </tr>
    <tr>
      <td>SOURCE_ISO_CODE</td>
      <td>varchar</td>
      <td>Währungs-ISO-Code, aus dem Quellsystem.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>START_DATE</td>
      <td>timestamp_ntz</td>
      <td>Startdatum der Konversionsrate.</td>
      <td>2018-11-01 00:00:00.000</td>
    </tr>
    <tr>
      <td>END_DATE</td>
      <td>timestamp_ntz</td>
      <td>Nächstes Startdatum für die Konversionsrate. (Das Enddatum für die Konversionsrate ist end_date minus 1 Tag.)</td>
      <td>2018-09-01 00:00:00.000</td>
    </tr>
    <tr>
      <td>CONVERSION_RATE</td>
      <td>number(38,0)</td>
      <td>Wechselkurs, der zum Konvertieren der Währung in die Unternehmenskurve verwendet wird.</td>
      <td>0,76728300</td>
    </tr>
    <tr>
      <td>IS_CURRENT</td>
      <td>boolean</td>
      <td>Die Semantik dieses Felds wurde beschädigt. Nicht verwenden.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz im Quellsystem erstellt wurde.</td>
      <td>2019-03-30 00:54:50.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes im Quellsystem.</td>
      <td>2019-03-30 00:54:50.000</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Gibt an, ob der Datensatz im Quellsystem als gelöscht betrachtet wird.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_COSTS {#biz-costs}

Kostendaten, die aus verbundenen Anzeigenkonten oder aus selbst gemeldeten Marketingausgaben importiert wurden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Eine eindeutige ID für den Kosteneintrag.</td>
      <td>aw.6601259029.285114995.21703163075.[AdWords Display]_2018-09-06</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes.</td>
      <td>2018-09-06 12:22:45.000</td>
    </tr>
    <tr>
      <td>COST_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum des Entstehens (oder Zuschreibens) der Kosten.</td>
      <td>2018-09-06 00:00:00.000</td>
    </tr>
    <tr>
      <td>SOURCE</td>
      <td>varchar</td>
      <td>Quelle der gemeldeten Kosten.</td>
      <td>[AdWords Anzeige]</td>
    </tr>
    <tr>
      <td>COST_IN_MICRO</td>
      <td>number(38,0)</td>
      <td>Kosten in Millionen. Der Benutzer muss den Wert durch 1000000 teilen.</td>
      <td>1410000</td>
    </tr>
    <tr>
      <td>CLICKS</td>
      <td>number(38,0)</td>
      <td>Anzahl der für die Gruppe gemeldeten Klicks für den Tag.</td>
      <td>4</td>
    </tr>
    <tr>
      <td>IMPRESSIONS</td>
      <td>number(38,0)</td>
      <td>Anzahl der für die Gruppe gemeldeten Impressionen für den Tag.</td>
      <td>4187</td>
    </tr>
    <tr>
      <td>ESTIMATED_TOTAL_POSSIBLE_IMPRESSIONS</td>
      <td>number(38,0)</td>
      <td>Gesamtzahl der von DCM geschätzten Impressionen für die Gruppe für den Tag.</td>
      <td>5024</td>
    </tr>
    <tr>
      <td>AD_PROVIDER</td>
      <td>varchar</td>
      <td>Anbieter, für den die Kosten abgerufen wurden.</td>
      <td>Google</td>
    </tr>
    <tr>
      <td>CHANNEL_UNIQUE_ID</td>
      <td>varchar</td>
      <td>ID für den Marketingkanal, erstellt von [!DNL Marketo Measure].</td>
      <td>Display.Google</td>
    </tr>
    <tr>
      <td>CHANNEL_NAME</td>
      <td>varchar</td>
      <td>Name für den Marketingkanal, der vom Kunden in der [!DNL Marketo Measure]-App erstellt wurde.</td>
      <td>Display.Google</td>
    </tr>
    <tr>
      <td>CHANNEL_IS_AGGREGATABLE_COST</td>
      <td>boolean</td>
      <td>Gibt an, ob die Zeile Kosten enthält, die nach Kanal summiert werden können. (d. h. um die Kanalkosten zu erhalten, summieren Sie die Zeilen, für die diese Spalte "true" ist.)</td>
      <td>false</td>
    </tr>
    <tr>
      <td>ADVERTISER_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Kennung des Advertisers, der aus der Anzeigenverbindung abgerufen wurde, insbesondere für Doubleclick-Verbindungen.</td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>ADVERTISER_NAME</td>
      <td>varchar</td>
      <td>Name des Advertisers, der aus der Anzeigenverbindung gezogen wird, insbesondere für Doubleclick-Verbindungen.</td>
      <td>[!DNL Marketo Measure] Marketing Analytics</td>
    </tr>
    <tr>
      <td>ADVERTISER_IS_AGGREGATABLE_COST</td>
      <td>boolean</td>
      <td>Gibt an, ob die Zeile Kosten enthält, die vom Advertiser zusammengefasst werden können. (d. h. um die Kosten des Advertisers zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Anzeigenkontos, das aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenkontos, das aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Konto summiert werden können. (d. h. um die Kontokosten zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne, die aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne, die aus der Anzeigenverbindung abgerufen wird.</p>
      </td>
      <td>
        <p>Partner-Retargeting</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die von Campaign zusammengefasst werden können. (d. h. um die Kampagnenkosten zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeigengruppe, die aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995.21703163075</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeigengruppe, die aus der Anzeigenverbindung abgerufen wird.</p>
      </td>
      <td>
        <p>Software für die Attributionsverwaltung | Wortgruppe</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die von Anzeigengruppen zusammengefasst werden können. (d. h. um die Anzeigengruppenkosten zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeige, die aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>dc.6114.9131003.24149929.467969200</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeige, die aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>Anzeigenname: Ad3-320x50.gif; 320 x 50</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Anzeige summiert werden können. (d. h. um die Anzeigenkosten zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des Creative-Elements, das aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995.51749608028.266050115160</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Creative-Elements, das aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>Gartner Magic Quadrant 2019</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die von Creative zusammengefasst werden können. (d. h. um die Creative-Kosten zu erhalten, summieren Sie die Zeilen, für die diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des Suchbegriffs, der aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>aw.6601259029.669328935.39419128772.99608705795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Suchbegriffs, der aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>sfdc-Marketing-Attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Keyword summiert werden können. (d. h. um die Suchbegriffkosten zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Platzierung, die aus der Anzeigenverbindung abgerufen wird.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Platzierung, die aus der Anzeigenverbindung abgerufen wird.</p>
      </td>
      <td>
        <p>Hindernis</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Platzierung summiert werden können. (d. h. um die Platzierungskosten zu erhalten, summieren Sie die Zeilen, für die diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Site, die aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Site, die aus der Anzeigenverbindung abgerufen wurde.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Site summiert werden können. (d. h. um die Site-Kosten zu erhalten, summieren Sie die Zeilen, für die diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Datensatz im Quellsystem als gelöscht betrachtet wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>ISO_CURRENCY_CODE</td>
      <td>varchar</td>
      <td>ISO-Code für die Währung, der aus dem Quellsystem importiert wird.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>SOURCE_ID</td>
      <td>varchar</td>
      <td>ID für die Quelle, aus der der Datensatz stammt.</td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>number(38,0)</td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ROW_KEY</p>
      </td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>number(38,0)</td>
      <td>ID-Wert der Währung für den Datensatz.</td>
      <td>
        <p>-3253183181619994799</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CREATIVES {#biz-creatives}

Creatives, die aus einem beliebigen verbundenen Anzeigenkonto importiert wurden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Creative-Komponente.</p>
      </td>
      <td>
        <p>ba.3284209.132855866.4556709270.10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>Die Creative ID aus dem Quellsystem.</td>
      <td>
        <p>10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Anzeigenkonto, aus dem Creative importiert wurde.</p>
      </td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name für das Anzeigenkonto, aus dem das Creative-Element importiert wurde.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des Advertisers für Creative, insbesondere für Doubleclick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Advertisers für das Creative-Element, insbesondere für Doubleclick.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeigengruppe für Creative.</p>
      </td>
      <td>fb.106851586409075.6052044288804.6052044290004</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeigengruppe für Creative.</p>
      </td>
      <td>Anzeigenset für Anzeige B</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne für Creative.</p>
      </td>
      <td>
        <p>ba.3284209.132855866</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne für Creative.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob Creative im Quellsystem noch aktiv ist.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Creative-Komponente im Quellsystem gelöscht wurde.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-08-02 06:36:25.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Datensatz zum ersten Mal aus dem Quellsystem importiert wurde.</p>
      </td>
      <td>
        <p>2018-08-02 06:36:25.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Creative-Elements aus dem Quellsystem.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Creative-Inhalte für [!DNL Marketo Measure]-Tagging aktualisiert werden müssen.</p>
        <p>(Diagnostisches Feld, von interner Verarbeitung verwendet.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisches Feld für interne Verarbeitung.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "Creative".</p>
      </td>
      <td>
        <p>Werbemittel</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenanbieters für Creative.</p>
      </td>
      <td>
        <p>BingAds</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aktuelle Version der URL einschließlich aller Tags.</p>
        <p>(Diagnostisches Feld für die interne Verarbeitung.)</p>
      </td>
      <td>
        <p>cdn.adobe.com/redir?lp=http%3a%2f%2fwww.pipelinemarketing.com%2f&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}&amp;utm_content={adid}&amp;utm_term={keyword}&amp;utm_campaign=PipelineMarketing.com&amp;utm_source=bing&amp;utm_medium=cpc</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_DISPLAY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die gekürzte und benutzerfreundliche URL, die auf Creative angezeigt wird.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Vorheriger Wert für URL_CURRENT.</p>
        <p>(Diagnostisches Feld für die interne Verarbeitung.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die URL wird mit [!DNL Marketo Measure] Parameter.</p>
        <p>(Diagnostisches Feld für die interne Verarbeitung.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_SHORTENED</p>
      </td>
      <td>varchar</td>
      <td>Die gekürzte und benutzerfreundliche URL, die auf Creative angezeigt wird. (Wird nur für LinkedIn Ads verwendet.)</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Typ von Creative-Element, z. B. Text oder Anzeige</p>
      </td>
      <td>
        <p>Text</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_UPGRADED_URL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob das Creative-Element aktualisierte URLs verwendet.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HEADLINE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die oberste Zeile (Überschrift) des Creative-Elements</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DESCRIPTION_LINE_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Kopie aus der ersten Zeile des Creative-Elements</p>
      </td>
      <td>
        <p>Verbinden und lernen Sie mit umsatzorientierten B2B-Marketingexperten. Treten Sie der Community bei.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DESCRIPTION_LINE_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Kopie aus der zweiten Zeile des Creative-Elements</p>
      </td>
      <td>
        <p>Haben Sie Analytics verwendet? Hinterlassen Sie heute einen Review!</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>Diagnosefeld für interne Verarbeitung.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>Diagnosefeld für interne Verarbeitung.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>Diagnosefeld für interne Verarbeitung.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Diagnosefeld für interne Verarbeitung.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SHARE_URN</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Freigabe-ID. (Wird nur für LinkedIn Ads verwendet.)</p>
      </td>
      <td>
        <p>urn:li:share:6376987561897848832</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>Fremdschlüssel zur Biz_Facts-Ansicht.</td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CRM_EVENTS {#biz-crm-events}

Aus dem Quellsystem importierte Ereignisse. Diese Tabelle ist leer, wenn die Aktivitätensynchronisierung deaktiviert ist.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Die Ereignis-ID aus dem Quellsystem.</p>
      </td>
      <td>
        <p>00U3100000VLUnEEAX</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Erstellung des Ereignisses im Quellsystem.</p>
      </td>
      <td>
        <p>2016-12-12 19:32:53.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Ereignisses im Quellsystem.</p>
      </td>
      <td>
        <p>2018-09-03 08:39:51.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für den mit dem Ereignis verknüpften Lead.</p>
      </td>
      <td>
        <p>00Q0Z000013eVrxUAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail für den mit dem Ereignis verknüpften Lead.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>ID für den mit dem Ereignis verknüpften Kontakt.</p>
      </td>
      <td>
        <p>0030Z00003OyjbOQAR</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail für den mit dem Ereignis verknüpften Kontakt.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die [!DNL Marketo Measure]-Cookie-ID, die zum Ausfüllen von einem Integrationspartner verwendet wird, um ein Offline-Ereignis einer Websitzung zuzuordnen. Anforderung: Anrufverfolgung aktivieren: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Aktivitätstyps aus dem Quellsystem.</p>
      </td>
      <td>
        <p>E-Mail</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_START_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Startdatum für das Ereignis, eine der Optionen zur Bestimmung des Touchpoint-Datums.</p>
      </td>
      <td>
        <p>2016-12-16 19:30:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_END_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Enddatum für das Ereignis, eine der Optionen zur Bestimmung des Touchpoint-Datums.</p>
      </td>
      <td>
        <p>2016-12-16 21:30:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Gibt an, ob der Datensatz im Quellsystem als gelöscht betrachtet wird.</td>
      <td>
        <p>Falsch</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Benutzerdefinierte Eigenschaften im JSON-Format, die [!DNL Marketo Measure] aus dem Quellsystem importiert hat.</td>
      <td>{"Contact_Type__c":"CMO","Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CRM_TASKS {#biz-crm-tasks}

Aus dem Quellsystem importierte Aufgaben. Diese Tabelle wird gefüllt, wenn die Aktivitätensynchronisierung ODER das Aufruftracking aktiviert ist.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Die Aufgaben-ID aus dem Quellsystem.</p>
      </td>
      <td>
        <p>00T0Z00004Rf62rUAB</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Erstellung der Aufgabe, aus dem Quellsystem.</p>
      </td>
      <td>
        <p>2018-08-27 18:30:25.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung der Aufgabe, aus dem Quellsystem.</p>
      </td>
      <td>
        <p>2018-08-27 18:31:53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für den mit der Aufgabe verknüpften Lead.</p>
      </td>
      <td>
        <p>00Q0Z000013eVrxUAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail für den mit der Aufgabe verknüpften Lead.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>ID für den mit der Aufgabe verknüpften Kontakt.</p>
      </td>
      <td>
        <p>00331000038uGfhAAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail für den mit der Aufgabe verknüpften Kontakt.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die [!DNL Marketo Measure]-Cookie-ID, die zum Ausfüllen von einem Integrationspartner verwendet wird, um ein Offline-Ereignis einer Websitzung zuzuordnen. Anforderung: Anrufverfolgung aktivieren: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Aktivitätstyps aus dem Quellsystem.</p>
      </td>
      <td>
        <p>Anruf</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem die Aufgabe aufgetreten ist, eine der Optionen, mit denen das Touchpoint-Datum bestimmt wird.</p>
      </td>
      <td>
        <p>2018-08-27 07:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Gibt an, ob der Datensatz im Quellsystem als gelöscht betrachtet wird.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Benutzerdefinierte Eigenschaften im JSON-Format, die [!DNL Marketo Measure] aus dem Quellsystem importiert hat.</td>
      <td>{"Contact_Type__c":"CMO", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CURRENCIES {#biz-currencies}

Tabelle aller ISO-Währungen.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>number(38,0)</td>
      <td>Eine eindeutige ID für den Währungsdatensatz.</td>
      <td>139474809945095870</td>
    </tr>
    <tr>
      <td>ISO_CODE</td>
      <td>varchar</td>
      <td>ISO-Code für die Währung.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>IS_CORPORATE</td>
      <td>boolean</td>
      <td>Gibt an, ob die Währung die Unternehmenswährung ist.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>IS_ENABLED</td>
      <td>boolean</td>
      <td>Gibt an, ob die Währung im Quellsystem aktiviert ist.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz zuletzt geändert wurde in [!DNL Marketo Measure].</td>
      <td>2018-08-27 18:30:25.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE_CRM</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes im Quellsystem.</td>
      <td>2018-08-27 18:30:25.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der Erstellung des Datensatzes in [!DNL Marketo Measure]</td>
      <td>2018-08-27 18:30:25.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE_CRM</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz im Quellsystem erstellt wurde.</td>
      <td>2018-08-27 18:30:25.000</td>
    </tr>
    <tr>
      <td>ISO_NUMERIC</td>
      <td>number(38,0)</td>
      <td>Numerischer ISO-Standardcode.</td>
      <td>048</td>
    </tr>
    <tr>
      <td>EXPONENT</td>
      <td>number(38,0)</td>
      <td>Die Anzahl der Dezimalstellen zwischen der kleinsten definierten Währungseinheit und einer ganzen Währungseinheit.</td>
      <td>2</td>
    </tr>
    <tr>
      <td>NAME</td>
      <td>varchar</td>
      <td>Name der Währung.</td>
      <td>Argentinischer Peso</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOMER_AB_TESTS {#biz-customer-ab-tests}

AB-Tests aufgezeichnet. Diese Tabelle ist leer, wenn AB-Tests nicht aktiviert sind.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Cookie-ID der zugehörigen Besucher-ID.</p>
      </td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete Cookie-ID zum Zeitpunkt der Ereignisprotokollierung.</p>
      </td>
      <td>36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Chat protokolliert wurde.</p>
      </td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>IP_ADDRESS</td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete IP-Adresse zum Zeitpunkt der Protokollierung des Experiments.</p>
      </td>
      <td>192.0.2.1</td>
    </tr>
    <tr>
      <td>
        <p>EXPERIMENT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die ID des Experiments, das von der AB-Testplattform abgerufen wurde.</p>
      </td>
      <td>123</td>
    </tr>
    <tr>
      <td>
        <p>EXPERIMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name des Experiments, das von der AB-Testplattform abgerufen wurde.</p>
      </td>
      <td>Experiment A</td>
    </tr>
    <tr>
      <td>
        <p>VARIATION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Variantenkennung des Experiments, das von der AB-Testplattform abgerufen wurde.</p>
      </td>
      <td>456</td>
    </tr>
    <tr>
      <td>
        <p>VARIATION_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Variantenname des Experiments, das von der AB-Testplattform abgerufen wurde.</p>
      </td>
      <td>Blauer Test</td>
    </tr>
    <tr>
      <td>
        <p>ABTEST_USER_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die ID des Benutzers, dem das Experiment bereitgestellt wurde, das von der AB-Testplattform abgerufen wurde.</p>
      </td>
      <td>584d64et</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Datensatz gelöscht, für Diagnose und Prüfung verwendet wurde.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOMER_EVENTS {#biz-customer-events}

Web-Ereignisse, die mit benutzerdefinierten Ereignissen in JavaScript aufgezeichnet wurden. Diese Tabelle ist leer, wenn [!DNL Marketo Measure]-Ereignisse nicht aktiviert sind.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Cookie-ID der zugehörigen Besucher-ID.</p>
      </td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete Cookie-ID zum Zeitpunkt der Auslösung des Ereignisses aus dem benutzerdefinierten JavaScript.</p>
      </td>
      <td>36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Datum, an dem das Ereignis vom benutzerdefinierten JavaScript ausgelöst wurde.</p>
      </td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Das letzte Datum, an dem der Datensatz geändert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete IP-Adresse zum Zeitpunkt der Auslösung des Ereignisses aus dem benutzerdefinierten JavaScript.</p>
      </td>
      <td>192.0.2.1</td>
    </tr>
    <tr>
      <td>
        <p>KEY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name des Ereignisses, das durch das benutzerdefinierte JavaScript ausgelöst wurde.</p>
      </td>
      <td>Videoansicht</td>
    </tr>
    <tr>
      <td>
        <p>VALUE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Wert, der dem Ereignis zugewiesen wurde, das vom benutzerdefinierten JavaScript ausgelöst wurde.</p>
      </td>
      <td>75 % angezeigt</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Datensatz gelöscht, für Diagnose und Prüfung verwendet wurde.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOM_LANDING_PAGES {#biz-custom-landing-pages}

Landing-Pages, die von einem beliebigen verbundenen Anzeigenkonto heruntergeladen wurden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für den Datensatz.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>ID für das Anzeigenkonto, von dem die Landingpage importiert wurde.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>Name des Anzeigenkontos, von dem die Landingpage importiert wurde</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des Advertisers für die Landingpage, insbesondere für Doubleclick.</p>
      </td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Advertisers für die Landingpage, insbesondere für Doubleclick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>ID der Anzeigengruppe für die Landingpage.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeigengruppe für die Landingpage.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne für die Landingpage.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne für die Landingpage.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Datum der letzten Änderung der Zeile</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_EMAIL_TO_VISITOR_IDS {#biz-email-to-visitor-ids}

Zuordnungstabelle für E-Mail-Adressen und Besucher-IDs.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Eine eindeutige ID für den Datensatz.</td>
      <td>
        <p>0013800001MMPPiAAP_person@adobe.com|2022-01-05 17:22:13 000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Eine bekannte E-Mail-Adresse, die von einer Sitzung an eine bestimmte Besucher-ID gebunden ist</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das erste Cookie der zugehörigen Besucher-ID</p>
      </td>
      <td>
        <p>v_36ec805b4db344d6e92c972c86aee34a</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Datum der letzten Änderung der Zeile</p>
      </td>
      <td>
        <p>2018-08-14 23:55:03.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Erstellungsdatum der Zeile</p>
      </td>
      <td>
        <p>2018-08-14 23:55:03.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Datensatz als gelöscht gilt, für Diagnose und Prüfung verwendet wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>IS_IGNORE</td>
      <td>boolean</td>
      <td>Gibt an, ob die E-Mail- oder Besucher-ID als Rauschen oder Spam gilt, wird für die interne Verarbeitung verwendet.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_FACTS {#biz-facts}

Vereinigungen, die Impressionen, Seitenansichten, Besuche, Formularübermittlungen, Benutzer-Touchpoints, Touchpoint (BT), Attribution Touchpoints (BAT) und Kostendaten kombinieren. Wird intern zur Unterstützung verwendet [!DNL Marketo Measure] Berichterstellung.

>[!IMPORTANT]
>
>Marketo Measure wird diese Tabelle Mitte 2024 einstellen. Wenn Sie sie selbst erstellen möchten, führen Sie [diese SQL-Abfrage](/help/marketo-measure-data-warehouse/assets/BIZ_FACTS.sql) aus.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
      <td>COST_KEY</td>
      <td>number(38,0)</td>
      <td>Wird für den Beitritt zum Kostentabelle verwendet.</td>
      <td>2672629811884560039</td>
    </tr>
    <tr>
      <td>ATP_KEY</td>
      <td>number(38,0)</td>
      <td>Wird verwendet, um eine Verknüpfung zur Tabelle "Attribution Touchpoints"herzustellen.</td>
      <td>2672629811884560039</td>
    </tr>
    <tr>
      <td>TP_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit den Touchpoints- oder Benutzer-Touchpoints-Tabellen verwendet.</td>
      <td>5028390208679093800</td>
    </tr>
    <tr>
      <td>PAGE_VIEW_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Seitenansichten" verwendet.</td>
      <td>-8044063242541720607</td>
    </tr>
    <tr>
      <td>SESSION_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Sitzungstabelle verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>Die erste Cookie-ID der zugehörigen Besucher-ID.</td>
      <td>v_530d8334c455460df0d48f48270a4b23</td>
    </tr>
    <tr>
      <td>COOKIE_ID</td>
      <td>varchar</td>
      <td>Die aufgezeichnete Cookie-ID zum Zeitpunkt der Ereignisprotokollierung.</td>
      <td>530d8334c455460df0d48f48270a4b23</td>
    </tr>
    <tr>
      <td>FORM_SUBMIT_KEY</td>
      <td>number(38,0)</td>
      <td>Wird verwendet, um eine Verknüpfung zur Tabelle "Formular-Übermittlungen"herzustellen.</td>
      <td>-8659572802702769670</td>
    </tr>
    <tr>
      <td>IMPRESSION_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Impressionstabelle verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der URL-Tabelle verwendet.</td>
      <td>4079876040770132443</td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der URL-Tabelle verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der URL-Tabelle verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>AD_PROVIDER_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Anzeigenanbieter“ verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Wird zum Verbinden mit der Tabelle "Kanäle“ verwendet.</p>
      </td>
      <td>
        <p>-1921844114032355934</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Wird zum Verbinden mit der Tabelle "Werbekampagnen“ verwendet.</p>
      </td>
      <td>
        <p>252687814634577606</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Wird zum Verbinden mit der Tabelle "Keywords“ verwendet.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Wird zum Verbinden mit der Anzeigentabelle verwendet.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Wird zum Verbinden mit der Tabelle "Anzeigengruppen“ verwendet.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Wird zum Verbinden mit der Creatives-Tabelle verwendet.</p>
      </td>
      <td>
        <p>-2333871387956621113</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Wird zum Verbinden mit der Sites-Tabelle verwendet.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Wird zum Verbinden mit der Tabelle "Advertiser" verwendet.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Wird zum Verbinden mit der Tabelle "Anzeigenkonten" verwendet.</p>
      </td>
      <td>
        <p>1825012532740770032</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Wird zum Verbinden mit der Tabelle "Platzierungen" verwendet.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>CATEGORY_01_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_02_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_03_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_04_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_05_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_06_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_07_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_08_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_09_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_10_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_11_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_12_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORY_13_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_14_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORY_15_KEY</td>
      <td>number(38,0)</td>
      <td>Wird zum Verbinden mit der Tabelle "Segmente" verwendet.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>TYPE</td>
      <td>number(38,0)</td>
      <td>Gibt den Faktentyp der Zeile an. 1 = Buyer Attribution Touchpoint 2 = Kosten 3 = Buyer Touchpoint 4 = Benutzer-Touchpoint 5 = Seitenansicht 6 = Sitzung 7 = Formular-Übermittlung 8 = Impression</td>
      <td>3</td>
    </tr>
    <tr>
      <td>DATE</td>
      <td>Datum</td>
      <td>Datum, an dem das Ereignis eingetreten ist.</td>
      <td>2018-08-28</td>
    </tr>
    <tr>
      <td>TIMESTAMP</td>
      <td>timestamp_ntz</td>
      <td>Datum und Uhrzeit des Eintretens des Ereignisses.</td>
      <td>2018-08-28 19:39:15.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung der Zeile.</p>
      </td>
      <td>
        <p>2018-08-29 00:46:47.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COST_IN_MICRO</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Kosten in Millionen. Der Benutzer muss den Wert durch 1000000 teilen.</p>
      </td>
      <td>
        <p>27370000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IMPRESSIONS</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Anzahl der für die Gruppe gemeldeten Impressionen für den Tag.</p>
      </td>
      <td>
        <p>340</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLICKS</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Anzahl der für die Gruppe gemeldeten Klicks für den Tag.</p>
      </td>
      <td>4</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil es sich um einen Erstkontakt handelt.</p>
      </td>
      <td>0,0000000000000000000</td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil es sich um einen Lead-Erstellungskontakt handelt.</p>
      </td>
      <td>100,0000000000000000000</td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet wird, weil er Teil eines U-förmigen Touchings ist.</p>
      </td>
      <td>
        <p>100,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet wird, weil er Teil eines W-förmigen Touchings ist.</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugewiesen wird, weil er Teil eines vollständigen Pfadmodells ist.</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CUSTOM_MODEL_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugewiesen wird, weil er Teil eines benutzerdefinierten Modells ist.</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AMOUNT</p>
      </td>
      <td>
        <p>number(38,8)</p>
      </td>
      <td>
        <p>Betrag der Möglichkeit aus dem Quellsystem.</p>
      </td>
      <td>
        <p>42000,00000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_WON</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Opportunity auf eine Phase verschoben wurde, die als "Gewinner" klassifiziert ist.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CLOSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Opportunity zu einer Phase verschoben wurde, die als geschlossen klassifiziert ist.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Opportunity-ID aus dem Quellsystem.</p>
      </td>
      <td>
        <p>0060Z00000nFEfEQAW</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_CREATED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Erstellung der Opportunity, aus dem Quellsystem.</p>
      </td>
      <td>
        <p>2018-08-31 15:45:47.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_CLOSE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Abschlussdatum der Opportunity, aus dem Quellsystem.</p>
      </td>
      <td>
        <p>2018-12-31 07:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_CREATED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Erstellung des Kontaktdatensatzes, aus dem Quellsystem.</p>
      </td>
      <td>2017-04-28 00:21:52.000</td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Kontakt-ID aus dem Quellsystem.</p>
      </td>
      <td>
        <p>0030Z00003ORVJmQAP</p>
      </td>
    </tr>
    <tr>
      <td>EMAIL</td>
      <td>varchar</td>
      <td>E-Mail-Adresse für den Datensatz.</td>
      <td>personb@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>LEAD_CREATED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Erstellung des Lead-Datensatzes aus dem Quellsystem.</p>
      </td>
      <td>
        <p>2017-04-28 00:21:52.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Leads aus dem Quellsystem.</p>
      </td>
      <td>
        <p>00Q3100001GMPIsEAP</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Anzeige summiert werden können. (d. h. um die Anzeigenkosten zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_ADVERTISER</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die vom Advertiser zusammengefasst werden können. (d. h. um die Kosten des Advertisers zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD_ACCOUNT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Konto summiert werden können. (d. h. um die Kontokosten zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD_GROUP</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die von Anzeigengruppen zusammengefasst werden können. (d. h. um die Anzeigengruppenkosten zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CAMPAIGN</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die von Campaign zusammengefasst werden können. (d. h. um die Kampagnenkosten zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CHANNEL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Kanal summiert werden können. (d. h. um die Kanalkosten zu erhalten, summieren Sie die Zeilen, für die diese Spalte "true" ist.)</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CREATIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die von Creative zusammengefasst werden können. (d. h. um die Creative-Kosten zu erhalten, summieren Sie die Zeilen, für die diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_KEYWORD</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Keyword summiert werden können. (d. h. um die Suchbegriffkosten zu erhalten, summieren Sie die Zeilen, bei denen diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_PLACEMENT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Platzierung summiert werden können. (d. h. um die Platzierungskosten zu erhalten, summieren Sie die Zeilen, für die diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_SITE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile Kosten enthält, die nach Site summiert werden können. (d. h. um die Site-Kosten zu erhalten, summieren Sie die Zeilen, für die diese Spalte "true" ist.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Datensatz gelöscht wurde oder nicht, wird als Audit-Protokoll verwendet.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>number(38,0)</td>
      <td>ID-Wert der Währung für den Datensatz.</td>
      <td>-3253183181619994799</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_FORM_SUBMITS {#biz-forms-submits}

Übermittlungen erfasster Formulare.

<table>
  <tbody>
    <tr>
      <th>
        Spalte
      </th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Formularübermittlung.</p>
      </td>
      <td>
        <p>2018-08-06:01-35-21-927280.9bc63c34482f4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete Cookie-ID zum Zeitpunkt der Protokollierung der Formularübermittlung.</p>
      </td>
      <td>
        <p>9bc63c34482f4de8c2e3b9d8d9f0df56</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Cookie-ID der zugehörigen Besucher-ID. Wenn der Datensatz als is_duplicated = true markiert ist, ist dieses Feld null.</p>
      </td>
      <td>
        <p>v_9bc63c34482f4de8c2e3b9d8f9f0df56</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete Sitzungs-ID zum Zeitpunkt der Protokollierung der Formularübermittlung. Wenn der Datensatz als is_duplicated = true markiert ist, ist dieses Feld null.</p>
      </td>
      <td>
        <p>2018-08-06:01-35-24-1231230.9bc63c34482f</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Übermittlung des Formulars.</p>
      </td>
      <td>
        <p>2018-08-06 01:35:21.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-08-07 23:09:52.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL, an die das Formular gesendet wurde, ohne Abfrageparameter.</p>
      </td>
      <td>
        <p>https://info.adobe.com/webinar-marketo-measure-impact</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL, an die das Formular gesendet wurde, einschließlich aller Abfrageparameter.</p>
      </td>
      <td>
        <p>https://info.adobe.com/webinar-marketo-measure-impact?utm_source=partner&amp;mkt_tok=eyJpIjoiTnpBeE1EVml PV0UyWlRObSIsInQiOiI3MEFIek04ZVJiWm9renc1Z29RXC9kXC92YkxycFRYclE0MVhOaH Nwdml3YTZBZDdPdXh4Q0RmcnBJWXhwZTF1Z0RrbXlDVmxJNzIwNkhW</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete IP-Adresse zum Zeitpunkt der Übermittlung des Formulars.</p>
      </td>
      <td>
        <p>174127184158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TYPE</p>
      </td>
      <td>varchar</td>
      <td>Gibt den Ereignistyp an.</td>
      <td>
        <p>FormSubmit</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_AGENT_STRING</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Gerät und Browser, die zum Zeitpunkt der Formularübermittlung aufgezeichnet wurden.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (Macintosh) Intel Mac OS X 10_13_6) AppleWebKit/605.1.15 (KHTML, wie Gecko) Version/11.1.2 Safari/605.1.15</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>varchar</td>
      <td>Gibt die Reihenfolge an, in der die Seitenansicht in der Sitzung stattgefunden hat.</td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>varchar</td>
      <td>Wird für interne Rechnungsprüfung und Verarbeitung verwendet.</td>
      <td>
        <p>20042b6b7af44512b43f6244d86faf4c</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Gibt an, ob der Datensatz als Duplikat betrachtet wird.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Wird für die interne Verarbeitung verwendet.</td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail-Adresse, die im Formular angegeben ist, wie aus dem JavaScript erfasst.</p>
      </td>
      <td>
        <p>personc@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_TYPE</p>
      </td>
      <td>varchar</td>
      <td>Gibt den Typ des gesendeten Formulars an.</td>
      <td>
        <p>Chat</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Gibt die Methode an, bei der das Formular erkannt wurde, z. B. onSubmit oder AjaxIntercept</p>
      </td>
      <td>
        <p>onSubmit</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_IDENTIFIER</p>
      </td>
      <td>varchar</td>
      <td>ID-Wert für das Formular.</td>
      <td>
        <p>-956012665</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>-6255315750913680000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Fremdschlüssel in der URL-Tabelle.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_IMPRESSIONS {#biz-impressions}

Impressionen ausgelöst und aufgezeichnet. Diese Tabelle erfordert eine DoubleClick-Verbindung und die Einstellung von &quot;View Through&quot; auf True.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Impression.</p>
      </td>
      <td>
        <p>6acd7b43290490fe5c53eed31281d09a|2020-05-18:22:20:59|0000|0|2869369052</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete Cookie-ID zum Zeitpunkt der Impression.</p>
      </td>
      <td>08c1063cb0a64349ad0d2d862f5cc700</td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Cookie-ID der zugehörigen Besucher-ID.</p>
      </td>
      <td>v_08c1063cb0a64349ad0d2d862f5cc700</td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete Sitzungs-ID zum Zeitpunkt der Protokollierung der Impression.</p>
      </td>
      <td>2018-08-06:01-35-24-1231230.9bc63c34482f</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem die Impression bereitgestellt wurde.</p>
      </td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL, an die die Impression gesendet wurde, ohne Abfrageparameter.</p>
      </td>
      <td>https://info.adobe.com/webinar-marketo-measure-impact</td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL, an die die Impression gesendet wurde, einschließlich aller Abfrageparameter.</p>
      </td>
      <td>https://info.adobe.com/webinar-marketo-measure-impact?utm_source=partner&amp;mkt_tok=eyJpIjoiTnpBeE1EVml PV0UyWlRObSIsInQiOiI3MEFIek04ZVJiWm9renc1Z29RXC9kXC92YkxycFRYclE0MVhOaH Nwdml3YTZBZDdPdXh4Q0RmcnBJWXhwZTF1Z0RrbXlDVmxJNzIwNkhW</td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete IP-Adresse zum Zeitpunkt der Impression.</p>
      </td>
      <td>174127184158</td>
    </tr>
    <tr>
      <td>
        <p>TYPE</p>
      </td>
      <td>varchar</td>
      <td>Gibt den Ereignistyp an.</td>
      <td>Impression</td>
    </tr>
    <tr>
      <td>
        <p>USER_AGENT_STRING</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Gerät und Browser, die zum Zeitpunkt der Formularübermittlung aufgezeichnet wurden.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (Macintosh) Intel Mac OS X 10_13_6) AppleWebKit/605.1.15 (KHTML, wie Gecko) Version/11.1.2 Safari/605.1.15</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>varchar</td>
      <td>Gibt die Reihenfolge an, in der die Seitenansicht in der Sitzung stattgefunden hat.</td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>varchar</td>
      <td>Wird für interne Rechnungsprüfung und Verarbeitung verwendet.</td>
      <td>
        <p>20042b6b7af44512b43f6244d86faf4c</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Gibt an, ob der Datensatz als Duplikat betrachtet wird.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Wird für die interne Verarbeitung verwendet.</td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In der Regel die externe Landingpage unmittelbar vor dem Besuch des Benutzers auf der Website. Im CRM als "Referrer-Seite" bezeichnet.</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE-RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In der Regel die externe Landingpage unmittelbar vor dem Besuch des Benutzers auf der Website. Eine Raw-Referrer-Seite kann Abfrageparameter in der URL enthalten. Im CRM als "Referrer Page - Raw" bezeichnet.</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>CITY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgelöste Stadt aus der IP-Adresse.</p>
      </td>
      <td>
        <p>Seattle</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der aufgelöste Bereich von der IP-Adresse.</p>
      </td>
      <td>
        <p>Washington</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COUNTRY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das aufgelöste Land aus der IP-Adresse.</p>
      </td>
      <td>
        <p>Vereinigte Staaten</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ISP_NAME</p>
      </td>
      <td>varchar</td>
      <td>Wird als null erwartet, da das Feld veraltet ist.</td>
      <td>NULL</td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Anzeigenplattform, über die [!DNL Marketo Measure] auflösen konnte, in der Regel einer unserer Integrationspartner.</p>
      </td>
      <td>Google</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Anzeigenkontos, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>aw.6601259029</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenkontos, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Advertisers aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Advertisers aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>Marketing-Analyse für Marktmessungen</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Site aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Site aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Platzierung aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Platzierung aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>Hindernis</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>aw.6601259029.317738075</td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>Marketing-Zuordnung</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da keine Anzeigengruppe in der Doppelklick-Hierarchie für Impressionen vorhanden ist</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da keine Anzeigengruppe in der Doppelklick-Hierarchie für Impressionen vorhanden ist</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeige aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für DoubleClick Campaign Manager und Facebook (Anzeige).</p>
      </td>
      <td>
        <p>68035923</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeige aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für DoubleClick Campaign Manager und Facebook (Anzeige).</p>
      </td>
      <td>
        <p>centurylink_banner_98121</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen kein Creative-Element gibt.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen kein Creative-Element gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen kein Creative-Element gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen kein Creative-Element gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen kein Creative-Element gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen kein Creative-Element gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen keinen Suchbegriff gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen keinen Suchbegriff gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen keinen Suchbegriff gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus der erkannte Browser, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Chrome</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Version des Browsers, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Plattform, auf der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Version der Plattform, auf der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur BIZ_FACTS-Ansicht.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_KEY</p>
      </td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_KEYWORDS {#biz-keywords}

Aus einem beliebigen verbundenen Anzeigenkonto importierte Suchbegriffe.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für den Suchbegriff.</p>
      </td>
      <td>
        <p>ba.3284209.132630532.3646889365.39464932147</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>Die Keyword-ID aus dem Quellsystem.</td>
      <td>
        <p>39464932147</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Anzeigenkonto, von dem aus der Suchbegriff importiert wurde.</p>
      </td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenkontos, von dem aus der Suchbegriff importiert wurde.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen keinen Suchbegriff gibt.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in der Doppelklick-Hierarchie für Impressionen keinen Suchbegriff gibt.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeigengruppe für den Suchbegriff.</p>
      </td>
      <td>
        <p>ba.3284209.132630532.3646889365</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeigengruppe für den Suchbegriff.</p>
      </td>
      <td>
        <p>Umsatzzuordnung - B2B</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne für den Suchbegriff.</p>
      </td>
      <td>
        <p>ba.3284209.132630532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne für den Suchbegriff.</p>
      </td>
      <td>
        <p>Umsatzzuordnung</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Suchbegriff im Quellsystem noch aktiv ist.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob das Keyword im Quellsystem gelöscht wurde.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>2018-08-02 06:37:29.000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Datensatz zum ersten Mal aus dem Quellsystem importiert wurde.</p>
      </td>
      <td>
        <p>2018-08-02 06:37:29.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Suchbegriffs aus dem Quellsystem.</p>
      </td>
      <td>
        <p>[Umsatzzuordnung b2b]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Suchbegriff für das [!DNL Marketo Measure]-Tagging aktualisiert werden muss.</p>
        <p>(Diagnostisches Feld, für die interne Verarbeitung verwendet.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisches Feld für die interne Verarbeitung.</td>
      <td>
        <p>ba.3284209.132630532.3646889365</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "Keyword".</p>
      </td>
      <td>
        <p>Keyword</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenanbieters für den Suchbegriff.</p>
      </td>
      <td>
        <p>BingAds</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die URL für die Landingpage.</p>
        <p>(Diagnostisches Feld für die interne Verarbeitung.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Vorheriger Wert für URL_CURRENT.</p>
        <p>(Diagnostisches Feld für die interne Verarbeitung.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_REQUESTED</td>
      <td>varchar</td>
      <td>
        <p>Die URL für die Landingpage mit [!DNL Marketo Measure] Parameter.</p>
        <p>(Diagnostisches Feld für die interne Verarbeitung.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_UPGRADED_URL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Diagnostisches Feld für interne Verarbeitung.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WORD</p>
      </td>
      <td>varchar</td>
      <td>Die vom Benutzer eingegebene Suchphase.</td>
      <td>
        <p>Umsatzzuordnung b2b</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Art der Übereinstimmung, die zwischen dem Suchbegriff und dem Keyword gefunden wurde.</p>
      </td>
      <td>
        <p>Exakt</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>Wird für die interne Diagnose verwendet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLIED</p>
      </td>
      <td>varchar</td>
      <td>Die URL-Tracking-Vorlage, die [!DNL Marketo Measure] zum Suchbegriff hinzugefügt hat.</td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>-2712935512233520000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_LANDING_PAGES {#biz-landing-pages}

Landing-Pages, die aus einem verbundenen Anzeigenkonto importiert wurden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Landingpage.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>ID für das Anzeigenkonto, von dem die Landingpage importiert wurde.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>Name des Anzeigenkontos, von dem die Landingpage importiert wurde.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des Advertisers für die Landingpage, insbesondere für Doubleclick.</p>
      </td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Advertisers für die Landingpage, insbesondere für Doubleclick.</p>
      </td>
      <td>Marketing Analytics</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>ID der Anzeigengruppe für die Landingpage.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>Name der Anzeigengruppe für die Landingpage.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>Kennung der Kampagne für die Landingpage.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>Name der Kampagne für die Landingpage.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Datum der letzten Änderung der Zeile.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_LEADS {#biz-leads}

Aus dem Quellsystem importierte Leads.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Die ID des Leads aus dem Quellsystem.</p>
      </td>
      <td>
        <p>00Q0Z00001MZcj8UAD</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Lead-Datensatzes im Quellsystem.</p>
      </td>
      <td>
        <p>2018-08-27 21:52:10.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Erstellung des Lead-Datensatzes aus dem Quellsystem.</p>
      </td>
      <td>2018-08-27 21:52:10.000</td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail-Adresse des Leads aus dem Quellsystem.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>WEB_SITE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Für den Lead eingegebene Website aus dem Quellsystem, die für die Zuordnung von Lead2Account verwendet wird.</p>
      </td>
      <td>
        <p>adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COMPANY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Firmenname, der für den Lead aus dem Quellsystem eingegeben wurde und für die Zuordnung von Lead2Account verwendet wird.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Quelle, in der der Lead erstellt wurde.</p>
      </td>
      <td>
        <p>Werbung</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CONVERTED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Lead in einen Kontakt umgewandelt wurde.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_OPPORTUNITY_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der zugehörigen Opportunity nach der Konvertierung des Leads.</p>
      </td>
      <td>
        <p>0013100001b44aGAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Lead in einen Kontakt umgewandelt wurde.</p>
      </td>
      <td>
        <p>2018-08-27 07:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_CONTACT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des entsprechenden Kontakts nach der Konvertierung des Leads.</p>
      </td>
      <td>
        <p>0030Z00003Oyp25QAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNTID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des zugeordneten Kontos. Voraussetzungen: Aktivieren von ABM</p>
      </td>
      <td>
        <p>0010Z0000236F9GQAU</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Aktuelle Phase des Leads, die als benutzerdefinierte Phase erkannt wird und in der [!DNL Marketo Measure]-Anwendung erstellt werden kann.</p>
      </td>
      <td>
        <p>Demo geplant</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Alle vorherigen Phasen für den Lead, die als benutzerdefinierte Phasen erkannt werden, die in der [!DNL Marketo Measure]-Anwendung erstellt werden können.</p>
      </td>
      <td>
        <p>MQL</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>number(38,19)</p>
      </td>
      <td>
        <p>Diese Funktion ist veraltet. Verwenden Sie diese Spalte nicht.</p>
      </td>
      <td>
        <p>Nicht zutreffend</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SCORE_MODEL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>(veraltet)</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SCORE_RESULTS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>(veraltet)</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die [!DNL Marketo Measure]-Cookie-ID, die zum Ausfüllen von einem Integrationspartner verwendet wird, um ein Offline-Ereignis einer Websitzung zuzuordnen. Anforderung: Anrufverfolgung aktivieren: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Datensatz im Quellsystem gelöscht wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>3263982503087870000</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Benutzerdefinierte Eigenschaften im JSON-Format, die [!DNL Marketo Measure] aus dem Quellsystem importiert hat.</td>
      <td>{"Lead_Type__c":"Sales Created", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>IS_DUPLICATE</td>
      <td>boolean</td>
      <td>Dient zum Deduplizieren von Datensätzen, wenn sowohl eine CRM- als auch eine Marketo-Integration eingerichtet sind. Bei Duplikaten wird Marketo Lead als "true"markiert.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>SOURCE_SYSTEM</td>
      <td>varchar</td>
      <td>Gibt an, ob der Datensatz aus einem CRM-System oder einer Marketo-Integration stammt.</td>
      <td>Crm</td>
    </tr>
    <tr>
      <td>OTHER_SYSTEM_ID</td>
      <td>varchar</td>
      <td>Ordnet eine Person aus einer Marketo-Integration einem Lead aus einer CRM-Integration zu. Wenn sowohl eine CRM- als auch eine Marketo-Integration vorhanden sind, ist der Wert die entsprechende ID.</td>
      <td>1234</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_LEAD_STAGE_TRANSITIONS {#biz-lead-stage-transitions}

Phasen-Transitionen für Leads oder Kontakte.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Transition.</p>
      </td>
      <td>
        <p>ST_0030Z00003FhkRXQAZ__FT-1_TP2_Person_0030Z00003FhkRXQAZ_2018-08-27:17-05-45-94 74800.0d5c18c29d7b</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die angegebene E-Mail-Adresse für den zugehörigen Lead/Kontakt.</p>
      </td>
      <td>
        <p>persone@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung für den mit der Transition verknüpften Lead.</p>
      </td>
      <td>
        <p>00Q3100001Fx6AlEAJ</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Kennung des der Transition zugeordneten Kontakts.</p>
      </td>
      <td>
        <p>0033100003Aq9grAAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung für den mit der Transition verbundenen Buyer Touchpoint.</p>
      </td>
      <td>
        <p>TP2_Person_00Q3100001Fx6AlEAJ_2018-08-28:14-41-06-1674260.d00ceb09fbd3</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRANSITION_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Datensatz in die Phase übergegangen ist.</p>
      </td>
      <td>
        <p>2018-08-27 16:05:34.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID-Wert der Phase für die Transition.</p>
      </td>
      <td>
        <p>_bizible_FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Phase für die Transition.</p>
      </td>
      <td>
        <p>FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>RANK</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Der numerische Rang des Stagings, entsprechend der Reihenfolge in den Einstellungen für die Phasen-Zuordnung in [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>5</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Wird in der internen Verarbeitung für die Indizierung und Sortierung von Boomerang-Phasen verwendet.</p>
      </td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>Wird in der internen Verarbeitung für die Indizierung und Sortierung von Boomerang-Phasen verwendet.</td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PENDING</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Touchpoint als ausstehend und noch nicht geschlossen gilt. Dies wird nur für Kunden mit vollständigem Pfadattributionsmodell angezeigt.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_NON_TRANSITIONAL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile mit einer Meilensteinschritte-Transition verknüpft ist. Wenn es z. B. 3 Phasen/Einträge (FT, LC, MQL) und 4 Touchpoints gibt, wird der 1 Touchpoint ohne Phase als "nicht vorübergehend" betrachtet, sodass der Wert "true" entspricht.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PREVIOUS_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Übergangsdatum für die vorherige Phase, entsprechend der Rangliste der Phasen.</p>
      </td>
      <td>
        <p>2017-11-28 21:26:44.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEXT_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Übergangsdatum für die nächste Phase, entsprechend der Rangliste der Phasen.</p>
      </td>
      <td>
        <p>2017-12-11 22:39:17.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-08-28 15:31:10.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Übergangsdatensatz als gelöscht betrachtet wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_OPPORTUNITIES {#biz-opportunities}

Aus dem Quellsystem importierte Möglichkeiten.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Die Opportunity ID aus dem Quellsystem.</p>
      </td>
      <td>
        <p>0060Z00000o89I4QAI</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Datum der letzten Änderung der Option aus dem Quellsystem.</p>
      </td>
      <td>2017-11-28 21:26:44.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Erstellungsdatum der Möglichkeit aus dem Quellsystem.</p>
      </td>
      <td>2017-11-28 21:26:44.000</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des zugehörigen Kontos.</p>
      </td>
      <td>
        <p>001i000000qbyeoAAA</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name der Opportunity aus dem Quellsystem.</p>
      </td>
      <td>
        <p>Marketo Measurement Renewal</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_WON</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Opportunity zu einer als erfolgreich betrachteten Phase verschoben wurde.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Opportunity zu einer Phase verschoben wurde, die als geschlossen gilt.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLOSE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Voraussichtliches oder tatsächliches Schließdatum der Opportunity, vom Quellsystem aus.</p>
      </td>
      <td>
        <p>2019-08-28 07:00:00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_CUSTOM_MODEL_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>(veraltet)</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AMOUNT</p>
      </td>
      <td>
        <p>number(38,8)</p>
      </td>
      <td>
        <p>Gesamtbetrag, der von der Möglichkeit erwartet oder geschlossen wird, vom Quellsystem.</p>
      </td>
      <td>
        <p>8988,00000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_FROM_LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die ID des zugehörigen Leads, der in diese Opportunity konvertiert wurde.</p>
        <p>Beachten Sie, dass dieses Feld nicht festgelegt ist und in Snowflake für alle Kunden null zurückgibt.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_FROM_LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die E-Mail des zugehörigen Leads, der in diese Opportunity konvertiert wurde.</p>
        <p>Beachten Sie, dass dieses Feld nicht festgelegt ist und in Snowflake für alle Kunden null zurückgibt.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PRIMARY_CONTACT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wenn die primäre Kontaktrolle verwendet wird, wird die ID des entsprechenden Kontakts als primäre Kontaktrolle aufgelistet.</p>
      </td>
      <td>
        <p>00331000038uGfhAAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PRIMARY_CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wenn die primäre Kontaktrolle verwendet wird, wird die E-Mail des entsprechenden Kontakts als primäre Kontaktrolle aufgelistet.</p>
      </td>
      <td>
        <p>personb@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>number(38,19)</p>
      </td>
      <td>
        <p>Diese Funktion ist veraltet. Verwenden Sie diese Spalte nicht.</p>
      </td>
      <td>
        <p>Nicht zutreffend</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Aktuelle Phase der Opportunity, wie in der [!DNL Marketo Measure]-Anwendung definiert.</p>
      </td>
      <td>
        <p>DM Demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Eine Zeichenfolge aller Phasen, die die Opportunity zuvor durchlaufen hat, wie in der [!DNL Marketo Measure]-Anwendung definiert.</p>
      </td>
      <td>
        <p>Qualifizierte Erkennung, geplante Demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Datensatz im Quellsystem gelöscht wird.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>4609512587744160000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENCY_ISO_CODE</td>
      <td>varchar</td>
      <td>ISO-Code für die Währung, der aus dem Quellsystem importiert wird.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>number(38,0)</td>
      <td>ID-Wert der Währung für den Datensatz.</td>
      <td>4609512587744160000</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Benutzerdefinierte Eigenschaften im JSON-Format, die [!DNL Marketo Measure] aus dem Quellsystem importiert hat.</td>
      <td>{"Opportunity_Location__c":"Seattle", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td><b>*</b> OPPORTUNITY_TYPE</td>
      <td>varchar</td>
      <td>Art der Möglichkeit, wie z. B. Neues Geschäft, Verlängerung usw.</td>
      <td>Verlängerung, potenzielle Kundin oder potenzieller Kunde</td>
    </tr>
  </tbody>
</table>
<p>
<b>*</b> <i>Nur verfügbar in Marketo Measure Ultimate</i>
<p>

### BIZ_OPP_STAGE_TRANSITIONS {#biz-opp-stage-transitions}

Phasen-Transitionen für Opportunitys.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Transition.</p>
      </td>
      <td>
        <p>ST_0060Z00000nEgjlQAC_0030Z00003IjojKQAR_Demo Scheduled-1_BAT2_0060Z00000nEgjlQAC_0030Z00003IjojKQAR_2018-06-01:19-51-38-1685390.beec556e7757</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Konto, das mit der Opportunity verknüpft ist.</p>
      </td>
      <td>
        <p>0013100001b44nTAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung für die mit der Transition verknüpfte Opportunity.</p>
      </td>
      <td>
        <p>0060Z00000nEgjlQAC</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Kennung des der Transition zugeordneten Kontakts.</p>
      </td>
      <td>
        <p>0030Z00003IjojKQAR</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die angegebene E-Mail-Adresse für den entsprechenden Kontakt.</p>
      </td>
      <td>
        <p>persone@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung für den mit der Transition verbundenen Buyer Attribution Touchpoint.</p>
      </td>
      <td>
        <p>BAT2_0060Z00000nEgjlQAC_0030Z00003IjojKQAR_2018-06-01:19-51-38-1685390.bef ec556e7757</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRANSITION_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Datensatz in die Phase übergegangen ist.</p>
      </td>
      <td>
        <p>2018-05-26 07:29:43.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Phase für die Transition.</p>
      </td>
      <td>
        <p>Demo geplant</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID-Wert der Phase für die Transition.</p>
      </td>
      <td>
        <p>_bizible_FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>RANK</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Der numerische Rang der Phase, entsprechend der Reihenfolge in den Einstellungen für die Phasen-Zuordnung in [!DNL Marketo Measure].</p>
      </td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Wird in der internen Verarbeitung für die Indizierung und Sortierung von Boomerang-Phasen verwendet.</p>
      </td>
      <td>1</td>
    </tr>
    <tr>
      <td>
        <p>LAST_INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Wird in der internen Verarbeitung für die Indizierung und Sortierung von Boomerang-Phasen verwendet.</p>
      </td>
      <td>1</td>
    </tr>
    <tr>
      <td>
        <p>IS_PENDING</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Touchpoint als ausstehend und noch nicht geschlossen gilt. Dies wird nur für Kunden mit vollständigem Pfadattributionsmodell angezeigt.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_NON_TRANSITIONAL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Zeile mit einer Meilensteinschritte-Transition verknüpft ist. Wenn es z. B. 3 Phasen/Einträge (FT, LC, MQL) und 4 Touchpoints gibt, wird der 1 Touchpoint ohne Phase als "nicht vorübergehend" betrachtet, sodass der Wert "true" entspricht.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PREVIOUS_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Übergangsdatum für die vorherige Phase, entsprechend der Rangliste der Phasen.</p>
      </td>
      <td>
        <p>2015-07-16 17:41:49.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEXT_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Übergangsdatum für die nächste Phase, entsprechend der Rangliste der Phasen.</p>
      </td>
      <td>
        <p>2018-08-27 19:40:52.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-08-28 03:53:33.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Übergangsdatensatz als gelöscht betrachtet wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_PAGE_VIEWS {#biz-page-views}

Seitenansichten, die aus Webbesuchen erfasst wurden. Mehrere Seitenansichten können eine einzelne Sitzung bilden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Seitenansicht.</p>
      </td>
      <td>
        <p>2018-08-19:16-49-58-24340.277d79d0167849</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete Cookie-ID zum Zeitpunkt der Protokollierung der Seitenansicht.</p>
      </td>
      <td>
        <p>277d79d01678498fea067c9b631bf6df</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das erste Cookie der zugehörigen Besucher-ID.</p>
      </td>
      <td>
        <p>v_277d79d01678498fea067c9b631bf6df</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Sitzungs-ID korreliert mit der Seitenansicht.</p>
      </td>
      <td>
        <p>2018-08-19:16-49-58-24340.277d79d0167849</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem die Seitenansicht stattgefunden hat.</p>
      </td>
      <td>
        <p>2018-08-19 16:49:58.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-08-19 16:55:37.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL der Seitenansicht ohne Abfrageparameter.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL der Seitenansicht, einschließlich aller Abfrageparameter.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo?hsCtaTracking=207219e9-87b6-4105-8f4b-0a3b62ae1af8%7C48060522-3aeb-4c72-8ce5-fd4b1017f069</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete IP-Adresse zum Zeitpunkt der Übermittlung des Formulars.</p>
      </td>
      <td>
        <p>174127184158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TYPE</p>
      </td>
      <td>varchar</td>
      <td>Gibt den Ereignistyp an.</td>
      <td>
        <p>PageView</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_AGENT_STRING</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Gerät und Browser, die zum Zeitpunkt der Formularübermittlung aufgezeichnet wurden.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (X11; Linux x86_64; rv:52.0) Gecko/20100101 Firefox/52.0</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Gibt die Reihenfolge an, in der die Seitenansicht in der Sitzung stattgefunden hat.</p>
      </td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>varchar</td>
      <td>Wird für interne Rechnungsprüfung und Verarbeitung verwendet.</td>
      <td>
        <p>103532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Gibt an, ob der Datensatz als Duplikat betrachtet wird.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Wird für die interne Verarbeitung verwendet.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL, aus der die Seitenansicht stammt, ohne Abfrageparameter.</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL, von der die Seitenansicht stammt, einschließlich aller Abfrageparameter.</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=Social&amp;utm_campaign=SU%20-%20CMO%20JT&amp;utm_content=CMOs%20Guide&amp;utm_term=lisu05091601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PAGE_TITLE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Titel der Seite.</p>
      </td>
      <td>
        <p>Der CMO-Leitfaden zur B2B-Marketing-Attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail-Adresse, die in einem Formular bereitgestellt wird, wie aus dem JavaScript erfasst.</p>
      </td>
      <td>personc@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>-6255315750913680000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Fremdschlüssel in der URL-Tabelle.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td>Fremdschlüssel in der URL-Tabelle.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>HAS_USER_CONSENT</td>
      <td>boolean</td>
      <td>Gibt an, ob der Benutzer dem Tracking zugestimmt hat. "False" bedeutet, dass die Seitenansicht erfasst wurde, da die Benutzerzustimmung nicht erforderlich ist. "True" bedeutet, dass die Seitenansicht erfasst wurde und der Benutzer seine Zustimmung zur Verfolgung gegeben hat.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_PLACEMENTS {#biz-placements}

Tabelle, die alle Platzierungen speichert, die von allen verbundenen Anzeigenkonten heruntergeladen wurden - ein Objekt aus der Doubleclick-Integration.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Platzierung.</p>
      </td>
      <td>
        <p>ba.3284209.132855866.4556709270.10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>Die Platzierungs-ID aus dem Quellsystem.</td>
      <td>10426699711</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Anzeigenkonto, von dem aus die Platzierung importiert wurde.</p>
      </td>
      <td>fb. 106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name für das Anzeigenkonto, von dem aus die Platzierung importiert wurde.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Advertisers für die Platzierung, insbesondere für Doubleclick.</p>
      </td>
      <td>300184624</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Advertisers für die Platzierung, insbesondere für Doubleclick.</p>
      </td>
      <td>[!DNL Marketo Measure] Analytics</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Platzierung eine Anzeigengruppe gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Platzierung eine Anzeigengruppe gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne für die Platzierung.</p>
      </td>
      <td>ba.3284209.132855866</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne für die Platzierung.</p>
      </td>
      <td>Pipeline-Marketing</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Platzierung im Quellsystem noch aktiv ist.</p>
      </td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Platzierung im Quellsystem gelöscht wurde.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>2018-08-02 06:36:25.000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Datensatz zum ersten Mal aus dem Quellsystem importiert wurde.</p>
      </td>
      <td>2018-08-02 06:36:25.000</td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Platzierung aus dem Quellsystem.</p>
      </td>
      <td>Markt</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Platzierung für das [!DNL Marketo Measure]-Tagging aktualisiert werden muss.</p>
        <p>(Diagnostisches Feld, von interner Verarbeitung verwendet.)</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisches Feld für interne Verarbeitung.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "Platzierung".</p>
      </td>
      <td>Platzierung</td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenanbieters für die Platzierung.</p>
      </td>
      <td>BingAds</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Erstellungsdatum des Datensatzes durch Snowflake</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Änderungsdatum des Datensatzes durch Snowflake</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Löschdatum des Datensatzes durch Snowflake, falls er gelöscht wurde</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SEGMENTS {#biz-segments}

Segmentwerte gemäß der Definition in der [!DNL Marketo Measure]-Anwendung.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für das Segment.</p>
      </td>
      <td>
        <p>Neues Unternehmen</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Segments.</p>
      </td>
      <td>
        <p>Neues Unternehmen</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>1028715376434030000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SEGMENT_NAMES {#biz-segment-names}

Ordnet den Namen des benutzerdefinierten Segments dem Kategoriewert zu. (Dadurch werden die Spaltennamen den Spaltenüberschriften der Kategorien 1 bis 15 zugeordnet, die in den Touchpoint-Tabellen enthalten sind.)

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
      <td>
        <p>CATEGORY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Gibt die Kategorie an, der der Segmentname zugeordnet ist.</p>
      </td>
      <td>
        <p>CategoryOne</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2022-02-28 18:12:35.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEGMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des der Kategorie zugeordneten Segments.</p>
      </td>
      <td>
        <p>1028715376434030000</p>
      </td>
    </tr>
    <tr>
      <td>IS_ACTIVE</td>
      <td>boolean</td>
      <td>Gibt an, ob die Kategorie verwendet wird.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Gibt an, ob der Datensatz gelöscht wird.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SESSIONS {#biz-sessions}

Sitzungen werden über Seitenansichten verarbeitet. Mehrere Seitenansichten können aus einer Sitzung bestehen, und eine einzelne Besucher-ID kann mehreren Sitzungen zugeordnet werden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Sitzung.</p>
      </td>
      <td>
        <p>2016-08-01:14-24-21-9079480.33163948f0a3</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das erste Cookie der zugehörigen Besucher-ID.</p>
      </td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete Cookie-ID der Sitzung.</p>
      </td>
      <td>277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Sitzung.</p>
      </td>
      <td>
        <p>2016-08-01 14:24:21.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MODIFIED DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-09-01 03:49:10.000</p>
      </td>
    </tr>
    <tr>
      <td>IS_FIRST_SESSION</td>
      <td>boolean</td>
      <td>Gibt an, ob dies die erste Sitzung für die Besucher-ID ist.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kanal, der der Sitzung zugeordnet ist, wie durch die Kanaldefinitionen definiert, die im [!DNL Marketo Measure] Anwendung.</p>
      </td>
      <td>
        <p>Paid Search.AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PAGE_TITLE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Web-Seite.</p>
      </td>
      <td>
        <p>Salesforce-Google Analytics | [!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL der ersten Seitenansicht der Sitzung ohne Abfrageparameter.</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL der ersten Seitenansicht der Sitzung, einschließlich aller Abfrageparameter.</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics?_bt=83558988035&amp;_bk=google%20analytics%20salesforce&amp;_bm= p&amp;gclid=CMvd5YTLo84CFUI9gQodd-kLEQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL, aus der die Sitzung stammt, ohne Abfrageparameter.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL, von der die Sitzung stammt, einschließlich aller Abfrageparameter.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der verweisenden Seite.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Wert, den der Benutzer im Browser eingegeben hat, um danach zu suchen, wodurch er schließlich auf die Website gelang.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Google Salesforce</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird verwendet, um die Quelle zu definieren, die zu der Sitzung führte. Dies kann aus der URL von utm_source geparst oder auf einen Anzeigenanbieter festgelegt werden, wenn [!DNL Marketo Measure] eine Anzeige auflösen kann.</p>
      </td>
      <td>
        <p>Google AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_FORM</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Sitzung ein Ausfüllen des Formulars enthielt,</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_CHAT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Sitzung einen Webchat enthielt.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_EMAIL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Sitzung eine E-Mail-Adresse enthielt.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_CRM_ACTIVITY</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Sitzung aus einem CRM-Aktivitätsdatensatz stammt oder nicht.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DEVICE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Browser und das Betriebssystem des Benutzers während der Sitzung.</p>
      </td>
      <td>
        <p>Chrome (65.0), Windows (6.1)</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Anzeigenplattform, über die [!DNL Marketo Measure] auflösen konnte, in der Regel einer unserer Integrationspartner.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Anzeigenkontos, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenkontos, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Advertisers, von dem aus die Anzeige aufgelöst wurde, insbesondere aus der Verbindung mit Doubleclick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Anzeigenkonten einen Advertiser gibt.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Site, von der die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Site, aus der die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Platzierung, von der aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Platzierung, aus der die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>Hindernis</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Kampagne, aus der die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>aw.6601259029.321586235</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne, aus der die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>Webinar zur Planung eines Budgets</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeigengruppe, aus der die Anzeige aufgelöst wurde. Dies gilt nur für Google Adwords.</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeigengruppe, aus der die Anzeige aufgelöst wurde. Dies gilt nur für Google Adwords.</p>
      </td>
      <td>
        <p>Salesforce - Google Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Anzeige, von der aus aufgelöst wurde. Dies gilt für DoubleClick Campaign Manager und Facebook (Anzeige).</p>
      </td>
      <td>aw.6601259029.321586235.23182235435</td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeige, von der aus aufgelöst wurde. Dies gilt für DoubleClick Campaign Manager und Facebook (Anzeige).</p>
      </td>
      <td>Winterangebot - Grün</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Creative-Elements, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435.83558988035</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Creative-Elements, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>GA und Salesforce integrieren</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Zeile des Creative-Elements aus der Suchanzeige, die aus dem Anzeigenkonto abgerufen wurde, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>Integrieren von Salesforce und Analytics in</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die zweite Zeile des Creative-Elements aus der Suchanzeige, die aus dem Anzeigenkonto abgerufen wurde, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>Für Umsatz optimieren. Lernen Sie, wie.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Landingpage, auf die das Durchklicken von der Suchanzeige führt und die aus dem Anzeigenkonto abgerufen wird, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Anzeigename der URL, der in der Suchanzeige angezeigt wird und aus dem Anzeigenkonto abgerufen wird, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>adobe.com/Salesforce-for-GA</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des Suchbegriffs, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435.35934468937</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Suchbegriffs, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>Google Analytics Salesforce</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Art der Übereinstimmung, die zwischen dem Suchbegriff und dem gekauften Keyword gefunden wird.</p>
      </td>
      <td>
        <p>Satz</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird über die URL von utm_campaign analysiert.</p>
      </td>
      <td>
        <p>SU - ABC-Konten - Paid Media-Fähigkeiten</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird über die URL von utm_source analysiert.</p>
      </td>
      <td>
        <p>linkedin</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird über die URL von utm_medium analysiert.</p>
      </td>
      <td>
        <p>Social</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TERM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird aus der URL von utm_term analysiert.</p>
      </td>
      <td>
        <p>lisu07261601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTENT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird über die URL von utm_content analysiert.</p>
      </td>
      <td>
        <p>AdWords-Benchmark-Bericht 2016</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CITY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgelöste Stadt aus der IP-Adresse.</p>
      </td>
      <td>Vancouver</td>
    </tr>
    <tr>
      <td>
        <p>REGION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der aufgelöste Bereich von der IP-Adresse.</p>
      </td>
      <td>Britisch Kolumbien</td>
    </tr>
    <tr>
      <td>
        <p>COUNTRY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das aufgelöste Land aus der IP-Adresse.</p>
      </td>
      <td>Kanada</td>
    </tr>
    <tr>
      <td>
        <p>ISP_NAME</p>
      </td>
      <td>varchar</td>
      <td>Wird als null erwartet, da das Feld veraltet ist.</td>
      <td>
        <p>NULL</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die aufgezeichnete IP-Adresse zum Zeitpunkt der Sitzung.</p>
      </td>
      <td>
        <p>174127184158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Bestimmt, ob diese Sitzung mit einer anderen zusammengeführt wurde und gelöscht werden soll.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SITES {#biz-sites}

Sites, die aus einem verbundenen Anzeigenkonto importiert wurden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für die Site.</p>
      </td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>Die Site-ID aus dem Quellsystem.</td>
      <td>39464932147</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Anzeigenkonto, von dem aus die Site importiert wurde.</p>
      </td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenkontos, von dem aus die Site importiert wurde.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die ID des Advertisers für die Site, insbesondere für Doubleclick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name des Advertisers für die Site, insbesondere für Doubleclick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Site eine Anzeigengruppe gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird als null erwartet, da es in keiner Anzeigen-Hierarchie oberhalb der Site eine Anzeigengruppe gibt.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne für die Site.</p>
      </td>
      <td>
        <p>ba.3284209.132630532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne für die Site.</p>
      </td>
      <td>Revue-Zuordnung</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Site im Quellsystem noch aktiv ist.</p>
      </td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Site im Quellsystem gelöscht wurde.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>2018-08-02 06:37:29.000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Datensatz zum ersten Mal aus dem Quellsystem importiert wurde.</p>
      </td>
      <td>2018-08-02 06:37:29.000</td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Site, aus dem Quellsystem.</p>
      </td>
      <td>Umsatz</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob die Site für das [!DNL Marketo Measure]-Tagging aktualisiert werden muss.</p>
        <p>(Diagnostisches Feld, für die interne Verarbeitung verwendet.)</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisches Feld für die interne Verarbeitung.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "Site".</p>
      </td>
      <td>Seite</td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenanbieters für die Site.</p>
      </td>
      <td>AdWords</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SITE_LINKS {#biz-site-links}

Sites-Links von einem beliebigen verbundenen Anzeigenkonto aus.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für den Site-Link</p>
      </td>
      <td>
        <p>aw.6601259029.285077795.1654234342</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td>
        <p>1654234342</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Kennung des verbundenen Anzeigenkontos für den Site-Link</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name des verbundenen Anzeigenkontos für den Site-Link</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die ID des Advertisers für den Site-Link, insbesondere für Doubleclick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name des Advertisers für den Site-Link, insbesondere für Doubleclick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die ID der Anzeigengruppe für den Site-Link</p>
      </td>
      <td>aw.6601259029.208548635.16750166675</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name der Anzeigengruppe für den Site-Link</p>
      </td>
      <td>Marke - Core</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Kennung der Kampagne für den Site-Link</p>
      </td>
      <td>
        <p>aw.6601259029.285077795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name der Kampagne für den Site-Link</p>
      </td>
      <td>
        <p>Marke</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Site-Link im Anzeigenkonto noch aktiv ist</p>
      </td>
      <td>
        <p>TRUE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Site-Link im Anzeigenkonto gelöscht wurde</p>
      </td>
      <td>
        <p>FALSE</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Datum der letzten Änderung der Zeile</p>
      </td>
      <td>
        <p>2018-08-02 06:36:50.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Das Datum, an dem der Site-Link zum ersten Mal heruntergeladen wurde von [!DNL Marketo Measure]</p>
      </td>
      <td>
        <p>2018-08-02 06:36:50.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name des Site-Links</p>
      </td>
      <td>Link A</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Site-Link aktualisiert werden muss, um das Marketo Measure-Tagging zu erhalten</p>
      </td>
      <td>
        <p>FALSE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td>
        <p>aw.6601259029.285077795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das Hauptobjekt oder die Entität für diese Tabelle. In diesem Fall "SiteLink"</p>
      </td>
      <td>
        <p>SiteLink</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Name des Anzeigen-Anbieters für den Site-Link</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die URL für die Landingpage.</p>
        <p>(Diagnostisches Feld für die interne Verarbeitung.)</p>
      </td>
      <td>
        <p>http://adobe.com/b2b-marketing-attribution?_bt =</p>
        <p>{creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Vorheriger Wert für URL_CURRENT.</p>
        <p>(Diagnostisches Feld für die interne Verarbeitung.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die URL wird mit [!DNL Marketo Measure] Parameter.</p>
        <p>(Diagnostisches Feld für die interne Verarbeitung.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Erstellungsdatum des Datensatzes durch Snowflake</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Änderungsdatum des Datensatzes durch Snowflake</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Löschdatum des Datensatzes durch Snowflake, falls er gelöscht wurde</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_STAGE_DEFINITIONS {#biz-stage-definitions}

Liste der Schritte, wie sie importiert oder in der [!DNL Marketo Measure]-Anwendung definiert wurden.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für den Schritt.</p>
      </td>
      <td>
        <p>01J3100000QE753EAD</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-08-22 17:27:27.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Schritts.</p>
      </td>
      <td>
        <p>Verbal</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_INACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Gibt an, ob der Schritt als inaktiv betrachtet wird.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IN_CUSTOM_MODEL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Schritt für die Verfolgung im benutzerdefinierten Modell ausgewählt ist.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_BOOMERANG</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Schritt zum Nachverfolgen als Boomerang-Schritt ausgewählt ist.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_TRANSITION_TRACKING</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Gibt an, ob der Schritt zum Nachverfolgen von Transitionen ausgewählt ist.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Status des Schritts, wie in der Staging-Zuordnung der [!DNL Marketo Measure]-App definiert.</p>
      </td>
      <td>
        <p>Wurde geöffnet</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FROM_SALESFORCE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Schritt aus einem externen Quellsystem importiert wird.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DEFAULT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Gibt an, ob der Schritt als Standard festgelegt ist.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>RANK</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Der numerische Rang des Schritts, wird zum Sortieren von Schritten in Übergangsreihenfolge verwendet.</p>
      </td>
      <td>
        <p>53</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Schritt gelöscht wurde.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_TOUCHPOINTS {#biz-touchpoints}

Buyer Touchpoints, alle Touchpoints, die mit einem Lead oder Kontakt verknüpft sind. Diese Tabelle ist leer, wenn &quot;Lead-Touchpoints&quot; oder &quot;Kontakt-Touchpoints&quot; deaktiviert sind.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für den Buyer Touchpoint (BT).</p>
      </td>
      <td>
        <p>TP2_Person_00Q0Z000013e2PYUAY_2018-08-27:20-04-40-565690.1ee8567c175a</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-08-29 22:29:30.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>E-Mail-Adresse, die mit dem BT verknüpft ist.</td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>ID für den mit dem BT verknüpften Kontakt.</p>
      </td>
      <td>0030Z00003K5bpKQAR</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das mit BT verknüpfte Konto.</p>
      </td>
      <td>
        <p>0013100001lSLScAAO</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für den mit dem BT verknüpften Lead.</p>
      </td>
      <td>
        <p>00Q0Z000013e2PYUAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>UNIQUE_ID_PERSON</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Datensatz der übergeordneten Person, der sich auf einen Lead oder Kontakt bezieht.</p>
      </td>
      <td>
        <p>Person_00Q0Z000013e2PYUAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für den Benutzer-Touchpoint, der den BT generiert hat.</p>
      </td>
      <td>
        <p>person@adobe.com_2018-08-29:18-14-53-8102030.10df92cbb414</p>
      </td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>ID für den mit BT verknüpften Besucher.</td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum des Touchpoints.</p>
      </td>
      <td>
        <p>2018-08-27 20:04:40.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Aktivitätstyp, Webbesuch, Webformular, Webchat, Telefonaufruf, [CRM]-Kampagne oder [CRM]-Aktivität. Im CRM als "Touchpoint-Typ" bezeichnet.</p>
      </td>
      <td>
        <p>Webformular</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Kanal, in den der Touchpoint fällt, wie in den benutzerdefinierten Kanaldefinitionen innerhalb der Variablen [!DNL Marketo Measure] App. Im CRM als "Marketingkanal - Pfad" bezeichnet.</p>
      </td>
      <td>Social.LinkedIn</td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die erste Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td>ABC</td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die zweite Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td>
        <p>Ja</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY3</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die dritte Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td>
        <p>Andere</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY4</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die 4. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td>
        <p>Partner</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY5</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die 5. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY6</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die 6. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY7</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 7. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY8</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die achte Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY9</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 9. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY10</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 10. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY11</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 11. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY12</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 12. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY13</p>
      </td>
      <td>varchar</td>
      <td>Der Segmentwert für die 13. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY14</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die 14. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORY15</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Segmentwert für die 15. Kategorie, in die der Touchpoint fällt, wie in den Segmentdefinitionen in der [!DNL Marketo Measure]-App definiert. Im CRM als "Segmente" bezeichnet.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus der erkannte Browser, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>Chrome</td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Version des Browsers, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>68</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Plattform, auf der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Windows</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Version der Plattform, auf der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>10_12</td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Landingpage der Sitzung, die zu einem Touchpoint führte. Im CRM als "Landingpage" bezeichnet.</p>
      </td>
      <td>
        <p>https://info.adobe.com/definitive-guide-to-pipeline-marketing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Landingpage der Sitzung, die zu einem Touchpoint führte. Eine Raw-Landingpage enthält alle Abfrageparameter in der URL. Im CRM als "Landingpage - Roh" bezeichnet.</p>
      </td>
      <td>
        <p>https://info.adobe.com/definitive-guide-to-pipeline-marketing?utm_source=linkedin&amp;utm_medium=Social&amp;utm_campaign=SU_COM_Demand_ Skills&amp;utm_content=DGPM&amp;utm_term=lisu03151846&amp;_bl=66452504</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In der Regel die externe Landingpage unmittelbar vor dem Besuch des Benutzers auf der Website. Im CRM als "Referrer-Seite" bezeichnet.</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In der Regel die externe Landingpage unmittelbar vor dem Besuch des Benutzers auf der Website. Eine Raw-Referrer-Seite kann Abfrageparameter in der URL enthalten. Im CRM als "Referrer Page - Raw" bezeichnet.</p>
      </td>
      <td>
        <p>https://www.linkedin.com/feed</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das erste Formular, das in einer Sitzung aufgezeichnet wurde und zu einem Touchpoint führte. Nachfolgende Formularübermittlungen werden nicht in der Touchpoints-Tabelle, sondern in der Tabelle "Form_Submissions" angezeigt. Im CRM als "Formular-URL" bezeichnet.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>FORM_PAGE_RAW</td>
      <td>varchar</td>
      <td>Das erste Formular, das in einer Sitzung aufgezeichnet wurde und zu einem Touchpoint führte. Nachfolgende Formularübermittlungen werden nicht in der Touchpoints-Tabelle, sondern in der Tabelle "Form_Submissions" angezeigt. Eine Formularrohseite kann Abfrageparameter in der URL enthalten. Im CRM als "Formular-URL - Roh" bezeichnet.</td>
      <td>https://info.adobe.com/demo?hsCtaTracking=98adcc2f-afe2-40c4-9d79-40dcc41663ee%7C3cfaa909-39cb-4f5d-93eb-be05de6b0180</td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Übermittlung des Formulars.</p>
      </td>
      <td>
        <p>2017-06-20 01:06:41.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CITY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Stadt, in der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>New York</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Region, in der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>New York</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COUNTRY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus das erkannte Land, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Vereinigte Staaten</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird verwendet, um das Medium zu definieren, das zum Touchpoint führte. Dies kann entweder aus der URL von utm_medium herausgeparst werden. Oder wenn [!DNL Marketo Measure] eine Anzeige auflösen kann, kann es sich um Werte wie "cpc" oder "display" handeln.</p>
      </td>
      <td>
        <p>Social Media</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird verwendet, um die Quelle zu definieren, die zum Touchpoint führte. Dies kann aus der URL utm_source analysiert werden, die im Allgemeinen als "CRM-Kampagne" festgelegt ist, wenn sie aus dem CRM synchronisiert wurde. Wenn [!DNL Marketo Measure] eine Anzeige auflösen kann, kann es sich auch um Werte wie "Google AdWords" oder "Facebook" handeln. Im CRM als "Touchpoint-Quelle" bezeichnet.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Wert, den der Benutzer in den Browser eingegeben hat, um danach zu suchen, wodurch er schließlich auf die Website gelang. Abhängig vom gekauften Suchbegriff stimmt dies möglicherweise nicht mit den von der Paid Search-Plattform erworbenen Suchbegriffen überein.</p>
      </td>
      <td>
        <p>Markeot Measurement Attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Anzeigenplattform, über die [!DNL Marketo Measure] auflösen konnte, in der Regel einer unserer Integrationspartner.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Anzeigenkontos, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>li.502664737</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenkontos, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>MM SC 2016_14605342_3/7-3/31/16</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Advertisers aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Advertisers aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>Marketo Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Site aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Site aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Platzierung aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Platzierung aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>Hindernis</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>li.502664737.138949954</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>SU - COM Accounts - Demand Skills</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeigengruppe aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für Google Adwords.</p>
      </td>
      <td>aw.6601259029.317738075.23105327435</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeigengruppe aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für Google AdWords.</p>
      </td>
      <td>Marketing-Attribution - Allgemein</td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeige aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für DoubleClick Campaign Manager und Facebook (Anzeige).</p>
      </td>
      <td>dc.6114.8882972.25272734.492579576</td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeige aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für DoubleClick Campaign Manager und Facebook (Anzeige).</p>
      </td>
      <td>Budget-Webinar - Seitenleiste</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des Creative-Elements aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>li.502664737.138949954.66452504</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Creative-Elements aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>lisu03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Zeile des Creative-Elements aus der Suchanzeige, die aus dem Anzeigenkonto abgerufen wurde, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>Lead-Generierung ist erfolgt</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die zweite Zeile des Creative-Elements aus der Suchanzeige, die aus dem Anzeigenkonto abgerufen wurde, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>Laden Sie die endgültige Anleitung zum Pipeline-Marketing herunter: https://lnkd.in/e9xYj5M</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Landingpage, auf die das Durchklicken von der Suchanzeige führt und die aus dem Anzeigenkonto abgerufen wird, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>https://image-store.slidesharecdn.com/d29165c0-1e0b-4ffc-a494-d2c77e7cd4a6-large.jpeg</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Anzeigename der URL, der in der Suchanzeige angezeigt wird und aus dem Anzeigenkonto abgerufen wird, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>marektomeasure.com/guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des vom Paid Search-Kauf erworbenen Suchbegriffs, abgerufen aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>__GAId__lisu03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des vom Paid Search-Kauf erworbenen Suchbegriffs, abgerufen aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche)</p>
      </td>
      <td>
        <p>lisu03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Art der Übereinstimmung, die zwischen dem Suchbegriff und dem gekauften Keyword gefunden wird.</p>
      </td>
      <td>
        <p>Broad</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FIRST_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als Erstkontakt der Opportunity-Journey behandelt wird.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_LEAD_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als Touch zur Lead-Erstellung der Opportunity-Journey behandelt wird.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als Touch zur Opportunity-Erstellung der Opportunity-Journey behandelt wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als geschlossene Berührung des Opportunity-Journey behandelt wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>STAGES_TOUCHED</td>
      <td>varchar</td>
      <td>Dieses Feld ist veraltet. Informationen zur Phase finden Sie in den Tabellen Stage_Transitions .</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint während der Sitzung ein Formular ausgefüllt hat.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als erster Impression des Opportunity-Journey behandelt wird</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil es sich um einen Erstkontakt handelt (siehe Is_First_Touch).</p>
      </td>
      <td>
        <p>100</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil es sich um einen Lead-Erstellungskontakt handelt (siehe Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>100</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugewiesen wird, weil er Teil eines U-förmigen Touchings ist (siehe Is_First_Touch und Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>100</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil er Teil eines W-förmigen Touchings ist (siehe Is_First_Touch, Is_Lead_Creation_Touch und Is_Opp_Creation_Touch). Wird als 0 erwartet, da dies ein BT ist.</p>
      </td>
      <td>
        <p>0</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENTAGE</p>
      </td>
      <td>
        <p>number(22,19)</p>
      </td>
      <td>
        <p>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil er Teil eines vollständigen Pfadmodells ist (siehe Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch). Wird als 0 erwartet, da dies ein BT ist.</p>
      </td>
      <td>
        <p>0</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_MODEL_PERCENTAGE</td>
      <td>number(22,19)</td>
      <td>Der berechnete Prozentsatz, der diesem Touchpoint zugeordnet ist, weil er Teil eines benutzerdefinierten Modells ist (siehe Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch). Wird als 0 erwartet, da dies ein BT ist.</p>
      </td>
      <td>0</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint gelöscht wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td>
        <p>Fremdschlüssel zur Biz_Facts-Ansicht.</p>
      </td>
      <td>
        <p>-9004910726709710000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ROW_KEY</p>
      </td>
      <td>
        <p>number(38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_URLS {#biz-urls}

Aggregation von URLs aus Landingpages, Referrer-Seiten und Seitenansichten.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Die vollständige URL.</td>
      <td>https://www.adobe.com/blog/strategic-marketing-plangoals</td>
    </tr>
    <tr>
      <td>SCHEME</td>
      <td>varchar</td>
      <td>Die sichere Kommunikation der Web-Seite über das Netzwerk.</td>
      <td>https</td>
    </tr>
    <tr>
      <td>HOST</td>
      <td>varchar</td>
      <td>Die Domäne der URL mit beliebigen Subdomains.</td>
      <td>www.adobe.com</td>
    </tr>
    <tr>
      <td>PAGE_TITLE</td>
      <td>varchar</td>
      <td>Titel der Seite.</td>
      <td>Der CMO-Leitfaden zur B2B-Marketing-Attribution</td>
    </tr>
    <tr>
      <td>PATH</td>
      <td>varchar</td>
      <td>Der Teil der URL, der auf einen bestimmten Ort auf dem Host verweist.</td>
      <td>/blog/strategic-marketing-plangoals</td>
    </tr>
    <tr>
      <td>PORT</td>
      <td>varchar</td>
      <td>Der Port eines Internet-Hosts, optional in einer URL.</td>
      <td>584</td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>number(38,0)</td>
      <td>Fremdschlüssel zur Biz_Facts-Ansicht.</td>
      <td>5686109553536636820</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_USER_TOUCHPOINTS {#biz-user-touchpoints}

Alle Touchpoints, die aus einem Ereignis erstellt wurden, das mit einer E-Mail verknüpft ist.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Eine eindeutige ID für den Benutzer-Touchpoint.</p>
      </td>
      <td>
        <p>person@adobe.com_2018-01-05:16-47-02-8803320.ddf67c101f58</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2018-09-05 23:30:53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-Mail-Adresse, die mit dem Benutzer-Touchpoint verknüpft ist.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für die Sitzung, die den Benutzer-Touchpoint erstellt hat.</p>
      </td>
      <td>
        <p>2018-01-05:16-47-02-8803320.ddf67c101f58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_MEMBER_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Kampagnenmitglied, das den Benutzer-Touchpoint erstellt hat.</p>
      </td>
      <td>
        <p>00v0Z00001VTgv1QAD</p>
      </td>
    </tr>
    <tr>
      <td>CRM_ACTIVITY_ID</td>
      <td>varchar</td>
      <td>ID für die Aktivität, die den Benutzer-Touchpoint erstellt hat.</td>
      <td>1678625515</td>
    </tr>
    <tr>
      <td>
        <p>CRM_EVENT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für das Ereignis, mit dem der Benutzer-Touchpoint erstellt wurde.</p>
      </td>
      <td>
        <p>00U0Z00000pCZmyUAG</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CRM_TASK_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für die Aufgabe, die den Benutzer-Touchpoint erstellt hat.</p>
      </td>
      <td>
        <p>00T0Z00004Qbd1jUAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IMPRESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID für die Impression, die den Benutzer-Touchpoint erstellt hat.</p>
      </td>
      <td>00T0Z00004Qbd1jUAB</td>
    </tr>
    <tr>
      <td>IS_FIRST_KNOWN_TOUCH</td>
      <td>boolean</td>
      <td>Gibt an, ob dieser Touchpoint als Erstkontakt der Opportunity-Journey behandelt wird.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>Die erste Cookie-ID der zugehörigen Besucher-ID.</td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum, an dem der Benutzer-Touchpoint aufgetreten ist.</p>
      </td>
      <td>
        <p>2018-01-05 16:47:02.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Aktivitätstyp, Webbesuch, Webformular, Webchat, Telefonaufruf, [CRM]-Kampagne oder [CRM]-Aktivität. Im CRM als "Touchpoint-Typ" bezeichnet.</p>
      </td>
      <td>
        <p>Webformular</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Kanal, in den der Touchpoint fällt, wie in den benutzerdefinierten Kanaldefinitionen innerhalb der Variablen [!DNL Marketo Measure] App. Im CRM als "Marketingkanal - Pfad" bezeichnet.</p>
      </td>
      <td>
        <p>Social.LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus der erkannte Browser, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Firefox</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Version des Browsers, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>33</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Plattform, auf der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Version der Plattform, auf der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Landingpage der Sitzung, die zu einem Touchpoint führte. Im CRM als "Landingpage" bezeichnet.</p>
      </td>
      <td>
        <p>https://www.adobe.com/blog/budget-and-planning-maturity-model-b2b-marketing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Landingpage der Sitzung, die zu einem Touchpoint führte. Eine Raw-Landingpage enthält alle Abfrageparameter in der URL. Im CRM als "Landingpage - Roh" bezeichnet.</p>
      </td>
      <td>
        <p>https://www.adobe.com/blog/budget-and-planning-maturity-model-b2b-marketing?utm_source=feedburner&amp;utm_medium=feed&amp;utm_campaign=Feed%3A+ marketo+%maeasure%27s+Pipeline+Marketing+Blog%29</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In der Regel die externe Landingpage unmittelbar vor dem Besuch des Benutzers auf der Website. Im CRM als "Referrer-Seite" bezeichnet.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In der Regel die externe Landingpage unmittelbar vor dem Besuch des Benutzers auf der Website. Eine Raw-Referrer-Seite kann Abfrageparameter in der URL enthalten. Im CRM als "Referrer Page - Raw" bezeichnet.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das erste Formular, das in einer Sitzung aufgezeichnet wurde und zu einem Touchpoint führte. Nachfolgende Formularübermittlungen werden nicht in der Tabelle "Attribution_Touchpoints" angezeigt, sondern in der Tabelle "Form_Submissions". Im CRM als "Formular-URL" bezeichnet.</p>
      </td>
      <td>
        <p>http://info.adobe.com/adwords-for-lead-generation</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Das erste Formular, das in einer Sitzung aufgezeichnet wurde und zu einem Touchpoint führte. Nachfolgende Formularübermittlungen werden nicht in der Tabelle "Attribution_Touchpoints" angezeigt, sondern in der Tabelle "Form_Submissions". Eine Formularrohseite kann Abfrageparameter in der URL enthalten. Im CRM als "Formular-URL - Roh" bezeichnet.</p>
      </td>
      <td>
        <p>http://info.adobe.com/adwords-for-lead-generation?utm_source=linkedin&amp;utm_medium=paid&amp;utm_content=sfskill&amp;utm _campaign=Content%20-%20AdWords%20Guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der Übermittlung des Formulars.</p>
      </td>
      <td>
        <p>2015-06-03 17:49:10.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CITY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Stadt, in der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Oakland</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus die erkannte Region, in der sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Kalifornien</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COUNTRY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Von der JavaScript- und IP-Adresse aus das erkannte Land, in dem sich der Benutzer während der Sitzung befand.</p>
      </td>
      <td>
        <p>Vereinigte Staaten</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird verwendet, um das Medium zu definieren, das zum Touchpoint führte. Dies kann entweder aus der URL von utm_medium herausgeparst werden. Oder wenn [!DNL Marketo Measure] eine Anzeige auflösen kann, kann es sich auch um Werte wie "cpc" oder "display" handeln.</p>
      </td>
      <td>
        <p>bezahlt</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wird verwendet, um die Quelle zu definieren, die zum Touchpoint führte. Dies kann aus der URL utm_source analysiert werden, die im Allgemeinen als "CRM-Kampagne" festgelegt ist, wenn sie aus dem CRM synchronisiert wurde. Wenn [!DNL Marketo Measure] eine Anzeige auflösen kann, kann es sich auch um Werte wie "Google AdWords" oder "Facebook" handeln. Im CRM als "Touchpoint-Quelle" bezeichnet.</p>
      </td>
      <td>
        <p>linkedin</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Wert, den der Benutzer in den Browser eingegeben hat, um danach zu suchen, wodurch er schließlich auf die Website gelang. Abhängig vom gekauften Suchbegriff stimmt dies möglicherweise nicht mit den von der Paid Search-Plattform erworbenen Suchbegriffen überein.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Anzeigenplattform, über die [!DNL Marketo Measure] auflösen konnte, in der Regel einer unserer Integrationspartner.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Anzeigenkontos, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Anzeigenkontos, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Konto</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des Advertisers aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Advertisers aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Site aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Site aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für den Kampagnen-Manager von DoubleClick.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Platzierung aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Platzierung aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für DoubleClick Campaign Manager.</p>
      </td>
      <td>
        <p>Hindernis</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung der Kampagne aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>aw.6601259029.208548635</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Kampagne aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde.</p>
      </td>
      <td>
        <p>Marke</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeigengruppe aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für Google Adwords.</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.16750166675</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeigengruppe aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt nur für Google AdWords.</p>
      </td>
      <td>
        <p>Marke - Core</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID der Anzeige aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für DoubleClick Campaign Manager und Facebook (Anzeige).</p>
      </td>
      <td>dc.6114.8882972.25272734.492579576</td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name der Anzeige aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für DoubleClick Campaign Manager und Facebook (Anzeige).</p>
      </td>
      <td>Budget-Webinar - Seitenleiste</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kennung des Creative-Elements aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.16750166675.195329631298</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des Creative-Elements aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Offizielle Site</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die erste Zeile des Creative-Elements aus der Suchanzeige, die aus dem Anzeigenkonto abgerufen wurde, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>Umsatzplanung und -zuordnung</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die zweite Zeile des Creative-Elements aus der Suchanzeige, die aus dem Anzeigenkonto abgerufen wurde, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>Erfahren Sie, warum mehr als 250 Unternehmen [!DNL Marketo Measure] für die Marketing-Attribution auswählen. Holen Sie sich eine Demo!</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Landingpage, auf die das Durchklicken von der Suchanzeige führt und die aus dem Anzeigenkonto abgerufen wird, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>http://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Der Anzeigename der URL, der in der Suchanzeige angezeigt wird und aus dem Anzeigenkonto abgerufen wird, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>ID des vom Paid Search-Kauf erworbenen Suchbegriffs, abgerufen aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche).</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.16750166675.46267805426</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Name des vom Paid Search-Kauf erworbenen Suchbegriffs, abgerufen aus dem Anzeigenkonto, von dem aus die Anzeige aufgelöst wurde. Dies gilt für Google AdWords und Bing Ads (Suche)</p>
      </td>
      <td>
        <p>[marketo]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Die Art der Übereinstimmung, die zwischen dem Suchbegriff und dem gekauften Keyword gefunden wird.</p>
      </td>
      <td>
        <p>Exakt</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint während der Sitzung ein Formular ausgefüllt hat.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob dieser Touchpoint als erster Impression Touch der Opportunity Journey behandelt wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Gibt an, ob der Touchpoint gelöscht wird.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>number(38,0)</td>
      <td>Fremdschlüssel zur Biz_Facts-Ansicht.</td>
      <td>-5269090762570690000</td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>number(38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_WEB_HOST_MAPPINGS {#biz-web-host-mappings}

Zuordnungstabelle der [!DNL Marketo Measure]-Sitzungs-ID zur Adobe ECID und Munckin ID.

<table>
  <tbody>
    <tr>
      <th>Spalte</th>
      <th>Datentyp</th>
      <th>Beschreibung</th>
      <th>Beispieldaten</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>Eine eindeutige ID für den Zuordnungsdatensatz.</td>
      <td>
        <p>0d643578c0c74753eff91abe668ed328|2020-06-17:19:03:36|0002|0|568668</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>Die von [!DNL Marketo Measure] aufgezeichnete Cookie-ID.</td>
      <td>0d643578c0c74753eff91abe668ed328</td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>Die erste Cookie-ID der zugehörigen Besucher-ID.</td>
      <td>v_0d643578c0c74753eff91abe668ed328</td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>Die [!DNL Marketo Measure] Sitzungs-ID.</td>
      <td>2018-08-06:01-35-24-1231230.9bc63c34482f</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem die Zuordnung aufgezeichnet wurde.</td>
      <td>
        <p>2020-06-17 19:03:36.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum der letzten Änderung des Datensatzes.</p>
      </td>
      <td>
        <p>2020-06-17 19:03:36.000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE</td>
      <td>varchar</td>
      <td>URL der Seitenansicht ohne Abfrageparameter.</td>
      <td>
        <p>https://learn.atest.com/simplify-retention-starter-kit.html</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_RAW</td>
      <td>varchar</td>
      <td>URL der Seitenansicht, einschließlich aller Abfrageparameter.</td>
      <td>
        <p>https://learn.atest.com/simplify-retention-starter-kit.html?x=nGfrBF&amp;utm_medium=cpc&amp;utm_source=intensify</p>
      </td>
    </tr>
    <tr>
      <td>IP_ADDRESS</td>
      <td>varchar</td>
      <td>Die aufgezeichnete IP-Adresse.</td>
      <td>
        <p>159203142127</p>
      </td>
    </tr>
    <tr>
      <td>TYPE</td>
      <td>varchar</td>
      <td>Gibt den Ereignistyp an.</td>
      <td>
        <p>HostMapping</p>
      </td>
    </tr>
    <tr>
      <td>USER_AGENT_STRING</td>
      <td>varchar</td>
      <td>Gerät und Browser, die zum Zeitpunkt der Seitenansicht aufgezeichnet wurden.</td>
      <td>
        <p>Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, wie Gecko) Chrome/79.0.3945.130 Safari/537.36</p>
      </td>
    </tr>
    <tr>
      <td>CLIENT_SEQUENCE</td>
      <td>varchar</td>
      <td>Gibt die Reihenfolge an, in der die Seitenansicht in der Sitzung stattgefunden hat.</td>
      <td>2</td>
    </tr>
    <tr>
      <td>CLIENT_RANDOM</td>
      <td>varchar</td>
      <td>Wird für interne Rechnungsprüfung und Verarbeitung verwendet.</td>
      <td>566868</td>
    </tr>
    <tr>
      <td>IS_DUPLICATED</td>
      <td>boolean</td>
      <td>Gibt an, ob der Datensatz als Duplikat betrachtet wird.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>IS_PROCESSED</td>
      <td>boolean</td>
      <td>Wird für die interne Verarbeitung verwendet.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>MAPPING_TYPE</td>
      <td>varchar</td>
      <td>Der Typ der ID, die der [!DNL Marketo Measure]-Cookie-ID zugeordnet wird.</td>
      <td>Adobe_OrgId_Ecid</td>
    </tr>
    <tr>
      <td>MAPPING_ORD_ID</td>
      <td>varchar</td>
      <td>Adobe IMS Org ID.</td>
      <td>8CC867C25245ADC30A490D4C</td>
    </tr>
    <tr>
      <td>MAPPING_COOKIE_ID</td>
      <td>varchar</td>
      <td>Adobe ECID für die angegebene Organisations-ID.</td>
      <td>09860926390077352923264316157493772857</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake erstellt wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum der letzten Änderung des Datensatzes in Snowflake.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum, an dem der Datensatz in Snowflake als gelöscht markiert wurde.</td>
      <td>2020-01-01 01:01:00.000</td>
    </tr>
  </tbody>
</table>

## Beispielabfragen {#sample-queries}

**Wie viele Buyer Touchpoints (BTs) waren im letzten Monat für jeden Kanal/Subkanal vorhanden?**

```
--Note: This query can quickly be modified to show Buyer Attribution Touchpoint (BAT) counts by switching the biz_touchpoints table to the biz_attribution_touchpoints table.
 
select trim(split(ch.name,'.')[0])  as channel
      ,trim(split(ch.name,'.')[1])  as subchannel
      ,count(bt.id)                 as buyer_touchpoint_count
  from biz_user_touchpoints     ut
       left outer join
       biz_touchpoints          bt
        on bt.user_touchpoint_id    = ut.id
       and bt._deleted_date         is null
       left outer join
       biz_channels             ch
        on ut.channel               = ch.id
       and ch._deleted_date         is null
 where ut._deleted_date is null
   and ut.touchpoint_date between add_months(date_trunc(month,current_date),-1) and last_day(dateadd(month,-1,current_date))
group by 1,2
```

**Wie viel zugewiesener Umsatz für jeden Kanal wurde im letzten Monat für das vollständige Pfadzuordnungsmodell geschlossen?**

```
--Note: This query does not perform any currency conversion.  If your data contains multiple currencies, you will need to add in logic to perform the conversion to the desired currency using the biz_conversion_rates table.
 
select trim(split(ch.name,'.')[0])  as channel
      ,sum(opp.amount*(bat.full_path_percentage/100))   as attributed_revenue
  from biz_user_touchpoints         ut
       inner join
       biz_attribution_touchpoints  bat
        on bat.user_touchpoint_id   = ut.id
       and bat._deleted_date        is null
       inner join
       biz_opportunities            opp
        on bat.opportunity_id       = opp.id
       and opp._deleted_date        is null
       and opp.is_closed            = true
       and opp.is_won               = true
       and opp.close_date between add_months(date_trunc(month,current_date),-1) and last_day(dateadd(month,-1,current_date))
       left outer join
       biz_channels                 ch
        on ut.channel               = ch.id
       and ch._deleted_date         is null
 where ut._deleted_date is null
group by 1
```

**Was ist die gesamte Journey für eine Person? (Alle Touchpoints für eine E-Mail-Adresse anzeigen.)**

```
select ut.touchpoint_date
      ,ut.marketing_touch_type
      ,listagg(distinct ifnull(sdl.stage_name,sdo.stage_name),',')           as touchpoint_position
  from biz_user_touchpoints         ut
       left outer join
       biz_touchpoints              bt
        on bt.user_touchpoint_id    = ut.id
       and bt._deleted_date         is null
       left outer join
       biz_attribution_touchpoints  bat
        on bat.user_touchpoint_id   = ut.id
       and bat._deleted_date        is null
       left outer join
       biz_lead_stage_transitions   lst
        on lst.touchpoint_id        = bt.id
       and lst._deleted_date        is null
       and lst.is_pending           = false
       and lst.is_non_transitional  = false
       left outer join
       biz_stage_definitions        sdl
        on lst.stage_id             = sdl.id
       and sdl._deleted_date        is null
       left outer join
       biz_opp_stage_transitions    ost
        on ost.touchpoint_id        = bat.id
       and ost._deleted_date        is null
       and ost.is_pending           = false
       and ost.is_non_transitional  = false
       left outer join
       biz_stage_definitions        sdo
        on ost.stage_id             = sdo.id
       and sdo._deleted_date        is null
 where ut._deleted_date     is null
   and ut.email             = [email address]
group by 1,2
order by 1
```

**Anzeigen aller Buyer Attribution Touchpoints (BATs) und deren zugewiesener Umsätze für eine einzige Opportunity.**

>[!NOTE]
>
>Diese Abfrage gibt den zugeordneten Umsatz für das W-Form-Modell zurück. Ändern Sie das Modell, indem Sie das Feld in der Berechnung des zugeordneten Umsatzes aktualisieren.

```
select bat.id
      ,bat.touchpoint_date
      ,bat.email
      ,opp.amount*(bat.w_shape_percentage/100)             as attributed_revenue
      ,listagg(osd.stage_name,', ')                        as touchpoint_position
  from biz_opportunities               opp
       inner join
       biz_attribution_touchpoints     bat
        on bat.opportunity_id      = opp.id
       and bat._deleted_date       is null
       left outer join
       biz_opp_stage_transitions       ost
        on ost.touchpoint_id       = bat.id
       and ost._deleted_date       is null
       and ost.is_pending          = false
       and ost.is_non_transitional = false
       left outer join
       biz_stage_definitions            osd
        on ost.stage_id             = osd.id
       and osd._deleted_date        is null
 where opp._deleted_date    is null
   and opp.id               = [opportunity id]
group by 1,2,3,4
order by touchpoint_date
```

[Nach oben](#data-warehouse-schema)
