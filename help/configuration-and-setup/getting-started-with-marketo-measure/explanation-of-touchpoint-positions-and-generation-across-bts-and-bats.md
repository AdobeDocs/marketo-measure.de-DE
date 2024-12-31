---
description: Erläuterung der Touchpoint-Positionen und -Generierung in BT und BAT - [!DNL Marketo Measure]
title: Erläuterung der Touchpoint-Positionen und der Generierung über BTs und [!DNL BATs] hinweg
exl-id: 4903f917-a366-4767-a126-5216d2377399
feature: Touchpoints
source-git-commit: cd5597a681f388a5b5c743dadd38bf3127811bff
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 3%

---

# Erläuterung der Touchpoint-Positionen und -Generierung in BT und [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**Erstellung von Touchpoint-Positionen und Fluss durch die Buyers Journey**

Das Verständnis der Buyer Touchpoint-Positionen und ihrer Auslösung ist für ein erfolgreiches Reporting mit [!DNL Marketo Measure]-Daten von entscheidender Bedeutung. Sie möchten ein klares Verständnis davon haben, was Ihre potenziellen Kunden getan haben, als sie sich durch die Journey des Käufers bewegten, und wie dies wiederum in den Touchpoint-Daten aussehen wird. Für mehr Kontext zu diesem Thema empfehlen wir den Artikel [[!UICONTROL Touchpoint-Generierung und -Zuordnung]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md).

[!DNL Marketo Measure] verfügt über eine Vielzahl von Touchpoint-Positionen, die durch verschiedene Schritte auf dem Journey des Käufers ausgelöst werden. Bei der Berichterstellung über [!DNL Marketo Measure] Daten gibt es zwei Arten von Touchpoint-Daten: Käufer-Touchpoints (BT) und Käufer-Attribution-Touchpoints (BAT). Sie werden feststellen, dass diese Datensätze leicht unterschiedliche Positionen einnehmen, da sie sich auf verschiedene Objekte beziehen. Für mehr Kontext zu diesem Thema empfehlen wir den Artikel [Unterschied zwischen Käufer-Touchpoints (BT) und Käufer-Attribution-Touchpoints (BAT](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md).

**Buyer Touchpoints (BT)**: Dies sind die Touchpoints, die einer einzelnen Person und deren Journey zugeordnet sind und für diese Person eindeutig sind. Die folgenden vordefinierten Berichte basieren auf Buyer Touchpoint-Daten.

* [!DNL Marketo Measure] 101: Leads nach ID
* [!DNL Marketo Measure] 101: Leads nach Kanal
* [!DNL Marketo Measure] 101: Lead/Kontakt nach ID
* [!DNL Marketo Measure] 101: Lead/Kontakt nach Kanal

Im Folgenden werden die Buyer Touchpoint-Positionen beschrieben, die beschreiben, wo sich eine Person in ihrem Journey befindet und welche Maßnahmen sie ergriffen haben, um diese Position zu erlangen.

<table> 
 <tbody>
  <tr>
   <th>Position von Buyer Touchpoint (BT)</th> 
   <th>Touchpoint-Typ (Aktion, die Touchpoint-Trigger auslösen kann)</th> 
   <th>Beschreibung des Touchpoints</th> 
  </tr>
  <tr>
   <td>First Touch (FT)</td> 
   <td>Web-Besuch</td> 
   <td>Die erste Marketing-Interaktion eines Kontakts mit Ihrer Marke</td> 
  </tr>
  <tr>
   <td>Lead Creation (LC)</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Kampagnen/Programm-Einbindung</td> 
   <td>Das erste Formular, das ein Kontakt ausfüllt, enthält (normalerweise eine Formularübermittlung, könnte aber auch eine Kampagne/ein Einschlussprogramm sein)</td> 
  </tr>
  <tr>
   <td>Post LC</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Kampagnen/Programm-Einbindung</td> 
   <td>Jedes Formular, das eine Person nach ihrer LC (oder einer nachfolgenden Kampagne/Programmeinbindung) ausfüllt</td> 
  </tr>
 </tbody>
</table>

**Buyer Attribution Touchpoints (BAT)**: Dies sind die Touchpoints, die mit einer Opportunity und ihrem Journey verbunden sind. Diese Touchpoints sind mit dem Umsatz verbunden, da sie mit der Opportunity und ihren Kontakten verbunden sind. Die folgenden vordefinierten Berichte basieren auf Buyer Attribution Touchpoint-Daten.

* [!DNL Marketo Measure] 101: Vertriebschancen nach ID
* [!DNL Marketo Measure] 101: Vertriebschancen nach ID-Kanal

<table> 
 <tbody>
  <tr>
   <th>Position von Buyer Attribution Touchpoint (BAT)</th> 
   <th>Touchpoint-Typ (Aktion, die Touchpoint-Trigger auslösen kann)</th> 
   <th>Beschreibung des Touchpoints</th> 
  </tr>
  <tr>
   <td>First Touch (FT)</td> 
   <td>Web-Besuch</td> 
   <td>Die erste Marketing-Interaktion eines Kontakts mit Ihrer Marke</td> 
  </tr>
  <tr>
   <td>Lead Creation (LC)</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Kampagnen/Programm-Einbindung</td> 
   <td>Das erste ausgefüllte Formular, das ein Kontakt hatte (normalerweise eine Formularübermittlung, könnte aber auch eine Kampagne/ein Einschluss-Programm sein)</td> 
  </tr>
  <tr>
   <td>Opportunity-Erstellung</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Web-Besuch <strong>ODER</strong> Kampagnen-/Programmeinbindung</td> 
   <td>Die Marketing-Interaktion, die dem Zeitpunkt der Erstellung der Opportunity am nächsten kommt</td> 
  </tr> 
  <tr>
   <td>Gewonnen/Verloren</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Web-Besuch <strong>ODER</strong> Kampagnen-/Programmeinbindung</td> 
   <td>Die Marketing-Interaktion, die dem Zeitpunkt am nächsten kommt, zu dem die Opportunity geschlossen wird (gewonnen oder verloren)</td> 
  </tr>
  <tr>
   <td>Middle Touches</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Kampagnen/Programm-Einbindung</td> 
   <td>Wenn ein Kontakt ein Online-Formular ausfüllt und es nicht mit dem Meilenstein-Touchpoint übereinstimmt</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] verfügt über diese beiden Touchpoint-Datensätze, um den Journey und die Chancen einer Person genau zu verstehen. Diese beiden Touchpoint-Datensätze geben Ihnen eine klare Übersicht darüber, was von der Trichteroberseite bis zur Trichterunterseite passiert ist.

