---
unique-page-id: 18874656
description: Filter - [!DNL Marketo Measure] - Produktdokumentation
title: Filter
exl-id: 249266c8-9ff5-4895-979c-4f377423d031
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1290'
ht-degree: 3%

---

# Filter {#filters}

Erfahren Sie mehr über die verschiedenen Filter, die Ihnen in Discover zur Verfügung stehen, und wie Sie sie verwenden können.

>[!NOTE]
>
>Die Operatoren &quot;stimmt mit einem Benutzerattribut überein&quot;und &quot;stimmt überein mit (erweitert)&quot;in Ihren Discover-Filtern sind rein administrativ und können problemlos ignoriert werden.

**Konto-ID**

_Verwendet in: Account-basiertes Marketing_

Wählen Sie eine Reihe von Konto-IDs aus dem CRM-System aus oder fügen Sie sie ein, um die Ergebnisse zu filtern. Konto-IDs bieten mehr Eindeutigkeit als der Kontoname, da Namen identisch sein können.

**Kontoname**

_Verwendet in: Account-basiertes Marketing_

Wählen Sie aus dem CRM-System eine Reihe von Kontonamen aus oder fügen Sie diese ein, um die Ergebnisse zu filtern. Zeichenfolgen können Duplikate aufweisen, sodass mehrere &quot;[!DNL Marketo Measure]&quot; beispielsweise. Wenn in diesem Fall ein einzelnes Konto benötigt wird, verwenden Sie stattdessen den Filter Konto-ID .

**Attributionsmodell**

_Verwendet in: Übersicht, Marketing-Ausgaben, Anzeigen-ROI, Account-basiertes Marketing, Web-Traffic, CMO, Paid Media, Content Marketing, Pass_

Wählen Sie ein einzelnes Attributionsmodell aus, das auf die Pinnwand angewendet werden soll: Erstkontakt, Lead-Erstellungskontakt, U-förmig, W-förmig, Vollständiger Pfad oder benutzerdefiniertes Modell. Der vollständige Pfad und das benutzerdefinierte Modell sind nicht für alle Ebenen verfügbar.

**Kampagne**

_Verwendet in: Übersicht, Wachstum, Anzeigen-ROI, Web-Traffic, CMO, Paid Media, Content Marketing, Passport_

Filtern Sie die Pinnwand nach einem oder mehreren Kampagnennamen. Benutzer bieten dem Filter zusätzliche Flexibilität, z. B. die Operatoren &quot;enthält&quot;oder &quot;beginnt mit&quot;. Wenn ein Kanal- oder Subkanalfilter angewendet wurde, ist die Liste der angezeigten Kampagnen eine Untergruppe der angewendeten Filter.

**Kategorie 1-10**

_Verwendet in: Übersicht, Wachstum, Anzeigen-ROI, CMO, Paid Media, Content Marketing, Velocity, Snapshot, Cohort-Trichter, Pass_

Wenden Sie mithilfe der Kategorien und Segmente, die Sie in der [!DNL Marketo Measure] Einstellungen. Die Liste der von Ihnen erstellten Kategorien wird im Filtermenü angezeigt. Wenn also keine Kategorien eingerichtet wurden, enthält das Menü keine Kategoriefilter. Segmentkategorien sind nicht in allen Ebenen verfügbar, und die Anzahl der verfügbaren Kategorien variiert auch nach Ebene.

**Kanal**

_Verwendet in: Übersicht, Wachstum, Marketing-Ausgaben, Anzeigen-ROI, Web-Traffic, CMO, Paid Media, Content Marketing, Velocity, Passport_

Filtern Sie die Pinnwand nach einem oder mehreren Kanälen. Benutzer bieten dem Filter zusätzliche Flexibilität, z. B. die Operatoren &quot;enthält&quot;oder &quot;beginnt mit&quot;. Nach der Eingabe eines Kanals stammen die im Subkanal- und Kampagnenfilter angezeigten Werte aus dem angewendeten Subkanalfilter.

**Kohorten-Stadium**

_Verwendet in: Kohortentrichter_

Wählen Sie die Phase aus, für die Sie eine Kohorte anzeigen möchten. Die Phase, die Sie auswählen, wird oben im Trichter angezeigt, wobei alle Konversionen von oben nach unten fließen.

**Datum**

