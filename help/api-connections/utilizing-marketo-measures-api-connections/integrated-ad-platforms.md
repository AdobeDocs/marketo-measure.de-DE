---
unique-page-id: 18874594
description: Integrierte Anzeigenplattformen - [!DNL Marketo Measure]
title: Integrierte Anzeigenplattformen
exl-id: df30ee8a-8b07-4f14-94e8-cc482fca8b18
feature: APIs, Integration
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '1675'
ht-degree: 0%

---

# Integrierte Anzeigenplattformen {#integrated-ad-platforms}

[!DNL Marketo Measure] verfügt über API-Verbindungen mit Google AdWords, Microsoft BingAds, [!DNL Facebook] Ads und DoubleClick Campaign Manager. Durch diese API-Verbindungen kann [!DNL Marketo Measure] Daten einfach abrufen und zusammen mit der externen Käufer-App an Ihr CRM-System pushen. Es ist kein manuelles Hochladen von Kosten oder Daten erforderlich. Stattdessen müssen Ihre Konten einfach mit der [!DNL Marketo Measure]-App verbunden und autorisiert werden. [!DNL Marketo Measure] lädt dann automatisch Ihre Marketingkosten von den Plattformen herunter und lädt sie in die [!DNL Marketo Measure] -App. Wenn Sie das automatische Tagging für AdWords-, BingAds- oder [!DNL Facebook]-Anzeigen aktivieren, hängt [!DNL Marketo Measure] seine Parameter automatisch an die URLs Ihrer Anzeigen an.

## Anleitung zum Verbinden von Anzeigenplattformen {#how-to-connect-ad-platforms}

Bevor wir uns mit den Besonderheiten der einzelnen Plattformen befassen, werden wir uns mit der Verbindung dieser Konten zu [!DNL Marketo Measure] befassen. Melden Sie sich zunächst bei der App [!DNL Marketo Measure] an und navigieren Sie zur Option **[!UICONTROL Einstellungen]** auf der Registerkarte **[!UICONTROL Mein Konto]** oben links im Bildschirm. Wählen Sie als Nächstes **[!UICONTROL Verbindungen]** im Abschnitt **[!UICONTROL Integrationen]** auf der linken Seite aus.

Wie in der Abbildung unten dargestellt, sehen Sie eine Schaltfläche zum Einrichten neuer Werbeverbindungen.

![](assets/2.png)

Nachdem Sie auf die Schaltfläche [!UICONTROL Neue Anzeigenverbindung einrichten] geklickt haben, wird ein Fenster (wie unten gezeigt) mit vier Symboltypen für Anzeige [!UICONTROL connect]angezeigt. Klicken Sie auf Verbinden . Daraufhin wird ein weiteres Fenster angezeigt, in dem Sie nach Anmeldeinformationen gefragt werden. Geben Sie die Anmeldeinformationen ein und klicken Sie auf [!UICONTROL Autorisieren] , um das Konto mit [!DNL Marketo Measure] zu verbinden.

![](assets/select-account-type.png)

## Google AdWords {#google-adwords}

Wenn Sie Ihre Anzeigen in [!DNL Google AdWords] erstellen, sollten Sie Ihre Kampagnen auf eine von drei Arten mit Tags versehen: manuelles Tagging, automatisches Tagging oder Erstellen einer Tracking-Vorlage. Das manuelle Tagging Ihrer AdWords-URL setzt voraus, dass Sie die Parameter definieren und am Ende der Anzeigen-URLs hinzufügen. Das manuelle Tagging ermöglicht es jeder Nicht-Google-Plattform, die von den Parametern erfassten Daten einfach zu lesen.

Die Tracking-Vorlage ist ein Tool, das Google bereitstellt, um die so genannten ValueTrack-Parameter hinzuzufügen. Sie funktionieren auf die gleiche Weise wie UTMs und andere Tagging-Parameter.

## Was passiert, wenn automatisches Tagging aktiviert ist? {#what-happens-when-auto-tagging-is-enabled}

