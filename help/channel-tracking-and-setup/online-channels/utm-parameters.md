---
unique-page-id: 18874606
description: UTM-Parameter - [!DNL Marketo Measure] - Produktdokumentation
title: UTM-Parameter
exl-id: 2b20f3c4-1f39-4ac5-bad1-cb1d630d60e9
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 0%

---

# UTM-Parameter {#utm-parameters}

Das Tagging von URLs ist eine einfache und effektive Möglichkeit, Daten zu Ihren digitalen Marketingbemühungen zu erfassen. Es ist der Prozess des Hinzufügens von Parametern zum Ende von URLs, die Daten erfassen und aufzeichnen. Die am häufigsten verwendeten Parameter sind Urchin Tracking Module (UTMs), die von Google unterstützt werden. Es stehen fünf wichtige UTMs-Parameter zur Verfügung: Medium, Quelle, Kampagne, Inhalt und Begriff. Diese werden im nächsten Abschnitt ausführlicher erläutert.

UTM-Parameter können manuell zu URLs hinzugefügt oder durch automatisches Tagging mit bestimmten Plattformen wie z. B. AdWords angehängt werden. Das automatische Tagging automatisiert das Anhängen von Parametern an URLs. Es gibt auch die Option [URL-Builder](https://ga-dev-tools.appspot.com/campaign-url-builder/){target=&quot;_blank&quot;} verwenden, um Tagging-URLs manuell zu beschleunigen. Mit einem URL-Builder müssen Sie einfach die Werte für die einzelnen Parameter angeben, und der Builder formatiert die URL für Sie.

## Was sind UTM-Parameter? {#what-are-utm-parameters}

Um zu verstehen, wie UTM-Parameter funktionieren, sehen wir uns eine typische URL ohne UTMs an:

`http://www.adobe.com`

Sehen wir uns nun eine URL mit UTMs an:

`http://www.adobe.com?utm_medium=socialmedia&utm_source =facebook&utm_campaign=seasonal-sale&utm_content=photo-400x700px`

Wie Sie sehen können, enthält der zweite Link viel mehr Text. UTM-Parameter folgen immer der Domäne der obersten Ebene (.com in diesem Beispiel) und beginnen mit einem Fragezeichen. Danach spielt die Reihenfolge der Parameter keine Rolle, es wird jedoch empfohlen, eine konsistente Benennungskonvention einzuhalten. Um jedes UTM zu trennen, müssen zwischen den einzelnen Parametern kaufmännische Und-Zeichen gesetzt werden. Nun können wir detaillierter darüber informieren, was jeder Parameter darstellt.

Informationen zu [Best Practices zum Einrichten von UTM-Parametern](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md).

**utm_medium**

* Medium identifiziert die Fahrzeuge, die Sie zum Inverkehrbringen Ihres Unternehmens verwenden.
* Sie beantwortet die Frage: &quot;Wie kommen sie zu dir?&quot;
* Er gibt den Kanal der höchsten Ebene an.
* Soziale Medien, E-Mails, organische Suche und gebührenpflichtige Suche sind Beispiele für potenzielle mittlere Werte.
* Dieser Parameter ordnet Daten dem [!DNL Marketo Measure] Feld &quot;Mittel&quot;.
* _[!DNL Marketo Measure]Best Practice:_ Verwenden Sie dieses Feld nicht, um einen Unterkanal aufzurufen. Andernfalls kann es bei der Erstellung von Berichten für den eigentlichen Kanal zu Problemen kommen. Verwenden Sie ihn zur Identifizierung Ihres Marketing-Fahrzeugs oder -Kanals. Wenn Sie z. B. E-Mails zur Vermarktung Ihres Produkts verwenden möchten, ist das Medium E-Mail.

**utm_source**

* Die Quelle identifiziert den Unterkanal, der die Quelle Ihres Traffics darstellt.
* Sie beantwortet die Frage: &quot;Woher kommt diese Person?&quot;
* In einem Social-Media-Beispiel ist die verwendete Social-Media-Plattform die Quelle des Traffics.
   * In diesem Beispiel [!DNL Facebook] ist der Quellwert. Weitere Beispiele sind Twitter und Instagram. Wenn das UTM-Medium [!DNL Paid Search]andererseits könnte die UTM-Quelle AdWords oder BingAds sein.

* Dieser Parameter wird dem [!DNL Marketo Measure] Feld &quot;Touchpoint-Quelle&quot;in SFDC.
* _[!DNL Marketo Measure]Best Practice:_ Dieser Parameter verfolgt die Quelle Ihres Traffics, sodass es nicht zur Angabe des Anzeigentyps geeignet ist, z. B. Retargeting, Sponsored usw. Sie eignet sich am besten zur Verfolgung des Unterkanals auf höherer Ebene. Denken Sie daran, Sie beantworten die Frage &quot;Woher kommt mein Traffic?&quot; Sie suchen den Referrer. In diesem Beispiel ist die UTM-Quelle der Ort, an dem sich Ihre Anzeige befindet (nicht die tatsächliche Webseite, da diese automatisch außerhalb der Tags verfolgt wird). Wenn Sie eine Drip-E-Mail-Kampagne verfolgen, ist die Quelle drip email .

**utm_campaign**

* Campaign dient zur Identifizierung einer bestimmten Marketing-Kampagne.
* Sie beantwortet die Frage: &quot;Warum kommen sie zu dir?&quot;
* Verwenden Sie dieses Tag, um den Namen der Anzeigenkampagne so zu kennzeichnen, wie er in [!DNL Google AdWords] oder [!DNL BingAds]oder um den Namen anzugeben, mit dem Sie die Kampagne intern identifizieren. Sie können dieses Tag sogar verwenden, um andere Informationen wie Geolocation oder Werbenetzwerk anzugeben.
* Dieser Parameter wird dem [!DNL Marketo Measure] &quot;Feld für Anzeigenkampagnennamen&quot;in SFDC.
* _[!DNL Marketo Measure]Best Practice_: Vermeiden Sie bei der Bestimmung von Kampagnennamen die Verwendung von Satzzeichen oder Leerzeichen zwischen den Wörtern, da deren Verwendung zu Fehlern bei der Browserkodierung führen kann. Verwenden Sie stattdessen Unterstriche, um optimale Ergebnisse zu erzielen.

**utm_content**

* Verwenden Sie den Parameter &quot;UTM Content&quot;, wenn Sie mehr als ein auf einer Webseite vorhandenes Marketingelement verfolgen möchten. Wenn Sie beispielsweise über die Schaltfläche &quot;Demo anfordern&quot;und die Schaltfläche &quot;Für unseren wöchentlichen Newsletter anmelden&quot;verfügen und wissen möchten, welche die meisten Traffic generiert, benennen Sie jede Person und verwenden Sie ein UTM-Inhalts-Tag, um sie zu verfolgen. Der Name jedes &quot;Inhalts&quot;-Elements ist der Wert des Tags.
* Dieser Parameter wird dem [!DNL Marketo Measure] Feld &quot;Anzeigeninhalt&quot;in SFDC.
* _[!DNL Marketo Measure]Best Practice_: Dies ist ein optionaler Wert, aber [!DNL Marketo Measure] empfiehlt die Verwendung. Dieses Tag ist mit dem Titel der Anzeige oder des Marketingelements verknüpft, die/das Sie verfolgen möchten. Wenn Sie eine Bildanzeige verwenden, stellen Sie sicher, dass Sie die Abmessungen des Bildes in den Titel schreiben.

**utm_term**

* Der Begriff ähnelt dem Parameter &quot;UTM Content&quot;. Term eignet sich hervorragend zur Identifizierung von Suchbegriffen in Anzeigen für gebührenpflichtige Kampagnen. Wenn Sie die Funktion zum automatischen Taggen verwenden, geschieht dies für Sie. Wenn Sie die Funktion zum automatischen Tagging Ihrer Anzeigenplattform nicht verwenden, fügen Sie alle Suchbegriffe, die Sie verfolgen möchten, sorgfältig hinzu.
* Dieser Parameter wird dem [!DNL Marketo Measure] Feld &quot;Schlüsselworttext&quot;in SFDC.
* _[!DNL Marketo Measure]Best Practice_: Das UTM-Term-Tag ist optional, eignet sich aber hervorragend für das Tracking von Keywords. Überprüfen Sie die Rechtschreibung und vermeiden Sie die Verwendung von Sonderzeichen. Wenn mehr als ein Wort benötigt wird, versuchen Sie, Unterstriche oder überhaupt keine Leerzeichen zu verwenden.

Jeder Parameter erfasst Informationen, die für den zugewiesenen Wert relevant sind. Der Wert jedes Tags ermöglicht es Ihnen, alle Ihre digitalen Kampagnen zu verfolgen und zu sortieren und die Fragen zu beantworten: Wo, wie und warum?

Im Folgenden finden Sie eine Grafik der UTM-Parameter [!DNL Marketo Measure] analysiert und das entsprechende Touchpoint-Feld, an das sie gebunden sind:

| **UTM-Parameter** | **Entsprechende [!DNL Marketo Measure] Feld** |
|---|---|
| utm_medium | Mittel |
| utm_source | Touchpoint Quelle |
| utm_campaign | Anzeigenkampagnenname |
| utm_content | Anzeigeninhalt |
| utm_term | Suchbegrifftext |
