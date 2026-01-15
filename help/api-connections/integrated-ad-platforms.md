---
description: Anleitung zu integrierten Anzeigenplattformen für Marketo Measure-Benutzende
title: Integrierte Anzeigenplattformen
exl-id: df30ee8a-8b07-4f14-94e8-cc482fca8b18
feature: APIs, Integration
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '1734'
ht-degree: 1%

---

# Integrierte Anzeigenplattformen {#integrated-ad-platforms}

[!DNL Marketo Measure] verfügt über API-Verbindungen zu Google AdWords, Microsoft BingAds, [!DNL Facebook] Ads und DoubleClick Campaign Manager. Über diese API-Verbindungen kann [!DNL Marketo Measure] Daten einfach abrufen und zusammen mit der externen Buyer-App an Ihr CRM übertragen. Es ist kein manuelles Hochladen von Kosten oder Daten erforderlich. Stattdessen müssen Ihre Konten einfach mit der [!DNL Marketo Measure]-App verbunden und autorisiert werden. [!DNL Marketo Measure] laden dann automatisch Ihre Marketing-Kosten von den Plattformen herunter und laden sie in die [!DNL Marketo Measure] App. Wenn Sie das automatische Tagging für AdWords, BingAds oder [!DNL Facebook] Ads aktivieren möchten, hängen [!DNL Marketo Measure] seine Parameter automatisch an die URLs Ihrer Anzeigen an.

## Verbinden von Anzeigenplattformen {#how-to-connect-ad-platforms}

Bevor wir uns mit den Besonderheiten jeder Plattform befassen, werden wir uns damit befassen, wie wir eines dieser Konten mit [!DNL Marketo Measure] verbinden. Melden Sie sich zuerst bei der [!DNL Marketo Measure] App an und navigieren Sie **[!UICONTROL die Option]** Einstellungen auf der Registerkarte **[!UICONTROL Mein Konto]** oben links im Bildschirm. Wählen Sie anschließend **[!UICONTROL Verbindungen]** im Abschnitt **[!UICONTROL Integrationen]** auf der linken Seite aus.

Wie in der Abbildung unten dargestellt, wird eine Schaltfläche zum Einrichten neuer Werbeverbindungen angezeigt.

![Wie in der Abbildung unten dargestellt, wird eine Schaltfläche angezeigt, mit der Sie Folgendes tun können](assets/bizible-guide-1.png)

Nachdem Sie auf die Schaltfläche [!UICONTROL Neue Anzeigenverbindung einrichten] geklickt haben, wird ein Fenster (siehe unten) mit vier Anzeigenverbindungstypen [!UICONTROL Verbindung] angezeigt. Klicken Sie auf Verbinden. Daraufhin wird ein weiteres Fenster angezeigt, in dem Sie nach Anmeldeinformationen gefragt werden. Geben Sie die Anmeldeinformationen ein und klicken Sie auf [!UICONTROL Autorisieren], um das Konto mit [!DNL Marketo Measure] zu verbinden.

![Klicken Sie nach dem Klicken auf die Schaltfläche Neue Anzeigenverbindung einrichten , a](../assets/marketo-engage-activities-05.png)

## Google AdWords {#google-adwords}

Wenn Sie Ihre Anzeigen in [!DNL Google AdWords] erstellen, sollten Sie Ihre Kampagnen auf eine dieser drei Arten taggen: durch manuelles Tagging, automatisches Tagging oder durch Erstellen einer Tracking-Vorlage. Das manuelle Tagging Ihrer AdWords-URL beruht darauf, dass Sie die Parameter am Ende der URLs der Anzeigen definieren und hinzufügen. Das manuelle Tagging ermöglicht es allen Nicht-Google-Plattformen, die von den Parametern erfassten Daten einfach zu lesen.

Die Tracking-Vorlage ist ein Tool, das Google bereitstellt, um die so genannten ValueTrack-Parameter hinzuzufügen. Sie funktionieren auf die gleiche Weise wie UTMs und andere Tagging-Parameter.