[!DNL Marketo Measure] Suchvorgänge nach Tracking-Vorlagen in Ihrem [!DNL AdWords]-Konto:

* *Option A*: Tracking-Vorlage gefunden. [!DNL Marketo Measure] fügt seine Parameter zur Vorlage hinzu.
* *Option B*: Es wird eine Umleitung von Drittanbietern gefunden. Wenn eine Umleitung eines Drittanbieters in der Tracking-Vorlage gefunden wird, kann [!DNL Marketo Measure] keine Aktion ausführen. Sie müssen die [!DNL Marketo Measure] -Tags manuell zum Drittanbietersystem hinzufügen. Ein Beispiel für eine Umleitung von Drittanbietern wäre ein Angebotsmanagement-Tool wie Kenshoo oder Marin. Erfahren Sie mehr darüber, wie sich [Tools zur Angebotsverwaltung auf  [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"} auswirken.

* *Option C*: Es wurde keine Tracking-Vorlage gefunden. [!DNL Marketo Measure] überprüft alle Ihre Anzeigenziel-URLs auf die Parameter [!DNL Marketo Measure]. Basierend auf der Prüfung, wenn:
   * Parameter werden gefunden: Das Setup ist abgeschlossen!
   * Parameter werden nicht gefunden: [!DNL Marketo Measure] hängt seine Parameter an das Ende der Anzeigenziel-URLs an. [!DNL Marketo Measure] fügt neue Anzeigen innerhalb von zwei Stunden nach ihrer Erstellung hinzu. Beachten Sie, dass die Parameter nicht zu einer Vorlage hinzugefügt werden.

Erfahren Sie mehr über unsere [[!DNL AdWords] Funktion zum automatischen Taggen](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md){target="_blank"}.

## So aktivieren Sie das automatische Tagging für AdWords [!DNL Marketo Measure] {#how-to-enable-marketo-measure-auto-tagging-for-adwords}

Bevor Sie das automatische Tagging von [!DNL Marketo Measure] aktivieren, stellen Sie sicher, dass in Ihrem Adwords-Konto auf Konto-, Kampagnen- oder Anzeigengruppenebene eine Tracking-Vorlage aktiviert ist. **Dies ist für jedes Adwords -Konto erforderlich, für das die automatische Tagging mit [!DNL Marketo Measure] aktiviert ist.** Durch die Aktivierung einer Tracking-Vorlage wird jeder Verlust von Daten zum Anzeigenleistungsverlauf verhindert. Beachten Sie, dass die Aktivierung von Tracking-Vorlagen auf Keyword-, Sitelink- oder Anzeigenebene dazu führt, dass die Anzeige den Review- und Genehmigungsprozess durchläuft und möglicherweise den Leistungsverlauf Ihrer Anzeigen neu startet. Wenn überhaupt keine Tracking-Vorlage aktiviert ist, hängt [!DNL Marketo Measure] die Tracking-Parameter [!DNL Marketo Measure] direkt an die &quot;endgültige URL&quot;der Anzeige an, was auch zum Verlust von Daten zum Anzeigenverlauf führen kann.

Nachdem Sie eine Tracking-Vorlage eingerichtet haben, folgen Sie den unten stehenden Anweisungen, um das automatische Tagging von [!DNL Marketo Measure] zu aktivieren. Hinweis: [!DNL Marketo Measure] markiert auch alle ausgesetzten Anzeigen in Ihrem Konto automatisch.

1. Melden Sie sich bei Ihrem [!DNL Marketo Measure] -Konto unter [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} an.

1. Wechseln Sie zu [!UICONTROL Mein Konto] > [!UICONTROL Einstellungen] > [!UICONTROL Integrationen] > [!UICONTROL Verbindungen].

   ![](assets/4.png)

1. Klicken Sie auf das Bleistiftsymbol neben dem Adwords-Konto, für das die automatische Tagging mit [!DNL Marketo Measure] aktiviert wird.

   ![](assets/5.png)

1. Umschalten Sie oben rechts den Schalter **[!UICONTROL Autotagging]** auf **[!UICONTROL Ja]**. Klicken Sie unten auf der Seite auf **[!UICONTROL Mehr erfahren]** , um das Textfeld zu erweitern, und klicken Sie auf **[!UICONTROL Speichern]**. Die Einrichtung des automatischen Tagging ist abgeschlossen.

   ![](assets/6.png)

## Einrichten einer Tracking-Vorlage in AdWords mit [!DNL Marketo Measure]-Parametern {#how-to-set-up-a-tracking-template-in-adwords-with-marketo-measure-parameters}

Beachten Sie, dass Sie Tracking-Vorlagen auf der Ebene [!UICONTROL Konto], [!UICONTROL Kampagne] oder Anzeigengruppe in AdWords hinzufügen sollten. Wenn Sie Tracking-Vorlagen zur Suchbegriff-, Sitelink- oder Anzeigenebene hinzufügen, muss Ihre Anzeige den Review- und Genehmigungsprozess durchlaufen und riskieren, den Leistungsverlauf Ihrer Anzeigen neu zu starten. Erfahren Sie mehr über [Erstellen von Tracking-Vorlagen](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"}.

1. Melden Sie sich bei Ihrem [!DNL Google AdWords] -Konto an.
1. Navigieren Sie in der linken Navigationsleiste zu Ihrer Ansicht [!UICONTROL Kampagnen] .
1. Navigieren Sie zu &quot;[!UICONTROL Einstellungen]&quot;, auch in der linken Navigationsleiste.
1. Wechsel zur Ansicht &quot;[!UICONTROL Kontoeinstellungen]&quot; oben
1. Erweitern Sie den Abschnitt &quot;[!UICONTROL Tracking]&quot;.
1. Fügen Sie eine der folgenden Textzeichenfolgen in die Tracking-Vorlage ein, um den Wert der Vorlage festzulegen:

   * Verwenden Sie den folgenden URL-Text, wenn Sie Fragezeichen in all Ihren URLs haben:

   `{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

   * Wenn keine Ihrer URLs Fragezeichen aufweisen, fügen Sie den folgenden URL-Text hinzu:

   `{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}*`

   Um zu verhindern, dass beim manuellen Taggen Ihrer URLs Fehler auftreten, wird in der Regel empfohlen, die UTM-Parameter automatisch zu generieren. Dies bedeutet nicht, dass AdWords- oder [!DNL Marketo Measure]-Parameter automatisch getaggt werden müssen. Es gibt mehrere Tools, die den Prozess vereinfachen, indem die Parameter für die URL basierend auf den von Ihnen bereitgestellten Informationen automatisch generiert werden.

   >[!TIP]
   >
   >Wenn Sie eine Fehlermeldung erhalten, dass die Tracking-Vorlage ungültig ist, versuchen Sie, Ihren Browser-Cache zu leeren und es erneut zu versuchen. Dadurch wird das Problem häufig behoben.

## Automatisches Generieren von UTM-Tags für [!DNL Google AdWords] {#how-to-automatically-generate-utm-tags-for-google-adwords}

Die Erstellung von UTM-Tags kann zunächst schwierig erscheinen, es stehen jedoch viele Tools zur Verfügung, um URLs mit UTM-Parametern einfach zu erstellen. Sie können eine der folgenden Ressourcen verwenden oder im Internet nach weiteren Tools suchen. Beachten Sie, dass [!DNL Marketo Measure] bei diesen Plattformen und Tools keine Aktionen unterstützt oder garantiert.

**[!DNL Google URL]Builder**

Google URL Builder ist ein Standardwerkzeug zum Erstellen korrekt formatierter URLs mit UTM-Tags. Geben Sie die URL und den gewünschten Wert für jeden Parameter ein und klicken Sie auf &quot;[!UICONTROL URL generieren]&quot;. Dies ist ein ideales Tool zur Verwendung, wenn Sie nur über eine Handvoll von URLs verfügen, die mit Tags versehen werden sollen. Rufen Sie das Tool [hier](https://support.google.com/analytics/answer/1033867?hl=de){target="_blank"} auf.

**Von EpikOne generiertes Google-Arbeitsblatt**

Diese Tabelle enthält eine Formel, mit der automatisch getaggte Ziel-URLs generiert werden. Dieses Tool eignet sich hervorragend, wenn eine große Anzahl von Links mit Tags versehen werden muss. Rufen Sie die Tabelle [hier](https://spreadsheets.google.com/ccc?key=p7c_HKcmspSUfEYSO0gskKw&amp;hl=en){target="_blank"} auf.

**Rafflecopter Link Tagging Tool**

Die von Rafflecopter erstellte Tabelle ist eine modifizierte Version der [!DNL EpikOne's] -Tabelle. Es enthält auch eine Formel, mit der Sie automatisch getaggte Ziel-Links generieren, die Sie verwenden können.

Jedes dieser Tools verfügt über eine detaillierte Anleitung zur Verwendung und Anpassung an Ihre Anforderungen. Das Tool ist [hier](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} verfügbar.

**Auswirkungen von erstaunlichem UTM Builder**

Dieses Tool ist eine Chrome-Erweiterung, mit der Sie schnell UTM-Tags generieren können. Suchen Sie ihn [hier](https://chrome.google.com/webstore/detail/effin-amazing-utm-builder/eoaapiimcaimddnfhfnifgkinmpcbccp?hl=en){target="_blank"}.

## Bing-Werbeanzeigen {#bing-ads}

Bing Ads ist eine integrierte Plattform, mit der Sie automatisches Tagging für URLs aktivieren oder ein Tool von Drittanbietern wie [!DNL Marketo Measure] verwenden können, um Anzeigen zu taggen. [!DNL Bing Ads] verlässt sich auch auf UTM-Parameter.

Unsere Integration unterstützt die folgenden Anzeigentypen:

* Textwerbung
* Mobile Ad
* Erweiterte Textanzeige


Die Funktion zum automatischen Tagging von Bing Ads fügt die folgenden UTM-Parameter hinzu:

* Utm_source
* Utm_medium
* Utm_term

Durch das automatische Tagging von Bing Ads wird auch der folgende benutzerdefinierte Parameter hinzugefügt:

`_bt={adid}`

Die Zeichenfolge würde wie folgt aussehen:

`{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`

Beachten Sie, dass Sie mit [!DNL Bing Ads] noch mehr Parameter hinzufügen können, indem Sie ihre benutzerdefinierten Tags in Ihren endgültigen URLs verwenden, um bei Bedarf eine größere Granularität zu erzielen.

Eine Tracking-Vorlage kann bei Bedarf verwendet werden, die Integration von [!DNL Bing Ads] und [!DNL Marketo Measure] ist jedoch nicht erforderlich. Dies liegt daran, dass [!DNL Bing] die Bearbeitung von Anzeigen erlaubt, ohne den Verlauf zu ändern, sodass [!DNL Marketo Measure] die Ziel-URL aktualisieren kann.

Das automatische Tagging sollte über [!DNL Marketo Measure] aktiviert werden, damit die benutzerdefinierten [!DNL Marketo Measure] Parameter automatisch angehängt werden können. Es besteht kein Risiko, dass mit Bing Ads vergangene Anzeigen-Performance-Verläufe verloren gehen.

Weitere Informationen zum Hinzufügen von Tags zu ihrer Plattform finden Sie auf der Website [[!DNL Bing Ads]](https://advertise.bingads.microsoft.com/en-us/blog/post/august-2016/upgraded-urls-now-available-in-bing-ads-an-easier-way-to-manage-your-tracking-urls){target="_blank"} .

## Facebook-Anzeigen {#facebook-ads}

Durch die Integration von [!DNL Marketo Measure] mit [!DNL Facebook] können Anzeigeninformationen automatisch heruntergeladen und die URL mit ihren Parametern getaggt werden. [!DNL Marketo Measure] ruft die Informationen zu Kampagne und Anzeigenset über unser automatisches Tagging ab. Das Anzeigenset füllt unser Feld Anzeigengruppenname . Weitere Informationen zum Einrichten von URL-Tags auf der [!DNL Facebook]-Plattform finden Sie auf der Seite [!DNL Facebook] [business](https://www.facebook.com/business/help/1016122818401732/?ref=u2u){target="_blank"} .

Bevor Sie das automatische Tagging mit [!DNL Facebook Ads] aktivieren, müssen Sie den vorherigen Leistungsverlauf als CSV-Datei exportieren. Wenn [!DNL Marketo Measure] an dieser Stelle [!DNL Facebook Ads] mit dem Parameter _bf markiert, liest [!DNL Facebook] die Anzeigen als brandneu und löscht den Leistungsverlauf. Daher ist es wichtig, einen Datensatz der vorherigen Leistung zu exportieren, wenn dies für Sie und Ihr Unternehmen von Nutzen ist.

Beachten Sie, dass Sie Ihr [!DNL Facebook]-Konto jederzeit mit der [!DNL Marketo Measure]-App verbinden können und keine Daten verloren gehen. Der Leistungsverlauf wird nur bei aktiviertem automatischem Tagging gelöscht.

Weitere Informationen zum Exportieren von [!DNL Facebook] Anzeigenberichten finden Sie in [diesem Artikel](https://www.facebook.com/business/help/393890194130036){target="_blank"} aus Facebook.

## LinkedIn-gesponserte Inhalte {#linkedin-sponsored-content}

Die LinkedIn-Integration ermöglicht es [!DNL Marketo Measure], Ziel-URLs für [!DNL LinkedIn] gesponserte Inhalte zu taggen, wodurch [!DNL Marketo Measure] einem Benutzer letztendlich durch die gesamte Touchpoint-Journey folgen und die Aktivität wieder der jeweiligen [!DNL LinkedIn]-Kampagne und Creative zuordnen kann. Dies bietet Kunden Einblicke in den ROI ihrer [!DNL LinkedIn] -Aktivität. [!DNL Marketo Measure] sucht nach Kreativen mit einer eindeutigen [!DNL LinkedIn]-Freigabe und fügt am Ende einen `?_bl={creativeId}` -Parameter hinzu.

Da [!DNL LinkedIn] &quot;Teilen&quot;-Klicks für mehrere Kampagnen und kreative Inhalte verwendet werden können, bitten wir Kunden, vorhandene Kreative nicht zu kopieren/zu klonen/zu duplizieren, damit sie ihre Einzigartigkeit beibehalten können. Wenn &quot;Teilen&quot;-Klicks gefunden werden und erkannt werden, dass sie nur auf einem Kreativelement verwendet werden, kann [!DNL Marketo Measure] die Freigabe so taggen, wie es ist, ohne dass kreative Inhalte oder &quot;Teilen&quot;-Klicks neu erstellt werden müssen. Außerdem bleiben alle Anzeigen-Verläufe (Impressionen, Klicks, &quot;Teilen&quot;-Klicks) erhalten.

Sobald festgestellt wird, dass eine Freigabe für mehrere Kreative freigegeben ist, muss [!DNL Marketo Measure] den Prozess zum Anhalten, Kopieren und erneuten Taggen durchlaufen, um einen eindeutigen Satz zu erstellen. [!DNL Marketo Measure] hält Live-Kreative an und archiviert sie. Das bedeutet, dass auch die Kreativelemente mit den Impressionen, Klicks und Teilen aus sozialen Netzwerken archiviert werden.

## Nicht integrierte Plattformen {#non-integrated-platforms}

Bei Plattformen, die nicht mit [!DNL Marketo Measure] integriert sind, kann die Funktion für das automatische Tagging von [!DNL Marketo Measure] nicht verwendet werden. Die Parameter müssen manuell hinzugefügt werden.
