---
description: Erläuterung der Touchpoint-Positionen und Generierung über BT und BAT hinweg - [!DNL Marketo Measure]
title: Erläuterung der Touchpoint-Positionen und der Generierung über BTs und [!DNL BATs] hinweg
exl-id: 4903f917-a366-4767-a126-5216d2377399
feature: Touchpoints
source-git-commit: cd5597a681f388a5b5c743dadd38bf3127811bff
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 3%

---

# Erläuterung der Touchpoint-Position und der Generierung über BT und [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**Generierung von Touchpoint-Positionen und -Fluss durch die Käufer-Journey**

Das Verständnis der Buyer Touchpoint-Positionen und deren Auslösung ist für eine erfolgreiche Berichterstellung mit [!DNL Marketo Measure] -Daten von entscheidender Bedeutung. Sie möchten ein klares Verständnis davon haben, was Ihre Interessenten getan haben, als sie sich durch die Journey des Käufers bewegt haben, und was dies wiederum in den Touchpoint-Daten aussehen wird. Für mehr Kontext zu diesem Thema empfehlen wir, den Artikel [[!UICONTROL Touchpoint-Generierung und -Zuordnung]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) zu lesen.

[!DNL Marketo Measure] hat eine Vielzahl von Touchpoint-Positionen, die durch verschiedene Schritte im Journey des Käufers ausgelöst werden. Bei der Berichterstellung für [!DNL Marketo Measure] -Daten gibt es zwei Sätze von Touchpoint-Daten: Käufer-Touchpoints (BT) und Käufer-Attribution-Touchpoints (BAT). Diese Datensätze weisen möglicherweise etwas unterschiedliche Positionen auf, da sie sich auf verschiedene Objekte beziehen. Für mehr Kontext zu diesem Thema empfehlen wir, den Artikel [Unterschied zwischen Käufer-Touchpoints (BT) und Buyer Attribution Touchpoints (BAT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) zu lesen.

**Käufer-Touchpoints (BT)**: Dies sind die Touchpoints, die einer Person und ihrer Journey zugeordnet sind und für diese Person eindeutig sein werden. Die folgenden vordefinierten Berichte sind aus Buyer Touchpoint-Daten aufgebaut.

* [!DNL Marketo Measure] 101: Leads nach ID
* [!DNL Marketo Measure] 101: Leads nach Kanal
* [!DNL Marketo Measure] 101: Lead/Kontakt nach ID
* [!DNL Marketo Measure] 101: Lead/Kontakt nach Kanal

Im Folgenden werden die Positionen der Buyer Touchpoint beschrieben, in denen beschrieben wird, wo sich eine Person in ihrer Journey befindet und welche Maßnahmen sie ergriffen hat, um diese Position zu erlangen.

<table> 
 <tbody>
  <tr>
   <th>Position von Buyer Touchpoint (BT)</th> 
   <th>Touchpoint-Typ (Aktion, bei der Trigger-Touchpoint möglich ist)</th> 
   <th>Beschreibung des Touchpoints</th> 
  </tr>
  <tr>
   <td>First Touch (FT)</td> 
   <td>Web-Besuch</td> 
   <td>Die erste Marketing-Interaktion, die ein Kontakt mit Ihrer Marke hat</td> 
  </tr>
  <tr>
   <td>Lead Creation (LC)</td> 
   <td>Formularausfüllung <strong>ODER</strong> Kampagnen-/Programmeinbindung</td> 
   <td>Das erste Formular, das eine Person ausfüllt, hat (in der Regel eine Formularübermittlung, kann aber auch eine Kampagne/ein Programm enthalten)</td> 
  </tr>
  <tr>
   <td>Post LC</td> 
   <td>Formularausfüllung <strong>ODER</strong> Kampagnen-/Programmeinbindung</td> 
   <td>Jedes Formular, das eine Person nach ihrer LC (oder einer nachfolgenden Einbindung in Kampagne/Programm) ausfüllt</td> 
  </tr>
 </tbody>
</table>

**Touchpoints der Käuferzuordnung (BAT)**: Dies sind die Touchpoints, die einer Gelegenheit und ihrer Journey zugeordnet sind. Diese Touchpoints sind mit dem Umsatz verbunden, da sie mit der Gelegenheit und ihren Kontakten verbunden sind. Die folgenden vordefinierten Berichte sind aus Buyer Attribution Touchpoint-Daten aufgebaut.

* [!DNL Marketo Measure] 101: Chancen nach ID
* [!DNL Marketo Measure] 101: Chancen nach ID-Kanal

<table> 
 <tbody>
  <tr>
   <th>Position von Buyer Attribution Touchpoint (BAT)</th> 
   <th>Touchpoint-Typ (Aktion, bei der Trigger-Touchpoint möglich ist)</th> 
   <th>Beschreibung des Touchpoints</th> 
  </tr>
  <tr>
   <td>First Touch (FT)</td> 
   <td>Web-Besuch</td> 
   <td>Die erste Marketing-Interaktion, die ein Kontakt mit Ihrer Marke hatte</td> 
  </tr>
  <tr>
   <td>Lead Creation (LC)</td> 
   <td>Formularausfüllung <strong>ODER</strong> Kampagnen-/Programmeinbindung</td> 
   <td>Das erste Ausfüllen eines Formulars, das ein Kontakt hatte (normalerweise eine Formularübermittlung, aber auch eine Kampagnen-/Programmeinbindung sein kann)</td> 
  </tr>
  <tr>
   <td>Opportunity Creation</td> 
   <td>Ausfüllen des Formulars <strong>ODER</strong> Webbesuch <strong>ODER</strong> Einbindung der Kampagne/des Programms</td> 
   <td>Die Marketing-Interaktion, die dem Zeitpunkt der Erstellung der Opp am nächsten ist</td> 
  </tr> 
  <tr>
   <td>Geschlossen/verloren</td> 
   <td>Ausfüllen des Formulars <strong>ODER</strong> Webbesuch <strong>ODER</strong> Einbindung der Kampagne/des Programms</td> 
   <td>Die Marketing-Interaktion, die dem Zeitpunkt am nächsten kommt, an dem die Opp geschlossen wird (Gewinner oder Verlust)</td> 
  </tr>
  <tr>
   <td>Middle Touches</td> 
   <td>Formularausfüllung <strong>ODER</strong> Kampagnen-/Programmeinbindung</td> 
   <td>Wenn ein Kontakt ein Online-Formular ausfüllt und es nicht mit einem Meilenstein-Touchpoint zusammenfällt</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] verfügt über diese beiden Datensätze von Touchpoint-Daten, um ein klares Verständnis der Journey und Möglichkeiten einer Person zu schaffen. Diese beiden Touchpoint-Datensätze geben Ihnen eine klare Zuordnung von den Vorgängen vom Trichteranfang zum Trichterende.

