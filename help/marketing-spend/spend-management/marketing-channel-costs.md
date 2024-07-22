---
unique-page-id: 18874602
description: Marketingkanal-Kosten - [!DNL Marketo Measure]
title: Marketingkanal-Kosten
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
feature: Channels, Spend Management
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 0%

---

# Marketingkanal-Kosten {#marketing-channel-costs}

Einer der grundlegendsten Vorteile der Verwendung von [!DNL Marketo Measure] ist die Möglichkeit, Marketing-Maßnahmen direkt mit den Auswirkungen auf den Umsatz zu verbinden - mit einer so großen Granularität wie gewünscht. Es ist möglich, die Kapitalrendite auf der Touchpoint-Ebene zu sehen. Um diesen Vorteil nutzen zu können, müssen die Kanalkosten in die [!DNL Marketo Measure]-App hochgeladen werden. ROI-Berichte werden automatisch erstellt und stehen im **Marketing-ROI-Dashboard** in [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} zur Verfügung.

[Klicken Sie hier , um direkt zu den Anweisungen zu navigieren.](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs)

Mit der Funktion [!DNL Marketo Measure] Marketing-Ausgaben können Kunden ihre Ausgaben über alle Kanäle, Subkanäle und Kampagnen hochladen. Je mehr Daten von Kunden hinzugefügt werden, desto mehr ROI-Berichte werden im Dashboard &quot;Umsatzzuordnung&quot;angezeigt.

Kosten, die gemeldet und aus Direktwerbeverbindungen importiert werden, werden automatisch auf der detailliertesten Ebene erfasst und müssen nicht hochgeladen werden. Dazu gehören unsere aktuellen Integrationen mit Google AdWords, Bing Ads, Doubleclick und Facebook.

