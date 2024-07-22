---
unique-page-id: 18874648
description: Unterschied zwischen einer Google Analytics-Konversion und einer Buyer Touchpoint - [!DNL Marketo Measure]
title: Unterschied zwischen einer Google Analytics-Konversion und einem Buyer Touchpoint
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
feature: Touchpoints
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 5%

---

# Unterschied zwischen einer Google Analytics-Konversion und einem Buyer Touchpoint {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

Erfahren Sie, was ein [!DNL Google Analytics (GA)]-Ziel ist und wie es sich von einem Buyer Touchpoint unterscheidet.

**Was sind Google Analytics?**

[!UICONTROL Google Analytics] -Konversionen werden dadurch bestimmt, wie ein Marketing-Experte oder Web-Entwickler &quot;Ziel&quot;-Vervollständigungen auf einer bestimmten Website kodiert. Ziele könnten laut Google als &quot;Kauf tätigen (für eine E-Commerce-Site), Spiellevel abschließen (für eine mobile Gaming-App) oder ein Kontaktformular (für eine Marketing- oder Lead-Generierungssite) senden&quot;betrachtet werden. Meistens sehen Marketer Ziele/Konversionen als Personen, die ein Informationsformular ausfüllen.

Ziele können jedoch nicht für die Verwaltung bestimmter Verhaltensweisen kodiert werden. Stattdessen können Webentwickler Zieltypen konfigurieren. Im Folgenden finden Sie einige dieser Beispiele:

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><strong>Zieltyp</strong></td> 
   <td><p><strong>Beschreibung</strong></p></td> 
   <td><strong>Beispiel</strong></td> 
  </tr> 
  <tr> 
   <td><p>Ziel</p></td> 
   <td>Ein bestimmter Speicherort wird geladen</td> 
   <td><em>Vielen Dank für die Registrierung!</em> Webseite oder Anwendungsbildschirm</td> 
  </tr> 
  <tr> 
   <td>Dauer</td> 
   <td>Sitzungen, die einen bestimmten Zeitraum oder länger dauern</td> 
   <td>10 Minuten oder länger auf einer Support-Site verbracht</td> 
  </tr> 
  <tr> 
   <td>Seiten/Screens pro Sitzung</td> 
   <td>Ein Benutzer zeigt eine bestimmte Anzahl von Seiten oder Bildschirmen an</td> 
   <td>5 Seiten oder Bildschirme wurden geladen</td> 
  </tr> 
  <tr> 
   <td>Veranstaltung</td> 
   <td>Eine Aktion, die als Ereignis ausgelöst wurde</td> 
   <td>Social-Empfehlung, Videowiedergabe, Anzeigenklick</td> 
  </tr> 
 </tbody> 
</table>

Die meisten Marketing-Experten konfigurieren ihre Konversionen als &quot;Zielziele&quot;, d. h., sie erstellen normalerweise eine Dankeseite nach einem Formular, um zu berücksichtigen, dass es sich um eine formale Konversion handelt.

Das bedeutet, dass Google Dankesseiten als Konversion betrachtet. Aus Sicht der Google Analytics ist dies eine Erkenntnis, mit der die meisten Marketer einverstanden sind.

Die Touchpoints des Käufers verhalten sich jedoch anders.

**Wie unterscheiden sich die Touchpoints des Käufers?**

[!DNL Marketo Measure] JavaScript verfolgt Sitzungsdaten und Formularübermittlungen auf allen Formularen einer bestimmten Site. Es ist nicht erforderlich, Ziele aus einer [!DNL Marketo Measure] Perspektive zu kodieren. Dieser Prozess ist automatisch. Bei Formularübermittlungen meldet [!DNL Marketo Measure] jedes Mal, wenn ein anonymer Benutzer Informationsfelder in einem bestimmten Formular ausfüllt, einen Formularausfüllvorgang und auch auf die Schaltfläche zum Senden des Formulars klickt. [!DNL Marketo Measure] benötigt keine Dankeseite, um die Formularübermittlung aufzuzeichnen.

[!DNL Marketo Measure] erstellt einen Formular-Touchpoint, wenn:

* Ein mit diesen Konversionen verknüpfter Lead/Kontakt wird in Ihrem CRM-System angezeigt.
* Die JS [!DNL Marketo Measure] befindet sich auf den Webseiten, die das Formular enthalten.
* Ein Formular wird innerhalb einer 30-minütigen Sitzung eingereicht.

[!DNL Marketo Measure] ignoriert Ziel-Google Analytics-Konversionen, wenn:

* Ein Bot sendet Formulare auf einer Website (diese Bots machen sie normalerweise nicht in das CRM-System eines Kunden).
* Ein Benutzer sendet nach der ersten Formularübermittlung weitere Formulare. [!DNL Marketo Measure] gibt nur die erste Konversion aus dieser Sitzung weiter.
* Der Benutzer klickt mehrmals auf die Formularübermittlung. [!DNL Marketo Measure] berücksichtigt nur die erste Formularübermittlung.
* Der Benutzer lädt die Dankeseite mehrmals neu.
* Der Benutzer verwendet alle Tools zum Blockieren von Anzeigen.

Wie Sie sehen können, gibt es grundlegende Unterschiede zwischen dem, was GA und [!DNL Marketo Measure] für eine Konversion halten. Daher ist es wahrscheinlich, dass die Anzahl der Konvertierungen und die Anzahl der Formular-Touchpoints unterschiedlich sind.
