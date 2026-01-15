---
description: UTM-Parameteranleitung für Marketo Measure-Benutzende
title: UTM-Parameter
exl-id: 2b20f3c4-1f39-4ac5-bad1-cb1d630d60e9
feature: UTM Parameters
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '933'
ht-degree: 91%

---

# UTM-Parameter {#utm-parameters}

Das Tagging von URLs ist eine einfache und effektive Möglichkeit, Daten zu Ihren digitalen Marketing-Maßnahmen zu erfassen. Es geht dabei um den Prozess des Hinzufügens von Parametern am Ende von URLs, die Daten erfassen und aufzeichnen. Die am häufigsten verwendeten Parameter sind Urchin Tracking Modules (UTMs), die von Google unterstützt werden. Es stehen fünf wichtige UTMs-Parameter zur Verfügung: Medium, Quelle, Kampagne, Inhalt und Begriff. Diese werden im nächsten Abschnitt ausführlicher erläutert.

UTM-Parameter können manuell zu URLs hinzugefügt oder durch automatisches Tagging mit bestimmten Plattformen wie z. B. AdWords angehängt werden. Das automatische Tagging automatisiert das Anhängen von Parametern an URLs. Es gibt auch die Option von [URL Builders](https://ga-dev-tools.web.app/campaign-url-builder/){target="_blank"}, das Tagging von URLs manuell zu beschleunigen. Mit einem URL-Builder geben Sie einfach die Werte an, die für jeden Parameter verwendet werden sollen, und der Builder formatiert die URL für Sie.

## Was sind UTM-Parameter? {#what-are-utm-parameters}

Um zu verstehen, wie UTM-Parameter funktionieren, sehen wir uns eine typische URL ohne UTMs an:

`http://www.adobe.com`

Sehen wir uns nun eine URL mit UTMs an:

`http://www.adobe.com?utm_medium=socialmedia&utm_source =facebook&utm_campaign=seasonal-sale&utm_content=photo-400x700px`

Der zweite Link enthält mehr Text. UTM-Parameter folgen immer der Domain der obersten Ebene (.com in diesem Beispiel) und beginnen mit einem Fragezeichen. Danach spielt die Reihenfolge der Parameter keine Rolle, es wird jedoch empfohlen, eine konsistente Benennungskonvention einzuhalten. Um jedes UTM zu trennen, müssen zwischen den einzelnen Parametern kaufmännische Und-Zeichen (&amp;) gesetzt werden. Nun können wir detaillierter darauf eingehen, was jeder Parameter darstellt.

Informationen zu [Best Practices beim Einrichten von UTM-Parametern](/help/channel-tracking-and-setup/best-practices-for-setting-up-utm-parameters.md).

**utm_medium**

* Medium gibt an, mit welchen Mitteln Sie Ihr Unternehmen vermarkten.
* Es beantwortet die Frage: &quot;Wie kommen sie zu dir?&quot;
* Es gibt den Kanal der höchsten Ebene an.
* Social Media, E-Mails, organische Suche und gebührenpflichtige Suche sind Beispiele für potenzielle Medium-Werte.
* Dieser Parameter ordnet Daten dem [!DNL Marketo Measure]-Feld &quot;Medium“ zu.
* _[!DNL Marketo Measure] Best Practice :_Verwenden Sie dieses Feld nicht, um einen Unterkanal aufzurufen. Andernfalls kann es zu Problemen kommen, Berichte über den tatsächlichen Kanal zu erstellen. Verwenden Sie es, um Ihr Marketinginstrument oder Ihren Kanal zu identifizieren. Wenn Sie z. B. E-Mails zur Vermarktung Ihres Produkts verwenden möchten, ist das Medium E-Mail.

**utm_source**

* Die Quelle identifiziert den Unterkanal, der die Quelle Ihres Traffics darstellt.
* Sie beantwortet die Frage: &quot;Woher kommt diese Person?&quot;
* In einem Social-Media-Beispiel ist die verwendete Social-Media-Plattform die Quelle des Traffics.
   * In diesem Beispiel ist [!DNL Facebook] der Quellwert. Weitere Beispiele sind Twitter und Instagram. Wenn andererseits das UTM-Medium [!DNL Paid Search] ist, könnte die UTM-Quelle AdWords oder BingAds sein.

* Dieser Parameter wird dem [!DNL Marketo Measure]-Feld &quot;Touchpoint-Quelle“ in SFDC zugeordnet.
* _[!DNL Marketo Measure] Best Practice :_Dieser Parameter verfolgt die Quelle Ihres Traffics. Daher ist seine Verwendung zur Angabe des Anzeigentyps nicht geeignet, z. B. Retargeting, gesponsert usw. Er eignet sich am besten zur Verfolgung des Unterkanals auf höherer Ebene. Denken Sie daran, Sie beantworten die Frage &quot;Woher kommt mein Traffic?&quot; Sie suchen den Referrer. In diesem Beispiel ist die UTM-Quelle der Ort, an dem sich Ihre Anzeige befindet (nicht die tatsächliche Webseite, da diese automatisch außerhalb der Tags nachverfolgt wird). Wenn Sie eine Drip-E-Mail-Kampagne verfolgen, ist die Quelle drip email.

**utm_campaign**

* Kampagne dient zur Identifizierung einer bestimmten Marketing-Kampagne.
* Es beantwortet die Frage: &quot;Warum kommen sie zu dir?&quot;
* Verwenden Sie dieses Tag, um den Namen der Anzeigenkampagne so zu kennzeichnen, wie er in [!DNL Google AdWords] oder [!DNL BingAds] vorhanden ist, oder um den Namen anzugeben, mit dem Sie die Kampagne intern identifizieren. Sie können dieses Tag sogar verwenden, um andere Informationen wie Geolocation oder den Typ des Werbenetzwerks anzugeben.
* Dieser Parameter wird dem [!DNL Marketo Measure] &quot;Feld für Anzeigenkampagnennamen&quot; in SFDC zugeordnet.
* _[!DNL Marketo Measure]Best Practice_: Vermeiden Sie bei der Bestimmung von Kampagnennamen die Verwendung von Satzzeichen oder Leerzeichen zwischen den Wörtern, da deren Verwendung zu Fehlern bei der Browserkodierung führen kann. Verwenden Sie stattdessen Unterstriche, um optimale Ergebnisse zu erzielen.

**utm_content**

* Verwenden Sie den Parameter &quot;UTM Content&quot;, wenn Sie mehr als ein auf einer Web-Seite vorhandenes Marketing-Element verfolgen möchten. Wenn Sie beispielsweise über die Schaltfläche &quot;Demo anfordern&quot;und die Schaltfläche &quot;Für unseren wöchentlichen Newsletter anmelden&quot; verfügen und wissen möchten, welche den meisten Traffic generiert, benennen Sie jede Person und verwenden Sie ein UTM-Inhalts-Tag, um sie nachzuverfolgen. Der Name jedes &quot;Inhalts&quot;-Elements ist der Wert des Tags.
* Dieser Parameter wird dem [!DNL Marketo Measure] Feld &quot;Anzeigeninhalt“ in SFDC zugeordnet.
* _[!DNL Marketo Measure]Best Practice_: Dies ist ein optionaler Wert, aber [!DNL Marketo Measure] empfiehlt, ihn zu verwenden. Dieser Tag ist mit dem Titel der Anzeige oder des Marketing-Artikels verknüpft, die bzw. den Sie verfolgen möchten. Wenn Sie eine Bildanzeige verwenden, stellen Sie sicher, dass Sie die Abmessungen des Bildes in den Titel schreiben.

**utm_term**

* Der Begriff ähnelt dem Parameter &quot;UTM Content&quot;. Begriff eignet sich hervorragend zur Identifizierung von Suchbegriffen in Anzeigen für gebührenpflichtige Kampagnen. Wenn Sie die Funktion zum automatischen Taggen verwenden, wird dies für Sie getan. Wenn Sie die Funktion zum automatischen Taggen Ihrer Anzeigenplattform nicht verwenden, fügen Sie alle Suchbegriffe, die Sie verfolgen möchten, sorgfältig hinzu.
* Dieser Parameter wird dem [!DNL Marketo Measure]-Feld &quot;Keywordtext&quot;in SFDC zugeordnet.
* _[!DNL Marketo Measure]Best Practice_: Das UTM-Term-Tag ist optional, eignet sich aber hervorragend zur Nachverfolgung von Schlüsselwörtern. Überprüfen Sie die Rechtschreibung und vermeiden Sie die Verwendung von Sonderzeichen. Wenn mehr als ein Wort benötigt wird, versuchen Sie, Unterstriche oder überhaupt keine Leerzeichen zu verwenden.

Jeder Parameter erfasst Informationen, die für den zugewiesenen Wert relevant sind. Der Wert jedes Tags ermöglicht es Ihnen, alle Ihre digitalen Kampagnen zu verfolgen und zu sortieren und die Fragen zu beantworten: Wo, wie und warum?

Im Folgenden finden Sie eine Grafik der UTM-Parameter, die [!DNL Marketo Measure] analysiert, und des entsprechenden Touchpoint-Felds, an das sie gebunden sind:

| **UTM-Parameter** | **Entsprechendes [!DNL Marketo Measure]-Feld** |
|---|---|
| utm_medium | Medium |
| utm_source | Touchpoint Quelle |
| utm_campaign | Name der Ad-Kampagne |
| utm_content | Anzeigeninhalt |
| utm_term | Suchbegrifftext |