[Klicken Sie hier , um direkt zur FAQ zu navigieren.](/help/marketing-spend/spend-management/marketing-channel-costs.md#faq)

## Definitionen {#definitions}

**Ausgaben nach Kampagne**

Auf der detailliertesten Ebene können Kunden Ausgaben nach einzelnen Kampagnen eingeben, die innerhalb ihres jeweiligen Kanals gruppiert sind. Bei CRM-Kampagnen hat [!DNL Marketo Measure] die Kampagnen-ID in eine separate Spalte eingefügt, mit der Sie Offline-Kampagnenausgaben aus Ihrem CRM-System dieser Tabelle zuordnen können. Durch das Hinzufügen von Ausgaben auf dieser Ebene können Kunden den Kampagnen-ROI anzeigen und die Leistung von Campaign optimieren.

Die Summe aller Kampagnen muss nicht zu den Werten zusammenfassen, die im Subkanal oder Kanal eingegeben wurden. Sie darf jedoch nicht größer sein als die Werte, die im Subkanal oder Kanal eingegeben wurden. Wenn die Summe kleiner ist als der im Unterkanal oder Kanal eingegebene Wert, fügt [!DNL Marketo Measure] automatisch eine Zeile für &quot;Sonstige&quot;hinzu, um die Differenz abzudecken und Lücken zu füllen.

**Nach Unterkanal ausgeben**

Auf einer höheren Ebene können Kunden Ausgaben nach Subkanal eingeben, die unter ihrem Kanal gruppiert sind. Durch das Hinzufügen von Ausgaben auf dieser Ebene können Kunden den Subchannel-ROI anzeigen und die Leistung nach Subchannel optimieren.

Die Summe aller Unterkanäle muss nicht den im Kanal eingegebenen Werten entsprechen, darf jedoch nicht größer sein als die im Kanal eingegebenen Werte. Wenn die Summe kleiner ist als der im Kanal eingegebene Wert, fügt [!DNL Marketo Measure] automatisch eine Zeile für &quot;Sonstige&quot;hinzu, um die Differenz abzudecken und alle Lücken zu füllen.

**Verbringen nach Kanal**

Auf der höchsten Ebene können Kunden Ausgaben nach Kanal eingeben. Durch das Hinzufügen von Ausgaben auf dieser Ebene können Kunden den Kanal-ROI anzeigen und die Leistung nach Kanal optimieren.

**Datumsauswahl**

Der standardmäßige Datumsbereich beginnt von Ihrem Startdatum mit [!DNL Marketo Measure] bis zum aktuellen Monat. Um sicherzustellen, dass die Kosten korrekt bleiben, können Sie keine Kosten für zukünftige Monate angeben, sondern Kosten für Monate vor Ihrer Partnerschaft mit [!DNL Marketo Measure] eingeben.

**Filter**

Um Ihre Ergebnisse in der Tabelle Marketing-Ausgaben einzugrenzen, wählen Sie oben einen Kanal aus, um andere Kanäle herauszufiltern. Dies ist hilfreich, wenn Sie ein Team haben, das sich auf einen einzelnen Kanal konzentriert.

**Suche**

Verwenden Sie das Suchfeld, um übereinstimmenden Text aus Kanälen, Unterkanälen oder Kampagnen zu finden.

**Aktuelle Kosten herunterladen**

Die heruntergeladene CSV-Datei ruft die Ergebnisse von Ihrem aktuellen Bildschirm ab, d. h. alle Daten, Filter oder Suchvorgänge, die angewendet werden, werden unverändert heruntergeladen.

**CSV hochladen**

Unabhängig davon, welche Ansicht im Browser angezeigt wird, können Sie eine beliebige CSV-Datei hochladen, wenn es sich um eine gefilterte Ansicht oder eine Standardansicht mit allen Daten und Kanälen handelt.

Der häufigste Fehler ist das Format der Datumsspalten, das auftritt, wenn das Datumsformat geändert wird und der Wechsel zwischen Excel und/oder Google Tabellen mit Absicht erfolgen kann. Denken Sie daran, dass das Datum MM-YY sein sollte, also Sep-12 und nicht Sept-12, oder Mai-12 und nicht 05-12.

## Vorbereitung {#before-you-begin}

[!DNL Marketo Measure] enthält 13 Standardkanäle, die verwendet oder erweitert werden können. Zusätzlich können bis zu 40 Online- und Offline-Kanäle erstellt werden, um Ihre einzigartige Marketingstruktur zu berücksichtigen. Daraus können insgesamt 200 Unterkanäle erstellt werden, um diese Online- und Offline-Kanäle ebenfalls zu unterstützen.

[!DNL Marketo Measure] lädt die Marketingkanalkosten automatisch von Plattformen herunter, mit denen eine API-Integration besteht, z. B. Bing Ads und Google AdWords. Kosten für Plattformen, die nicht mit [!DNL Marketo Measure] integriert sind, müssen manuell hochgeladen werden. Die Marketingkanäle sollten eingerichtet werden, bevor die Kostendaten hochgeladen werden.

## Hochladen von Marketingkosten {#uploading-marketing-costs}

Sobald Marketing-Kanäle und -Regeln eingerichtet oder aktualisiert wurden, können die damit verbundenen Kosten hochgeladen werden. Gehen Sie dazu wie folgt vor:

**Schritt 1: Navigieren Sie zur Seite &quot;Marketing-Ausgaben&quot;in der [!DNL Marketo Measure] App.**

Gehen Sie zum Menü **[!UICONTROL Mein Konto]** , klicken Sie auf **[!UICONTROL Einstellungen]** und navigieren Sie dann zur Option **[!UICONTROL Marketingausgaben]** auf der linken Seitenleiste unter dem Abschnitt **[!UICONTROL Berichterstellung]** .

![](assets/1.png)

**Schritt 2: Laden Sie die aktuellen Kosten-CSV herunter**

Navigieren Sie rechts neben dem Bildschirm und klicken Sie auf **[!UICONTROL Aktuelle Kosten herunterladen].** Mit dieser Option können Sie eine Tabelle im CSV-Format herunterladen.

![](assets/2.png)

**Schritt 3: Öffnen Sie die CSV-Datei und nehmen Sie Änderungen vor**

Sie können die Datei importieren und öffnen, indem Sie Google Tabellen, Apple Numbers, Microsoft Excel oder Ihre Auswahl an Software verwenden. [!DNL Marketo Measure] empfiehlt die Verwendung von Google Tabellen.

Nehmen Sie nach dem Import des Blatts die gewünschten Änderungen vor, z. B. das Hinzufügen von Kosten zu Kanälen und Unterkanälen oder das Aktualisieren vorhandener Informationen.

Überprüfen Sie die Logikregeln in Ihrem Arbeitsblatt. Jede Zeile sollte einen Kanal und einen seiner Unterkanäle enthalten, die durch ein (.) Punkt am Ende. Die konsequente Verwendung dieses Formats ist wichtig.

Um beispielsweise Facebook als Unterkanal und Social als Kanal anzugeben, sollte die Regel wie folgt geschrieben werden: &quot;Social.Facebook&quot;. Um ein Offline-Ereignis zu verfolgen, sollte die Kanalsyntax folgendermaßen lauten: &quot;Events.Big Conference&quot;. Beispiele werden in der folgenden Abbildung gezeigt:

![](assets/3.png)

_Zusätzliche Hinweise_:

Ändern Sie die Daten im Arbeitsblatt nicht, da dies beim Hochladen des Dokuments zu Problemen führen kann.

Lassen Sie kein Feld leer. Auch wenn kein Dollarwert hinzukommt, geben Sie 0 Dollar als Dollarbetrag ein.

Die Kosten für Bing Ads und Google AdWords müssen nicht eingegeben oder aktualisiert werden, da [!DNL Marketo Measure] diese Daten automatisch aus der API-Verbindung mit diesen Plattformen abruft.

**Schritt 4: Datei im CSV-Format speichern**

Wenn Sie in Google Tabellen arbeiten, sollten Sie die Datei zuerst herunterladen. Schließen Sie keine monatlichen Daten aus oder löschen Sie sie, da dies beim Versuch, die CSV-Datei später in [!DNL Marketo Measure] hochzuladen, Schwierigkeiten verursacht.

**Schritt 5: CSV-Datei hochladen**

Wechseln Sie zum Abschnitt **[!UICONTROL Kosten]** der [!DNL Marketo Measure]-App und klicken Sie auf **[!UICONTROL Upload.CSV]**. Das System aktualisiert und gibt die neuen Informationen wieder.

## FAQs {#faq}

**Warum werden Zahlen im CSV angezeigt**

Wenn kein Wert auf einer höheren Ebene wie Kanal oder Subkanal eingegeben wird, summiert [!DNL Marketo Measure] automatisch die untergeordneten Ebenen für Sie, die nach dem Hochladen der Datei angezeigt werden. Wenn die Summe der untergeordneten Elemente kleiner ist als der für das übergeordnete Element eingegebene Wert, fügt [!DNL Marketo Measure] die Zeile &quot;Sonstige&quot;hinzu, um die Differenz in der Gesamtsumme anzuzeigen.

**Wie werden die Kampagnen in der Liste bestimmt, die mir angezeigt wird?**

Im Moment werden in unseren Ergebnissen Kampagnen aufgelistet, die wir gesehen haben, dass sie einem Touchpoint gutgeschrieben wurden. Wenn eine Kampagne eine Aktivität enthielt, zeigen wir, dass die Kampagne auf dem Touchpoint-Datum basiert, an dem sie aufgetreten ist.

**Es gibt zu viele Zeilen und Spalten, um durchs Bild zu gelangen. Kann ich die Ansicht konsolidieren?**

Mit der Fähigkeit, den Datumsbereich zu ändern, den Kanal zu filtern oder nach Werten zu suchen, können Sie die Ergebnisse der Tabelle konsolidieren, um sie Ihren Anforderungen besser anzupassen.

**Warum kann ich keine Datei hochladen?**

Wir haben verschiedene Berechtigungssätze innerhalb der [!DNL Marketo Measure]-App. Um eine Datei hochzuladen, müssen Sie ein &quot;AccountAdmin&quot;sein. Um dies zu umgehen, bitten Sie Ihren AccountAdmin um Zugriff oder lassen Sie Ihre AccountAdmin die Datei in Ihren Namen hochladen. Eine Liste der Benutzer und ihrer Rollen finden Sie unter **[!UICONTROL Mein Konto]** > **[!UICONTROL Einstellungen]** > **[!UICONTROL Kontobenutzer anzeigen/hinzufügen]**.
