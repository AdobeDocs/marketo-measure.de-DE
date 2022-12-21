---
unique-page-id: 18874648
description: Unterschied zwischen einer Google Analytics-Konversion und einem Käufer-Touchpoint - [!DNL Marketo Measure] - Produktdokumentation
title: Unterschied zwischen einer Google Analytics-Konversion und einem Käufer-Touchpoint
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# Unterschied zwischen einer Google Analytics-Konversion und einem Käufer-Touchpoint {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

Erfahren Sie mehr über [!DNL Google Analytics (GA)] Ziel ist und wie es sich von einem Käufer Touchpoint unterscheidet.

**Wie lauten die Konversionen der Google Analytics?**

[!UICONTROL Google Analytics] Konversionen werden vollständig dadurch bestimmt, wie ein Marketing-Experte oder Web-Entwickler die &quot;Zielabschlüsse&quot;auf einer bestimmten Website kodiert. Ziele, so Google, könnten als &quot;Kauf tätigen (für eine E-Commerce-Site), ein Spiellevel (für eine mobile Gaming-App) abschließen oder ein Kontaktformular (für eine Marketing- oder Lead-Generierungssite) senden&quot;. Meistens sehen Marketer Ziele/Konversionen als Personen, die ein Informationsformular ausfüllen.

Ziele können jedoch nicht codiert werden, um sehr spezifische Verhaltensweisen zu verwalten. Stattdessen können Webentwickler Zieltypen konfigurieren. Im Folgenden finden Sie einige dieser Beispiele:

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
   <td><em>Danke für die Registrierung!</em> Web-Seite oder App-Bildschirm</td> 
  </tr> 
  <tr> 
   <td>Dauer</td> 
   <td>Sitzungen, die einen bestimmten Zeitraum oder länger dauern</td> 
   <td>10 Minuten oder länger auf einer Support-Site verbracht</td> 
  </tr> 
  <tr> 
   <td>Seiten/Bildschirme pro Sitzung</td> 
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

Das bedeutet, dass Google die Dankeseitenansichten als Konversion betrachtet. Aus Sicht der Google Analytics ist dies eine Erkenntnis, mit der die meisten Marketer einverstanden sind.

Die Touchpoints des Käufers verhalten sich jedoch sehr unterschiedlich.

**Worin unterscheiden sich die Touchpoints des Käufers?**

[!DNL Marketo Measure] JavaScript verfolgt Sitzungsdaten und Formularübermittlungen auf allen Formularen einer bestimmten Site. Es ist nicht erforderlich, Ziele aus einer [!DNL Marketo Measure] Standpunkt. Dieser Prozess ist automatisch. Für Formularübermittlungen, [!DNL Marketo Measure] meldet jedes Mal, wenn ein anonymer Benutzer Informationsfelder in einem bestimmten Formular ausfüllt und auf die Schaltfläche zum Übermitteln des Formulars klickt, den Ausfüllen des Formulars. [!DNL Marketo Measure] benötigt keine Dankeseite, um die Formularübermittlung aufzuzeichnen.

[!DNL Marketo Measure] erstellt einen Formular-Touchpoint, wenn:

* Ein mit diesen Konversionen verknüpfter Lead/Kontakt wird in Ihrem CRM-System angezeigt.
* Die [!DNL Marketo Measure] JS ist auf den Webseiten vorhanden, die das Formular enthalten.
* Ein Formular wird innerhalb einer 30-minütigen Sitzung eingereicht.

[!DNL Marketo Measure] ignoriert die Ziel-Google Analytics-Konvertierungen, wenn:

* Ein Bot sendet Formulare auf einer Website (diese Bots machen sie normalerweise nicht in das CRM-System eines Kunden).
* Ein Benutzer sendet nach der ersten Formularübermittlung weitere Formulare. [!DNL Marketo Measure] sendet nur die erste Konversion von dieser Sitzung.
* Der Benutzer klickt mehrmals auf die Formularübermittlung. [!DNL Marketo Measure] berücksichtigt nur die erste Formularübermittlung.
* Der Benutzer lädt die Dankeseite mehrmals neu.
* Der Benutzer verwendet alle Tools zum Blockieren von Anzeigen.

Wie Sie sehen, gibt es grundlegende Unterschiede zwischen GA und [!DNL Marketo Measure] eine Konversion berücksichtigen. Daher ist es sehr wahrscheinlich, dass die Anzahl der Konvertierungen und die Anzahl der Formular-Touchpoints variieren.