Das folgende Beispiel zeigt den Datenfluss von Käufer-Touchpoints (BT) zu Käufer-Attribution-Touchpoints (BAT). In diesem Beispiel sind Person A und Person B beide Teil derselben Opportunity, die das Erstellungsdatum 3/7/2020 und das Abschlussdatum 5/6/2020 hat.

**Person A** Buyer Touchpoint-Datensatz

* First Touch (FT) - Paid Search.AdWords - 9/1/2019
* Lead Creation (LC) - Organische Suche.Google - 11/20/2019
* Post LC (Formular ausfüllen) - Webinar - 3/4/2020

**Person B** Buyer Touchpoint-Datensatz

* First Touch (FT) - Paid Social.Facebook - 8/26/2019
* Lead Creation (LC) - Organische Suche.Yahoo - 2/20/2020
* Post LC (Formular ausfüllen) - E-Mail - 5/1/2020

**Opportunities** würden Buyer Attribution Touchpoint-Daten wie folgt lauten…

* First Touch (FT) - Paid Social.Facebook - 8/26/2019
   * (von **Person B**, da sie die wahre _Erstkontakt_ für das Konto/die Opportunity haben)
* Lead Creation (LC) - Organische Suche.Google - 11/20/2019
   * (von **Person A**, da sie die _Lead-Erstellung_ für das Konto/die Opportunity haben)
* Opportunity Creation (OC) - Webinar - 3/4/2020
   * (Der Post LC-Touchpoint von **Person A** wäre der _OC Touchpoint_ da es die neueste Interaktion war, die wir zur Opportunity haben, die am 3/7/2020 erstellt wird)
* Abgeschlossen Gewonnen - E-Mail - 5/1/2020
   * (Der Post LC-Touchpoint von **Person B** wäre der _Closed Won Touchpoint_ da es die neueste Interaktion war, die wir haben, um die Opportunity am 5/6/2020 zu schließen)