Das folgende Beispiel zeigt den Datenfluss von Käufer-Touchpoints (BT) zu Buyer Attribution Touchpoints (BAT). In diesem Beispiel gehören Person A und Person B zu derselben Gelegenheit, die über ein Erstellungsdatum vom 7.3.2020 und ein Endergebnis vom 5.6.2020 verfügt.

**Person A** Buyer Touchpoint-Datensatz

* First Touch (FT) - Paid Search.AdWords - 1.9.2019
* Lead-Erstellung (LC) - Organische Suche.Google - 20.11.2019
* Post-LC (Formular ausfüllen) - Webinar - 3/4/2020

**Person B** Buyer Touchpoint-Datensatz

* First Touch (FT) - Paid Social.Facebook - 26.8.2019
* Lead-Erstellung (LC) - Organische Suche.Yahoo - 20.2.2020
* Post-LC (Formular ausfüllen) - E-Mail - 1.5.2020

**Chancen** Buyer Attribution Touchpoint-Daten würden wie folgt gelesen..

* First Touch (FT) - Paid Social.Facebook - 26.8.2019
   * (von **Person B** ), da sie den Wert &quot;true&quot;_First Touch_ für das Konto/die Opp hat
* Lead-Erstellung (LC) - Organische Suche.Google - 20.11.2019
   * (von **Person A** , da sie die wahre _Lead-Erstellung_ für das Konto/Opp hat)
* Opportunity Creation (OC) - Webinar - 3/4/2020
   * (Der Post-LC-Touchpoint von **Person A** wäre der _OC-Touchpoint_ , da es die aktuellste Interaktion war, die wir mit der am 7.3.2020 erstellten Opportunity hatten.)
* Closed Won - Email - 1.5.2020
   * (Der Post-LC-Touchpoint von **Person B** wäre der _Geschlossene Won Touchpoint_ , da es die letzte Interaktion war, die wir mit der Schließung der Opportunity am 6.5.2020 hatten.)