_Verwendet in: Übersicht, Wachstum, Marketing-Ausgaben, Anzeigen-ROI, Account-basiertes Marketing, Web-Traffic, CMO, Paid Media, Content Marketing, Velocity, Snapshot, Cohort Funnel, Passport_

Wählen Sie einen Datumsbereich aus, um die Daten in den Pinnwänden zu filtern, indem Sie flexible Datumsoperatoren verwenden, z. B. &quot;liegt im Bereich&quot;, &quot;ist im Jahr&quot;oder &quot;ist vor&quot;. Die Ausnahme ist Snapshot, bei dem Sie ein einzelnes Datum auswählen, um eine Momentaufnahme der Daten anzuzeigen.

**Datumstyp**

_Verwendet in: Übersicht, Wachstum, Marketing-Ausgaben, Anzeigen-ROI, Account-basiertes Marketing, Web-Traffic, CMO, Paid Media, Content Marketing, Passport_

Wählen Sie den Datumstyp aus, der mit dem Datumsfilter verknüpft werden soll. Der standardmäßige Datumstyp variiert je nach Pinnwand. Touchpoint-Datum bezieht sich auf das Datum, an dem die Marketing-Aktivität stattgefunden hat, das Erstellungsdatum das Datum, an dem der Lead oder Kontakt oder die Gelegenheit im CRM erstellt wurde, und das Datum des Schließen ist das Datum, an dem die Gelegenheit geschlossen wurde.

**Abmessung**

_Verwendet in: Paid Media_

Die Dimension ähnelt der Funktion &quot;Gruppieren nach&quot;, allerdings wird sie auf der Paid Media-Pinnwand etwas anders verwendet. Statt ein Diagramm zu stapeln, ändert die Dimension die Zeilen aus dem Übersichtsdiagramm sowie das führende Objekt in den Tabellen.

![](assets/1.png)

Standardmäßig ist die Dimension auf &quot;Subchannel&quot;festgelegt und kann wie folgt geändert werden:

* Keine: Zeigt alles aggregiert und ohne Aufschlüsselung an
* Kanal: Listet die Daten nach Marketing-Kanal auf
* Unterkanal: Listet die Daten nach Marketing-Unterkanal auf
* Kampagne: Listet die Daten nach Kampagne auf
* Konto: Listet die Daten nach Konto auf. Gilt für [!DNL AdWords], [!DNL Bing], und [!DNL Facebook].
* Anzeigengruppe: Listet die Daten nach Anzeigengruppe auf. Gilt für [!DNL AdWords], [!DNL Bing], und [!DNL Facebook].
* Anzeige: Listet die Daten nach Anzeige auf. Gilt für Doppelklick-Anzeigen. Wenn also kein Doppelklick verwendet wird, werden keine Ergebnisse angezeigt
* Advertiser: Listet die Daten nach Advertiser auf. Gilt für den Advertiser Doubleclick. Wenn also Doubleclick nicht verwendet wird, werden keine Ergebnisse angezeigt
* Kreativ: Listet die Daten kreativ auf. Gilt für [!DNL AdWords], [!DNL Bing], und [!DNL Facebook].
* Schlüsselwort: Listet die Daten nach Schlüsselwörtern auf. Gilt für [!DNL AdWords], [!DNL Bing], und [!DNL Facebook].
* Platzierung: Listet die Daten nach Platzierung auf. Gilt für Doppelklick-Platzierungen. Wenn also kein Doppelklick verwendet wird, werden keine Ergebnisse angezeigt
* Site: Listet die Daten nach Site auf. Gilt für Doubleclick-Sites. Wenn Doubleclick nicht verwendet wird, werden keine Ergebnisse angezeigt

**Gruppieren nach**

_Verwendet in: Übersicht, Wachstum, Marketing-Ausgaben, Account-basiertes Marketing, Web-Traffic, CMO_

Passt Diagramme an, um die Dimension zu ändern, die gestapelt und gruppiert wird. Standardmäßig ist &quot;Gruppieren nach&quot;auf &quot;Kanal&quot;gesetzt und kann wie folgt geändert werden:

