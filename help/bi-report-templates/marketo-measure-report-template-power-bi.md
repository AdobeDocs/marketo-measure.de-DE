---
description: „[!DNL Marketo Measure]-Berichtsvorlage – Power BI – [!DNL Marketo Measure]“
title: „[!DNL Marketo Measure]-Berichtsvorlage – Power BI“
exl-id: c296b8f9-4033-4723-9a71-63a458640d27
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '2540'
ht-degree: 100%

---

# [!DNL Marketo Measure]-Berichtsvorlage – Power BI {#marketo-measure-report-template-power-bi}

## Erste Schritte {#getting-started}

Auf die Vorlage des Power BI-Berichts können Sie [hier](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"} zugreifen.

Öffnen Sie die Power BI-Datei der Adobe [!DNL Marketo Measure]-Berichtsvorlage.

![](assets/marketo-measure-report-template-power-bi-1.png)

Sie finden Ihre spezifischen Server-, Warehouse- und Schemadaten in der [!DNL Marketo Measure]-Benutzeroberfläche auf der [!DNL Data Warehouse]-Informationsseite. Anweisungen zum Auffinden dieser Seite finden Sie [hier](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

Die Parameter „QueryFilterStartDate“ und „QueryFilterEndDate“ werden verwendet, um die Menge der importierten Daten zu begrenzen. Diese Parameter müssen in demselben SQL-Format vorliegen wie in den an [!DNL Snowflake] gesendeten Abfragen. Wenn Sie beispielsweise Daten auf die letzten zwei Jahre beschränken möchten, würde „QueryFilterStartDate“ auf „`dateadd` (year,-2,current_date())“ lauten. Diese Parameter werden mit den datetime-Datentypen verglichen. Daher wird empfohlen, „`dateadd` (day,1,current_date())“ für „QueryFilterEndDate“ zu verwenden, um alle Daten zur aktuellen Zeit zurückzugeben.

## Datenverbindung {#data-connection}

Mit den beim Öffnen der Datei eingegebenen Parametern werden native Abfragen strukturiert, mit denen Tabellen aus dem Data Warehouse importiert werden. Sie müssen weiterhin eine Datenverbindung zu Ihrer [!DNL Snowflake]-Instanz einrichten. Dazu benötigen Sie dieselben Server- und Warehouse-Namen sowie Ihren Benutzernamen und Ihr Kennwort. Details darüber, wo Sie Ihren Benutzernamen finden und Ihr Passwort gegebenenfalls zurücksetzen können, finden Sie [hier](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

## Datenimport {#data-import}

Um die Berichtsleistung zu verbessern und die Umwandlungsfunktionen von Power Query zu nutzen, richten Sie diese Vorlage mit der Import-Speichermethode ein.

### Abfrageparameter {#query-parameters}

Um die in das Modell importierten Daten zu begrenzen, wird jede Tabelle mithilfe einer nativen Abfrage als Quelle eingerichtet. Native Abfragen erfordern eine Validierung. Sie müssen für jede Abfrage auf „Ausführen“ klicken. Dieser Schritt ist nur erforderlich, wenn die Abfragen zum ersten Mal ausgeführt werden oder sich die Parameter ändern.

![](assets/marketo-measure-report-template-power-bi-2.png)

Alle Abfragen filtern gelöschte Zeilen heraus, und die [!UICONTROL Faktentabellen] sind so eingestellt, dass sie nach Zeilen mit einem geänderten Datum zwischen Start- und Enddatum filtern, die als Parameter eingegeben wurden.

>[!NOTE]
>
>Da die Datumsfilter auf das Änderungsdatum einer Zeile angewendet werden, sollten Sie beim Reporting für Daten, die außerhalb des eingeschränkten Datumsbereichs liegen, Vorsicht walten lassen. Nehmen wir zum Beispiel an, der geänderte Datumsbereich ist auf die letzten beiden Jahre beschränkt. Dies kann ein Ereignis mit einem Ereignisdatum von vor drei Jahren umfassen, das jedoch kürzlich geändert wurde. Das Reporting über Ereignisse, die drei Jahre zurückliegen, liefert jedoch unvollständige Ergebnisse, da nicht alle Zeilen innerhalb des Zeitraums von zwei Jahren geändert wurden.

![](assets/marketo-measure-report-template-power-bi-3.png)

Die folgenden Tabellen werden als Faktentabellen behandelt. Dabei wurden diese Abfragen um die Datumsbeschränkungen für das Änderungsdatum erweitert.

* Aktivität
* Touchpoint
* Lead-Touchpoint
* Attributions-Touchpoint
* Kosten
* Site-Formular
* Sitzung
* Kampagnenmitglied
* Aufgabe
* Veranstaltung
* Übergang von Lead-/Kontaktphasen
* Übergang von Opportunity-Phasen

Die folgenden Tabellen werden als Dimensionstabellen behandelt. Für diese Abfragen sind keine Datumsbegrenzungen festgelegt.

* Konto
* Kampagne
* Kontakt
* Konversionsrate
* Opportunity
* Lead
* Phase
* Kanal

## Datenumwandlungen {#data-transformations}

Einige Umwandlungen wurden auf die Daten in Power Query angewendet. Um die spezifischen Umwandlungen für eine Tabelle anzuzeigen, öffnen Sie Power Query, navigieren Sie zu einer Tabelle und achten Sie auf die angewendeten Schritte auf der linken Seite des Fensters. Einige der spezifischen Umwandlungen sind nachfolgend beschrieben.

![](assets/marketo-measure-report-template-power-bi-4.png)

### Spalten entfernt {#removed-columns}

Um das Datenmodell zu vereinfachen und unnötige Daten zu entfernen, wurde die Anzahl der aus der ursprünglichen [!DNL Snowflake]-Tabelle nach Power BI importierten Spalten verringert. Zu den entfernten Spalten gehören unnötige Fremdschlüssel, denormalisierte Dimensionsdaten, die besser über Beziehungen zu anderen Tabellen im Modell genutzt werden können, Audit-Spalten und für die interne [!DNL Marketo Measure]-Verarbeitung verwendete Spalten. Sie können Spalten entsprechend Ihren geschäftlichen Anforderungen hinzufügen oder entfernen. Navigieren Sie in einer beliebigen Tabelle zum Schritt „Andere Spalten entfernt“ nach dem Schritt „Quelle“, klicken Sie auf das Zahnradsymbol und aktualisieren Sie die ausgewählten Spalten in der Liste.

>[!NOTE]
>
>* Gehen Sie beim Hinzufügen zusätzlicher Fremdschlüsselwerte vorsichtig vor. Power BI wird häufig so eingestellt, dass Beziehungen im Modell automatisch erkannt werden. Das Hinzufügen von Fremdschlüsselwerten kann dabei zu unerwünschten Links zwischen Tabellen und/oder zur Deaktivierung vorhandener Beziehungen führen.
>
>* Die meisten Tabellen im [!DNL Marketo Measure] Data Warehouse enthalten denormalisierte Dimensionsdaten. Das Modell wurde in Power BI so weit wie möglich normalisiert und bereinigt, um die Leistung und Datengenauigkeit zu verbessern. Gehen Sie beim Einschließen zusätzlicher denormalisierter Felder in Faktentabellen vorsichtig vor. Dies kann nämlich zu einer fehlerhaften tabellenübergreifenden Dimensionsfilterung und ungenauen Berichten führen.


![](assets/marketo-measure-report-template-power-bi-5.png)

### Spalten umbenannt {#renamed-columns}

Tabellen und Spalten wurden umbenannt, um sie benutzerfreundlicher zu gestalten und Namenskonventionen zu standardisieren. Um die Spaltennamenänderungen anzuzeigen, navigieren Sie in einer beliebigen Tabelle zum Schritt „Spalten umbenannt“ nach dem Schritt „Andere Spalten entfernt“.

![](assets/marketo-measure-report-template-power-bi-6.png)

### Segmente umbenannt {#renamed-segments}

Segmentnamen sind anpassbar. Sie weisen daher im Snowflake Data Warehouse allgemeine Spaltennamen auf. [!DNL BIZ_SEGMENT_NAMES] ist eine Zuordnungstabelle, in der der allgemeine Segmentname und der zugeordnete angepasste Segmentname aufgeführt werden, wie im Segmentabschnitt der [!DNL Marketo Measure]-Benutzeroberfläche definiert. Die Tabelle „Segmentname“ wird verwendet, um die Segmentspalten in den Lead-Touchpoint- und Attributions-Touchpoint-Tabellen umzubenennen. Wenn kein benutzerdefiniertes Segment vorhanden ist, bleibt der allgemeine Segmentname erhalten.

![](assets/marketo-measure-report-template-power-bi-7.png)

### ID-Umwandlung mit Unterscheidung zwischen Groß-/Kleinschreibung {#case-sensitive-id-conversion}

[!DNL Marketo Measure]-Daten verfügen über einige Tabellen, bei denen die Werte des Primärschlüssels (ID) zwischen Groß- und Kleinschreibung unterscheiden, nämlich „Touchpoint“ und „Kampagne“. Die Daten-Engine, die die Power BI-Modellierungsebene steuert, unterscheidet nicht zwischen Groß- und Kleinschreibung, was zu „doppelten“ ID-Werten führt. Um die Groß-/Kleinschreibung dieser Schlüsselwerte zu erhalten, wurden Umwandlungsschritte implementiert, die unsichtbare Zeichen an Kleinbuchstaben anhängen, wobei die Eindeutigkeit der ID bei der Auswertung auf Daten-Engine-Ebene gewahrt bleibt. Weitere Informationen zu diesem Problem und zu den detaillierten Schritten für die angewendete Methode finden Sie [hier] (https://blog.crossjoin.co.uk/2019
/10/06/power-bi-and-case-sensitivity/){target="_blank"}. Diese ID-Werte, bei denen zwischen Groß- und Kleinschreibung unterschieden wird, werden als „Join-IDs“ (Verküpfungs-IDs) bezeichnet und als Joinkeys (Verknüpfungsschlüssel) auf Beziehungsebene verwendet. Die Join-IDs wurden in der Berichtsebene ausgeblendet, sodass die ursprünglichen ID-Werte für Berichte sichtbar bleiben, da die unsichtbaren Zeichen die Funktionen zum Ausschneiden/Einfügen und 
Filtern beeinträchtigen können.

![](assets/marketo-measure-report-template-power-bi-8.png)

![](assets/marketo-measure-report-template-power-bi-9.png)

### Zeilen hinzugefügt {#rows-added}

Um den Berechnungen im Modell Funktionen zur Währungsumrechnung hinzuzufügen, wurde sowohl in der Tabelle für die Opportunity als auch in der für die Kosten eine Spalte für den unternehmensbezogenen Umrechnungskurs hinzugefügt. Der Wert in dieser Spalte wird auf Zeilenebene hinzugefügt und ausgewertet, indem sowohl für die Datums- als auch für die Währungs-ID eine Verknüpfung zur Tabelle mit dem Umrechnungskurs hergestellt wird. Weitere Informationen dazu, wie die Währungsumrechnung in diesem Modell funktioniert, finden Sie im Abschnitt [Währungsumrechnung](#currency-conversion) in dieser Dokumentation.

![](assets/marketo-measure-report-template-power-bi-10.png)

Die in [!DNL Snowflake] gespeicherte Tabelle „Umrechnungskurs“ enthält einen Datumsbereich für jede Umrechnung. Power BI erlaubt keine Verknüpfungskriterien für eine Berechnung (d. h. zwischen einem Datumsbereich). Für eine Verknüpfung an einem Datum wurden der Tabelle Schritte für den Umrechnungskurs hinzugefügt, um die Zeilen so zu erweitern, dass im Datumsbereich für die Umrechnung für jedes Datum eine Zeile vorhanden ist.

![](assets/marketo-measure-report-template-power-bi-11.png)

## Datenmodell {#data-model}

Klicken Sie auf das folgende Bild, um es in voller Größe anzuzeigen.

[![](assets/marketo-measure-report-template-power-bi-12.png)](/help/bi-report-templates/assets/power-bi-data-model.png){target="_blank"}

### Beziehungen und Datenfluss {#relationships-and-data-flow}

Ereignisdaten, die zum Erstellen von Touchpoints verwendet werden, werden in den Tabellen [!UICONTROL Sitzung], [!UICONTROL Aufgabe], [!UICONTROL Veranstaltung], [!UICONTROL Aktivität] und „Kampagnenmitglied“ gespeichert. Diese Ereignistabellen werden über ihre jeweiligen IDs mit der Touchpoint-Tabelle verknüpft. Wenn das Ereignis zu einem Touchpoint geführt hat, werden die Details in der Touchpoint-Tabelle gespeichert.

Lead-Touchpoints und Attributions-Touchpoints werden in ihren eigenen Tabellen gespeichert, und zwar mit einem Link zur Touchpoint-Tabelle. Die meisten Dimensionsdaten für Lead- und Attributions-Touchpoints stammen aus ihrer Verknüpfung mit dem entsprechenden Touchpoint.

In diesem Modell sind die Dimensionen „Kampagne“ und „Kanal“ mit dem Touchpoint verknüpft, sodass alle Berichte zu diesen Dimensionen über diesen Link erfolgen. Das bedeutet, dass die dimensionsbezogenen Berichte zu Ereignisdaten möglicherweise unvollständig sind. Dies ist darauf zurückzuführen, dass viele Ereignisse erst dann Links zu diesen Dimensionen haben, nachdem sie zu Touchpoints verarbeitet wurden. Hinweis: Einige Ereignisse, wie z. B. Sitzungen, haben direkte Links zu den Dimensionen „Kampagne“ und „Kanal“. Wenn Berichte zu diesen Dimensionen auf Sitzungsebene gewünscht werden, wird empfohlen, hierzu ein eigenes Datenmodell zu erstellen.

Kostendaten werden auf unterschiedlichen Aggregationsebenen in der [!DNL Snowflake] Data Warehouse-Kostentabelle gespeichert. Für alle Anzeigenanbieter kann für die Daten auf Kampagnenebene ein Rollup auf Kanalebene durchgeführt werden. Aus diesem Grund ruft dieses Modell Kostendaten basierend auf dem Flag „campaign_is_aggregatable_cost“ ab. Selbstgemeldete Kosten können nur auf Kanalebene übermittelt werden und sind nicht erforderlich, um über Kampagnendaten zu verfügen. Um möglichst genaue Kostenberichte zu ermöglichen, werden die selbstgemeldeten Kosten basierend auf dem Flag „channel_is_aggregatable_cost“ abgerufen. Die Abfrage zum Import von Kostendaten wird mit folgender Logik verfasst: If ad_provider = &quot;SelfReported&quot; then channel_is_aggregatable_cost = true, else campaign_is_aggregatable_cost = true.

Kostendaten und Touchpoint-Daten verfügen über einige gemeinsame Dimensionen, sodass beide Faktentabellen Beziehungen zu den Dimensionstabellen „Kampagne“ und „Kanal“ aufweisen.

Im Kontext dieses Modells werden diese Modell-, [!UICONTROL Lead]-, [!UICONTROL Kontakt]-, [!UICONTROL Konto]- und [!UICONTROL Opportunity]-Daten als Dimensionsdaten betrachtet und direkt mit den Tabellen der [!UICONTROL Lead]- und [!UICONTROL Attributions]-Touchpoints verknüpft.

### Tabellen hinzugefügt {#added-tables}

**Datum**

Da Power BI nur Beziehungen zwischen Tabellen in einer Spalte ermöglicht, wurde eine Dimensionstabelle „Datum“ hinzugefügt, um die nötige Verknüpfung zwischen den Tabellen mit den Beträgen (Opportunity und Kosten) und der Tabelle „Umrechnungskurs“ zu ermöglichen. Weitere Informationen zum Berechnen von Währungsumrechnungen in diesem Modell finden Sie im Abschnitt „Währungsumrechnung“.

**Kennzahlen**

Alle Kennzahlen wurden einer speziellen Tabelle „Kennzahlen“ hinzugefügt. Sie ist nicht mit dem Modell verbunden, dient der Einfachheit halber aber als zentraler Speicherort für alle Kennzahlen.

**Attributionsmodell**

Es wurde eine separate Tabelle hinzugefügt, in der die Namen der Attributionsmodelle gespeichert werden. Diese Tabelle wird verwendet, um Filter zu erstellen, mit denen Benutzende bei Berechnungen attributierter Umsätze zwischen Attributionsmodellen wechseln können.

### Währungsumrechnung {#currency-conversion}

Die in der Tabelle „Umrechnungskurs“ angegebenen Kurse stellen den Wert dar, der zum Umrechnen eines Betrags aus der Unternehmenswährung erforderlich ist. Für Umrechnungen in eine beliebige Währung ist eine doppelte Umrechnung erforderlich: zunächst von der ursprünglichen Währung in die Unternehmenswährung und dann von der Unternehmenwährung in die ausgewählte Währung. Der erste Schritt in dieser Kette im Modell besteht darin, eine Spalte mit diesem Umrechnungskurs zu den Tabellen mit Beträgen, Opportunitys und Kosten hinzuzufügen. Diese Schritte werden unter der Überschrift „Zeilen hinzugefügt“ des Abschnitts „Datenumwandlungen“ in diesem Dokument beschrieben. Bei der Umrechnung von der ursprünglichen Währung in die Unternehmenswährung wird der Wert durch diese hinzugefügte Spalte geteilt. Der nächste Schritt besteht darin, den unternehmensbezogenen Währungswert mit dem Kurs in der Tabelle „Umrechnungskurs“ zu multiplizieren, der der ausgewählten Währung entspricht.

* Umrechnen des ursprünglichen Werts in den unternehmensbezogenen Währungswert / unternehmensbezogener Umrechnungskurs = Wert in der Unternehmenswährung
* Umrechnen des Werts aus dem unternehmensbezogenen in den ausgewählten Währungswert in der Unternehmenswährung `*` Umrechnungskurs der ausgewählten Währung = Wert in der ausgewählten Währung

Da Umrechnungskurse nicht statisch sein müssen und sich in bestimmten Datumsbereichen ändern können, müssen alle Währungsumrechnungen auf Zeilenebene durchgeführt werden. Umrechnungskurse beziehen sich, wie bereits erwähnt, nicht auf einen bestimmten Datumsbereich, sodass die Lookup-Berechnung innerhalb des DAX der Kennzahl durchgeführt werden muss, damit die Beziehung sowohl für den Währungs-Code als auch für das Datum definiert werden kann.

In den Kennzahlen für die Währungsumrechnung in diesem Modell wird der Wert 1,0 für den Kurs eingesetzt, wenn kein Umrechnungskurs identifiziert werden kann. Es wurden separate Kennzahlen erstellt, um den Währungswert für die Kennzahl anzuzeigen und einen Warnhinweis auszugeben, wenn eine Berechnung mehr als einen Währungswert enthält ((d. h. ein Wert konnte nicht in die ausgewählte Währung umgerechnet werden).

![](assets/marketo-measure-report-template-power-bi-13.png)

## Datendefinitionen {#data-definitions}

Zum Power BI-Modell wurden Definitionen für Tabellen, benutzerdefinierte Spalten und Kennzahlen hinzugefügt.

![](assets/marketo-measure-report-template-power-bi-14.png)

![](assets/marketo-measure-report-template-power-bi-15.png)

![](assets/marketo-measure-report-template-power-bi-16.png)

Informationen zum Anzeigen von Definitionen für Spalten, die direkt aus [!DNL Snowflake] stammen, finden Sie in der [Data-Warehouse-Dokumentation](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"}.

## Diskrepanzen zwischen Vorlagen- und Discover-Modell {#discrepancies-between-templates-and-discover}

### Attributierter Umsatz {#attributed-revenue}

Lead-Touchpoints und Attributions-Touchpoints übernehmen Dimensionsdaten vom ursprünglichen Touchpoint. Das Berichtsvorlagenmodell liefert alle übernommenen Dimensionsdaten aus der Beziehung zum Touchpoint, während im Discover-Modell Dimensionsdaten in die Lead- und Attributions-Touchpoint-Datensätze denormalisiert werden. Die insgesamt attributierten Umsätze oder attributierten Pipeline-Umsätze sollten zwischen den beiden Berichten stimmig sein. Es können jedoch Diskrepanzen auftreten, wenn der Umsatz nach Dimensionsdaten (Kanal, Subkanal oder Kampagne) aufgeschlüsselt oder gefiltert wird. Wenn die dimensionsbezogenen Umsatzbeträge zwischen Vorlage und Discover nicht übereinstimmen, fehlen wahrscheinlich Touchpoint-Datensätze im Vorlagenberichtsdatensatz. Dies geschieht, wenn ein Lead- oder Attributions-Touchpoint-Datensatz vorhanden ist, es aber keinen entsprechenden Datensatz in der Touchpoint-Tabelle innerhalb des in den Bericht importierten Datensatzes gibt. Diese Tabellen werden nach dem Änderungsdatum gefiltert. Daher ist es möglich, dass der Lead-/Attributions-Touchpoint-Datensatz später als der Touchpoint-Datensatz geändert und somit zwar der Lead-/Attributions-Touchpoint in den Datensatz importiert wurde, der ursprüngliche Touchpoint-Datensatz aber nicht. Um dieses Problem zu beheben, erweitern Sie den gefilterten Datumsbereich für die Touchpoint-Tabelle oder entfernen Sie die Datumsbeschränkung insgesamt. Hinweis: Die Touchpoint-Tabelle ist groß. Achten Sie daher auf eine gewisse Balance zwischen der Vollständigkeit eines Datensatzes und der Menge der zu importierenden Daten.

### Kosten {#cost}

Kostenberichte in den Vorlagen sind nur auf Kampagnen- und Kanalebene verfügbar. Discover bietet jedoch Berichte mit geringerer Granularität für bestimmte Anzeigenanbieter (d. h. zu Kreativinhalten, Keywords, Anzeigengruppen usw.). Weitere Informationen zum Modellieren der Kostendaten in den Vorlagen finden Sie im Abschnitt „Datenmodell“ in dieser Dokumentation. Wenn der Dimensionsfilter in [!UICONTROL Discover] auf Kanal oder Kampagne eingestellt ist, sollten die Kosten auf Kanal-, Subkanal- und Kampagnenebene zwischen Discover und Berichtsvorlagen stimmig sein.

### ROI {#roi}

Da sich der ROI aus attributiertem Umsatz und Kosten berechnet, können dieselben Diskrepanzen, die bei diesen Berechnungen auftreten können, auch im ROI aus den gleichen Gründen auftreten, wie in diesen Abschnitten beschrieben.

### Touchpoints {#touchpoints}

Diese Metriken werden, wie in den Berichtsvorlagen dargestellt, in Discover nicht widergespiegelt. Es ist derzeit kein direkter Vergleich zwischen Vorlagen und Discover möglich.

### Webtraffic {#web-traffic}

Das Datenmodell der Berichtsvorlage normalisiert die Dimensionsdaten von Kanal, Subkanal und Kampagne über die Beziehung zwischen Sitzung und Touchpoint. Dies unterscheidet sich vom Discover-Datenmodell, bei dem diese Dimensionen für die Sitzung denormalisiert werden. Aufgrund dieser Unterscheidung sollten die Gesamtzahlen für Besuche und Besuchende zwischen Discover und der Berichtsvorlage übereinstimmen. Wenn diese Zahlen jedoch nach Dimension angezeigt oder gefiltert werden, wird diese Übereinstimmung nicht erwartet. Dies liegt daran, dass die Dimensionsdaten in der Vorlage nur für Web-Ereignisse verfügbar sind, die zu einem Touchpoint geführt haben (d. h. nicht anonyme Ereignisse). Weitere Informationen finden Sie im Abschnitt [Datenmodell](#data-model) in dieser Dokumentation.

Es kann kleine Diskrepanzen bei der Gesamtzahl der Site-Formulare zwischen [!DNL Discover] und der Vorlage geben. Dies liegt daran, dass das Datenmodell in der Berichtsvorlage über eine Beziehung zur Sitzung und dann zum Touchpoint Dimensionsdaten für das Site-Formular erhält. Es einigen Fälle weisen Site-Formulardaten keine korrelierte Sitzung auf.

### Leads und Konten {#leads-and-accounts}

Die Dimensionsberichte für die betroffenen Konten können zwischen Discover und der Vorlage geringfügig voneinander abweichen. Dies ist erneut auf die Dimensionsmodellierung auf Basis der Beziehung zwischen Touchpoint und Lead- bzw. Attributions-Touchpoint zurückzuführen. Weitere Informationen dazu finden Sie im Abschnitt „Zugewiesener Umsatz“.

Alle Lead-Zahlen in Discover sind attributierte Lead-Zahlen, und in der Berichtsvorlage weist die Metrik Lead-Touchpoints auf. Daher ist für diese Kennzahl kein direkter Vergleich zwischen den beiden Berichten möglich.

### Interaktionsverlauf {#engagement-path}

Es gibt keinen direkten Vergleich zwischen dem Bericht [!UICONTROL Interaktionsverlauf] in Discover und der Vorlage. Der Bericht in [!DNL Discover] wird ausgehend vom Touchpoint, aber der Bericht in der Vorlage ausgehend vom Attributions-Touchpoint modelliert. Die Vorlage konzentriert sich ausschließlich auf Opportunitys und ihre zugehörigen Touchpoints, anstatt alle Touchpoint-Daten anzuzeigen.

### Abschlussgeschwindigkeit {#deal-velocity}

Es sollte keine Diskrepanz zwischen diesem Bericht in der Vorlage und der Kachel „Abschlussgeschwindigkeit“ im Dashboard „Geschwindigkeit“ in Discover geben.