## Was passiert, wenn das automatische Tagging aktiviert ist? {#what-happens-when-auto-tagging-is-enabled}

[!DNL Marketo Measure] Sucht in Ihrem [!DNL AdWords]-Konto nach Tracking-Vorlagen:

* *Option A*: Tracking-Vorlage wurde gefunden. [!DNL Marketo Measure] fügt seine Parameter zur Vorlage hinzu.
* *Option B*: Es wurde eine Umleitung von Drittanbietern gefunden. Wenn in der Tracking-Vorlage eine Weiterleitung eines Drittanbieters gefunden wird, können [!DNL Marketo Measure] keine Maßnahmen ergreifen. Sie müssen die [!DNL Marketo Measure] Tags manuell zum Drittanbietersystem hinzufügen. Ein Beispiel für eine Umleitung von Drittanbietern wäre ein Tool zur Angebotsverwaltung wie Kenshoo oder Marin. Erfahren Sie mehr darüber, wie [Tools zur Angebotsverwaltung [!DNL Marketo Measure]](/help/api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

* *Option C*: Keine Tracking-Vorlage gefunden. [!DNL Marketo Measure] werden alle Ihre Werbeziel-URLs auf die [!DNL Marketo Measure] Parameter überprüft. Basierend auf dem Scan, wenn:
   * Es wurden Parameter gefunden: die Einrichtung ist abgeschlossen!
   * Parameter wurden nicht gefunden: [!DNL Marketo Measure] hängen ihre Parameter an das Ende der Werbeziel-URLs an. [!DNL Marketo Measure] hängt neue Anzeigen innerhalb von zwei Stunden nach ihrer Erstellung an. Beachten Sie, dass die Parameter nicht zu einer Vorlage hinzugefügt werden.

Erfahren Sie mehr über unsere [[!DNL AdWords] automatische Tagging-Funktion](/help/api-connections/understanding-marketo-measure-adwords-tagging.md){target="_blank"}.

## So aktivieren Sie [!DNL Marketo Measure] automatische Tagging für Adwords {#how-to-enable-marketo-measure-auto-tagging-for-adwords}

Bevor Sie [!DNL Marketo Measure] automatisches Tagging aktivieren **stellen Sie sicher, dass in Ihrem AdWords-Konto eine Tracking-Vorlage auf Konto-, Kampagnen- oder Anzeigengruppenebene aktiviert ist. Dies ist für jedes AdWords-Konto erforderlich, für das [!DNL Marketo Measure] automatische Tagging aktiviert ist.** Durch die Aktivierung einer Tracking-Vorlage wird verhindert, dass Daten zum Anzeigenleistungsverlauf verloren gehen. Beachten Sie, dass die Aktivierung von Tracking-Vorlagen auf Keyword-, Sitelink- oder Anzeigenebene dazu führt, dass die Anzeige den Prüfungs- und Genehmigungsprozess durchläuft und möglicherweise den Leistungsverlauf Ihrer Anzeigen neu startet. Wenn keine Tracking-Vorlage aktiviert ist, hängen [!DNL Marketo Measure] die [!DNL Marketo Measure] Tracking-Parameter direkt an die „Endgültige URL“ der Anzeige an, was auch zu Verlust der Daten zum Anzeigenverlauf führen kann.

Nachdem Sie über eine Tracking-Vorlage verfügen, befolgen Sie die nachstehenden Anweisungen, um [!DNL Marketo Measure] automatische Tagging zu aktivieren. Hinweis: [!DNL Marketo Measure] werden auch alle pausierten Anzeigen in Ihrem Konto automatisch taggen.

1. Melden Sie sich bei Ihrem [!DNL Marketo Measure] Konto unter [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} an.

1. Navigieren Sie [!UICONTROL Mein Konto] > [!UICONTROL Einstellungen] > [!UICONTROL Integrationen] > [!UICONTROL Verbindungen].

   ![1. Gehen Sie zu Einstellungen meines Kontos Integrationen Verbindungen.](assets/utilizing-connections-8.png)

1. Klicken Sie auf das Stiftsymbol neben dem AdWords-Konto, für das das automatische Tagging [!DNL Marketo Measure] ist.

   ![1. Klicken Sie auf das Stiftsymbol neben dem AdWords-Konto, das Folgendes bewirkt](assets/utilizing-connections-9.png)

1. Schalten Sie in der oberen rechten Ecke den Umschalter **[!UICONTROL Automatisches Tagging]** auf **[!UICONTROL Ja]**. Klicken Sie unten auf der Seite auf **[!UICONTROL Weitere Informationen]**, um das Textfeld zu erweitern, und klicken Sie auf **[!UICONTROL Speichern]**. Die Einrichtung des automatischen Tagging ist abgeschlossen.

   ![1. Stellen Sie in der oberen rechten Ecke den Schalter für automatisches Tagging auf ein](assets/utilizing-connections-10.png)

## Einrichten einer Tracking-Vorlage in AdWords mit [!DNL Marketo Measure] {#how-to-set-up-a-tracking-template-in-adwords-with-marketo-measure-parameters}

Denken Sie daran, dass Sie Tracking-Vorlagen auf der Ebene [!UICONTROL Konto], [!UICONTROL Kampagne] oder Anzeigengruppe in AdWords hinzufügen sollten. Wenn Sie Tracking-Vorlagen auf Keyword-, Sitelink- oder Anzeigenebene hinzufügen, muss Ihre Anzeige den Prüfungs- und Genehmigungsprozess durchlaufen, und Sie riskieren, den Leistungsverlauf Ihrer Anzeigen neu zu starten. Weitere Informationen zum [&#x200B; von Tracking-Vorlagen](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"}.

1. Melden Sie sich bei Ihrem [!DNL Google AdWords] Konto an.
1. Navigieren Sie [!UICONTROL &#x200B; Ansicht &#x200B;]Kampagnen“ in der linken Navigationsleiste
1. Navigieren Sie zu [!UICONTROL Einstellungen], auch in der linken Navigationsleiste
1. Schalten Sie in die Ansicht [!UICONTROL Kontoeinstellungen] oben um
1. Erweitern Sie den Abschnitt [!UICONTROL Tracking]
1. Fügen Sie eine der folgenden Textzeichenfolgen in die Tracking-Vorlage ein, um den Wert der Vorlage festzulegen:

   * Wenn Sie Fragezeichen in ALLEN URLs haben, verwenden Sie den folgenden URL-Text:

   `{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

   * Wenn keine Fragezeichen auf einer Ihrer URLs vorhanden sind, fügen Sie den folgenden URL-Text hinzu:

   `{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}*`

   Um Fehler beim manuellen Taggen von URLs zu vermeiden, wird in der Regel empfohlen, die UTM-Parameter automatisch zu generieren. Dabei muss es sich nicht um automatisches Tagging mit AdWords oder [!DNL Marketo Measure] handeln. Es gibt mehrere Tools, die den Prozess vereinfachen, indem die Parameter für die URL automatisch basierend auf den von Ihnen bereitgestellten Informationen generiert werden.

   >[!TIP]
   >
   >Wenn Sie den Fehler erhalten, dass die Tracking-Vorlage ungültig ist, löschen Sie Ihren Browser-Cache und versuchen Sie es erneut - dies löst oft das Problem.

## Automatisches Generieren von UTM-Tags für [!DNL Google AdWords] {#how-to-automatically-generate-utm-tags-for-google-adwords}

UTM-Tags können zunächst schwer zu erstellen sein, es stehen jedoch viele Tools zur Verfügung, mit denen sich URLs mit UTM-Parametern einfach erstellen lassen. Sie können eine der folgenden Ressourcen verwenden oder im Web nach weiteren Tools suchen. Beachten Sie, dass [!DNL Marketo Measure] mit diesen Plattformen und Tools keine Inhalte befürwortet oder garantiert.

**[!DNL Google URL]Builder**

Google URL Builder ist ein Standardwerkzeug zum Erstellen korrekt formatierter URLs mit UTM-Tags. Geben Sie die URL und den gewünschten Wert jedes Parameters ein und klicken Sie auf &quot;[!UICONTROL URL generieren]. Dies ist ein ideales Tool, wenn Sie nur über eine Handvoll URLs zum Taggen verfügen. Rufen Sie das Tool [hier](https://support.google.com/analytics/answer/1033867?hl=de){target="_blank"} auf.

**Von EpikOne generierte Google-Tabelle**

Diese Tabelle verfügt über eine Formel, die automatisch getaggte Ziel-URLs generiert. Dies ist ein großartiges Tool, wenn eine große Anzahl von Links getaggt werden muss. Zugriff auf die Tabelle [hier](https://spreadsheets.google.com/ccc?key=p7c_HKcmspSUfEYSO0gskKw&hl=en){target="_blank"}.

**RaffleCopter Link Tagging Tool**

Die von Rafflecopter erstellte Tabelle ist eine modifizierte Version [!DNL EpikOne's] Tabelle. Sie enthält auch eine Formel, die automatisch getaggte Ziel-Links generiert, die Sie verwenden können.

Jedes dieser Tools verfügt über detaillierte Anweisungen zum Verwenden und Ändern des Tools entsprechend Ihren Anforderungen. Das Tool ist verfügbar [hier](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"}.

**Effin Amazing UTM Builder**

Dieses Tool ist eine Chrome-Erweiterung, mit der Sie UTM-Tags schnell generieren können. Finde es [hier](https://chrome.google.com/webstore/detail/effin-amazing-utm-builder/eoaapiimcaimddnfhfnifgkinmpcbccp?hl=en){target="_blank"}.

## Bing-Werbeanzeigen {#bing-ads}

Bing Ads ist eine integrierte Plattform, mit der Sie das automatische Tagging für URLs aktivieren oder ein Tool eines Drittanbieters wie [!DNL Marketo Measure] zum Taggen von Anzeigen verwenden können. [!DNL Bing Ads] sind auch UTM-Parameter erforderlich.

Unsere Integration unterstützt die folgenden Anzeigentypen:

* Textanzeige
* Mobile-Anzeige
* Erweiterte Textanzeige


Die automatische Tagging-Funktion von Bing Ads fügt die folgenden UTM-Parameter hinzu:

* utm_source
* utm_medium
* utm_term

Durch das automatische Tagging von Bing-Anzeigen werden auch die folgenden benutzerdefinierten Parameter hinzugefügt:

`_bt={adid}`

Die Zeichenfolge würde wie folgt aussehen:

`{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`

Beachten Sie, dass Sie mit [!DNL Bing Ads] sogar noch mehr Parameter hinzufügen können, indem Sie deren benutzerdefinierte Tags in Ihren endgültigen URLs verwenden, um ggf. mehr Granularität zu erhalten.

Eine Tracking-Vorlage kann bei Bedarf verwendet werden, es ist jedoch nicht erforderlich, dass [!DNL Bing Ads] und [!DNL Marketo Measure] integriert werden. Dies liegt daran, dass [!DNL Bing] die Bearbeitung von Anzeigen ermöglicht, ohne den Verlauf zu ändern, sodass [!DNL Marketo Measure] die Ziel-URL aktualisieren können.

Das automatische Tagging sollte über [!DNL Marketo Measure] aktiviert werden, damit die benutzerdefinierten [!DNL Marketo Measure] automatisch angehängt werden können. Es besteht kein Risiko, den bisherigen Verlauf der Anzeigenleistung mit Bing Ads zu verlieren.

Besuchen Sie die [[!DNL Bing Ads]](https://advertise.bingads.microsoft.com/en-us/blog/post/august-2016/upgraded-urls-now-available-in-bing-ads-an-easier-way-to-manage-your-tracking-urls){target="_blank"}-Website, um weitere Informationen zum Hinzufügen von Tags auf ihrer Plattform zu erhalten.

## Facebook-Anzeigen {#facebook-ads}

Die [!DNL Marketo Measure] Integration mit [!DNL Facebook] ermöglicht das automatische Herunterladen von Anzeigeninformationen und das Tagging der URL mit ihren Parametern. [!DNL Marketo Measure] werden die Kampagnen- und Anzeigensatzinformationen über unser automatisches Tagging abrufen. Mit dem Anzeigensatz wird das Feld Anzeigengruppenname ausgefüllt. Weitere Informationen zum Einrichten von URL-Tags auf der [!DNL Facebook]-Plattform finden Sie auf der [!DNL Facebook] [Business](https://www.facebook.com/business/help/1016122818401732/?ref=u2u){target="_blank"}-Seite.

Bevor Sie das automatische Tagging mit [!DNL Facebook Ads] aktivieren, müssen Sie den vorherigen Leistungsverlauf als CSV exportieren. An dieser Stelle, wenn [!DNL Marketo Measure] Tags mit dem _bf-Parameter [!DNL Facebook Ads], liest [!DNL Facebook] die Anzeigen als brandneu und löscht den Leistungsverlauf. Daher ist es wichtig, einen Datensatz der vorherigen Leistung zu exportieren, wenn dies für Sie und Ihr Unternehmen von Wert ist.

Beachten Sie, dass Sie Ihr [!DNL Facebook]-Konto jederzeit mit der [!DNL Marketo Measure]-App verbinden können und keine Daten verloren gehen. Der Leistungsverlauf wird nur gelöscht, wenn das automatische Tagging aktiviert ist.

Weitere [&#x200B; zum Exportieren von &#x200B;](https://www.facebook.com/business/help/393890194130036){target="_blank"} Ad-Berichten finden [!DNL Facebook] in diesem Artikel auf Facebook .

## Gesponserte LinkedIn-Inhalte {#linkedin-sponsored-content}

Durch die LinkedIn-Integration können [!DNL Marketo Measure] Ziel-URLs mit [!DNL LinkedIn] gesponserten Inhalten taggen, was es [!DNL Marketo Measure] letztendlich ermöglicht, einen Benutzer durch seine gesamte Touchpoint-Journey zu verfolgen und die Aktivität wieder den spezifischen [!DNL LinkedIn] Campaign und Creative zuzuordnen. Dadurch erhalten Kundinnen und Kunden Einblicke in den ROI ihrer [!DNL LinkedIn]. [!DNL Marketo Measure] werden nach Kreativen mit einer eindeutigen [!DNL LinkedIn]-Freigabe suchen und am Ende einen `?_bl={creativeId}` Parameter hinzufügen.

Da [!DNL LinkedIn]-Freigaben über mehrere Kampagnen und Kreative hinweg verwendet werden können, bitten wir Kunden, vorhandene Kreative nicht zu kopieren/klonen/duplizieren, damit sie ihre Einzigartigkeit beibehalten können. Wenn Freigaben gefunden werden und nur auf einer Creative verwendet werden, können [!DNL Marketo Measure] die Freigabe wie besehen taggen, ohne dass Kreative oder Freigaben neu erstellt werden müssen. Der gesamte Werbeverlauf (Impressionen, Klicks, Freigaben) bleibt erhalten.

Sobald festgestellt wird, dass eine Freigabe für mehrere Kreative freigegeben ist, müssen [!DNL Marketo Measure] einen Prozess zum Anhalten, Kopieren und erneuten Taggen durchlaufen, um einen eindeutigen Satz zu erstellen. [!DNL Marketo Measure] werden die Live-Kreativen anhalten und archivieren. Das bedeutet, dass das Kreative mit den Impressionen, Klicks und Social Shares auch archiviert wird.

## Nicht integrierte Plattformen {#non-integrated-platforms}

Bei Plattformen, die nicht mit [!DNL Marketo Measure] integriert sind, kann die Funktion zum automatischen Tagging von [!DNL Marketo Measure] nicht verwendet werden. Die Parameter müssen manuell hinzugefügt werden.