* Keine: Zeigt alles aggregiert und ohne Aufschlüsselung an
* Kanal: Gruppiert die Daten nach Marketing-Kanal
* Subchannel: Gruppiert die Daten nach Marketing-Subkanal
* Kampagne: Gruppiert die Daten nach Kampagne
* Konto: Gruppiert die Daten nach Konto. Gilt für [!DNL AdWords], [!DNL Bing], und [!DNL Facebook].
* Anzeigengruppe: Gruppiert die Daten nach Anzeigengruppe. Gilt für [!DNL AdWords], [!DNL Bing], und [!DNL Facebook].
* Anzeige: Gruppiert die Daten nach Anzeige. Gilt für Doppelklick-Anzeigen. Wenn also kein Doppelklick verwendet wird, werden keine Ergebnisse angezeigt
* Advertiser: Gruppiert die Daten nach Advertiser. Gilt für den Advertiser Doubleclick. Wenn also Doubleclick nicht verwendet wird, werden keine Ergebnisse angezeigt
* Kreativ: Gruppiert die Daten nach Kreativelementen. Gilt für [!DNL AdWords], [!DNL Bing], und [!DNL Facebook].
* Schlüsselwort: Gruppiert die Daten nach Schlüsselwörtern. Gilt für [!DNL AdWords], [!DNL Bing], und [!DNL Facebook].
* Platzierung: Gruppiert die Daten nach Platzierung. Gilt für Doppelklick-Platzierungen. Wenn also kein Doppelklick verwendet wird, werden keine Ergebnisse angezeigt
* Site: Gruppiert die Daten nach Site. Gilt für Doubleclick-Sites. Wenn Doubleclick nicht verwendet wird, werden keine Ergebnisse angezeigt

![](assets/2.png)

**Landing Page**

_Verwendet in: Content Marketing_

Informieren Sie sich über die Leistung einer einzelnen Landingpage oder vielleicht von Landingpages, die ein bestimmtes Wort wie &quot;Blog&quot;enthalten.

**Metrisch**

_Verwendet in: Übersicht, Web-Traffic, CMO, Paid Media, Content Marketing_

Es gibt zwei verschiedene Metrikwähler, die auf verschiedenen Pinnwänden verwendet werden. Die Metrikauswahl ändert die Kennzahl in einem Diagramm, sodass Sie z. B. zwischen Umsatz, Ausgaben oder Impressionen wechseln können.

Auf den Übersichts- und CMO-Pinnwänden finden Sie eine gekürzte Liste von Werten im Zusammenhang mit ROI-Metriken:

* Umsatz
* Ausgaben
* Abschlüsse
* Pipeline-Umsatz
* Gelegenheiten
* Kontakte
* Leads

In den Pinnwänden für Web-Traffic, gebührenpflichtige Medien und Content Marketing gibt es eine längere Liste von Werten, die sich sowohl auf ROI- als auch Trichtermetriken beziehen:

* Umsatz
* Ausgaben
* Abschlüsse
* Pipeline-Umsatz
* Gelegenheiten
* Kontakte
* Leads
* Klicks
* Impressionen
* Besuche
* Eindeutige Besuche
* Seitenansichten
* Formulare

**Phase**

_Verwendet in: Velocity_

Standardmäßig zeigt das Velocity-Forum die Zeiten für alle Bühnen an. Um jedoch zu einer bestimmten Phase zu gelangen, wählen Sie die Bühne mit dem Filter Staging aus.

**Unterkanal**

_Verwendet in: Übersicht, Wachstum, Marketing-Ausgaben, Anzeigen-ROI, Web-Traffic, CMO, Paid Media, Content Marketing, Pass_

Filtern Sie die Pinnwand nach einem oder mehreren Unterkanälen. Benutzer bieten dem Filter zusätzliche Flexibilität, z. B. die Operatoren &quot;enthält&quot;oder &quot;beginnt mit&quot;. Wenn ein Kanalfilter angewendet wurde, ist die Liste der angezeigten Unterkanäle eine Untergruppe der angewendeten Filter. Sobald ein Unterkanal eingegeben wurde, stammen die in den Kampagnenfiltern angezeigten Werte aus dem angewendeten Subkanalfilter.

**URL**

_Wird verwendet in: Web Traffic_

Informieren Sie sich über den Traffic einer einzelnen URL oder möglicherweise über URLs, die ein bestimmtes Wort wie &quot;Produkt&quot;enthalten.

**Gewonnen**

_Verwendet in: Velocity_

Standardmäßig berichtet das Velocity-Board nur über geschlossene Chancen, aber passt diesen Filter an, um die Geschwindigkeit für geschlossene oder geschlossene verlorene Gelegenheiten zu ermitteln.
