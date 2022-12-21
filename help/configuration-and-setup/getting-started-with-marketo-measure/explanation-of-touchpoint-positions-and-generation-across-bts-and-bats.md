---
description: Erläuterung der Touchpoint-Positionen und der Erzeugung zwischen BT und BVT - [!DNL Marketo Measure] - Produktdokumentation
title: Erläuterung der Touchpoint-Positionen und der Generierung über BTs hinweg und [!DNL BATs]
exl-id: 4903f917-a366-4767-a126-5216d2377399
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 2%

---

# Erläuterung der Touchpoint-Positionen und der Generierung über BTs hinweg und [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**Erzeugung von Touchpoint-Positionen und Fluss durch die Journey der Käufer**

Das Verständnis der Touchpoint-Positionen des Käufers und deren Auslösung ist für eine erfolgreiche Berichterstellung mit [!DNL Marketo Measure] Daten. Sie möchten ein klares Verständnis davon haben, was Ihre Interessenten getan haben, als sie sich durch die Journey des Käufers bewegt haben, und was dies wiederum in den Touchpoint-Daten aussehen wird. Für weiteren Kontext zu diesem Thema empfehlen wir, die [[!UICONTROL Touchpoint-Generierung und -Zuordnung]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) Artikel.

[!DNL Marketo Measure] hat eine Vielzahl von Touchpoint-Position, die durch verschiedene Schritte im Journey des Käufers ausgelöst werden. Bei der Berichterstellung für [!DNL Marketo Measure] Daten gibt es zwei Gruppen von Touchpoint-Daten: Käufer-Touchpoints (BTs) und Buyer Attribution Touchpoints (BATs). Diese Datensätze weisen möglicherweise etwas unterschiedliche Positionen auf, da sie sich auf verschiedene Objekte beziehen. Für weiteren Kontext zu diesem Thema empfehlen wir, die [Unterschiede zwischen Käufer-Touchpoints (BTs) und Buyer Attribution Touchpoints (BATs)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) Artikel.

**Touchpoints des Käufers (BTs)**: Dies sind die Touchpoints, die einer Person und ihrer Journey zugeordnet sind und für diese Person eindeutig sein werden. Die folgenden vordefinierten Berichte werden aus den Touchpoint-Daten des Käufers erstellt.

* [!DNL Marketo Measure] 101: Leads nach ID
* [!DNL Marketo Measure] 101: Leads nach Kanal
* [!DNL Marketo Measure] 101: Lead/Kontakt nach ID
* [!DNL Marketo Measure] 101: Lead/Kontakt nach Kanal

Im Folgenden werden die Touchpoint-Positionen des Käufers beschrieben, die beschreiben, wo sich eine Person in ihrer Journey befindet und welche Maßnahmen sie ergriffen haben, um diese Position zu erlangen.

<table> 
 <tbody>
  <tr>
   <th>Position des Käufer-Touchpoints (BTs)</th> 
   <th>Touchpoint-Typ (Aktion, bei der Trigger-Touchpoint möglich ist)</th> 
   <th>Beschreibung des Touchpoints</th> 
  </tr>
  <tr>
   <td>First Touch (FT)</td> 
   <td>Web-Besuch</td> 
   <td>Die allererste Marketing-Interaktion, die ein Kontakt mit Ihrer Marke hat</td> 
  </tr>
  <tr>
   <td>Lead Creation (LC)</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Einbindung von Kampagnen/Programmen</td> 
   <td>Das erste Ausfüllen des Formulars, das eine Person hat (in der Regel eine Formularübermittlung, kann aber auch eine Kampagne/ein Programm einschließen)</td> 
  </tr>
  <tr>
   <td>Post LC</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Einbindung von Kampagnen/Programmen</td> 
   <td>Jedes Formular, das eine Person nach ihrer LC (oder einer nachfolgenden Einbindung in Campaign/Programm) ausfüllt</td> 
  </tr>
 </tbody>
</table>

**Touchpoints der Käuferzuordnung (BATS)**: Dies sind die Touchpoints, die mit einer Chance und ihrer Journey verknüpft sind. Diese Touchpoints sind mit dem Umsatz verbunden, da sie mit der Gelegenheit und ihren Kontakten verbunden sind. Die folgenden vordefinierten Berichte werden aus den Touchpoint-Daten der Buyer Attribution erstellt.

* [!DNL Marketo Measure] 101: Möglichkeiten nach ID
* [!DNL Marketo Measure] 101: Möglichkeiten nach ID-Kanal

<table> 
 <tbody>
  <tr>
   <th>Position des Touchpoints der Käuferzuordnung (BVT)</th> 
   <th>Touchpoint-Typ (Aktion, bei der Trigger-Touchpoint möglich ist)</th> 
   <th>Beschreibung des Touchpoints</th> 
  </tr>
  <tr>
   <td>First Touch (FT)</td> 
   <td>Web-Besuch</td> 
   <td>Die allererste Marketing-Interaktion, die ein Kontakt mit Ihrer Marke hatte</td> 
  </tr>
  <tr>
   <td>Lead Creation (LC)</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Einbindung von Kampagnen/Programmen</td> 
   <td>Das erste Ausfüllen eines Formulars, das ein Kontakt hatte (normalerweise eine Formularübermittlung, aber auch eine Kampagnen-/Programmeinbindung sein kann)</td> 
  </tr>
  <tr>
   <td>Opportunity Creation</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Webbesuch <strong>ODER</strong> Einbindung von Kampagnen/Programmen</td> 
   <td>Die Marketing-Interaktion, die dem Zeitpunkt der Erstellung der Opp am nächsten ist</td> 
  </tr> 
  <tr>
   <td>Geschlossen/verloren</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Webbesuch <strong>ODER</strong> Einbindung von Kampagnen/Programmen</td> 
   <td>Die Marketing-Interaktion, die dem Zeitpunkt am nächsten kommt, an dem die Opp geschlossen wird (Gewinner oder Verlust)</td> 
  </tr>
  <tr>
   <td>Middle Touches</td> 
   <td>Formular ausfüllen <strong>ODER</strong> Einbindung von Kampagnen/Programmen</td> 
   <td>Wenn ein Kontakt ein Online-Formular ausfüllt und es nicht mit einem Meilenstein-Touchpoint zusammenfällt</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] verfügt über diese beiden Datensätze von Touchpoint-Daten, um ein klares Verständnis des Journey einer Person sowie der Möglichkeiten zu schaffen. Diese beiden Touchpoint-Datensätze geben Ihnen eine klare Zuordnung von den Vorgängen vom Trichteranfang zum Trichterende.

Das folgende Beispiel zeigt den Datenfluss von Käufer-Touchpoints (BTs) zu Buyer Attribution Touchpoints (BATs). In diesem Beispiel sind Person A und Person B Teil derselben Chance, die über ein Erstellungsdatum vom 3.7.2020 und ein Endergebnis vom 5.6.2020 verfügt.

**Person A** Touchpoint-Datensatz des Käufers

* First Touch (FT) - Paid Search.AdWords - 1.9.2019
* Lead-Erstellung (LC) - Organische Suche.Google - 20.11.2019
* Post-LC (Formular ausfüllen) - Webinar - 3/4/2020

**Person B** Touchpoint-Datensatz des Käufers

* First Touch (FT) - Paid Social.Facebook - 26.8.2019
* Lead-Erstellung (LC) - Organische Suche.Yahoo - 20.2.2020
* Post-LC (Formular ausfüllen) - E-Mail - 1.5.2020

**Chancen** Touchpoint-Daten der Käuferzuordnung würden wie folgt gelesen:

* First Touch (FT) - Paid Social.Facebook - 26.8.2019
   * (von **Person B** weil sie &quot;true&quot;haben _Erstkontakt_ für das Konto/Opp)
* Lead-Erstellung (LC) - Organische Suche.Google - 20.11.2019
   * (von **Person A** weil sie &quot;true&quot;haben _Lead-Erstellung_ für das Konto/Opp)
* Opportunity Creation (OC) - Webinar - 3/4/2020
   * (Post-LC-Touchpoint von **Person A** wäre _OC Touchpoint_ weil es die aktuellste Interaktion war, die wir mit der am 7.3.2020 erstellten Opportunity haben.)
* Closed Won - Email - 1.5.2020
   * (Post-LC-Touchpoint von **Person B** wäre _Geschlossener Won Touchpoint_ weil es die aktuellste Interaktion war, die wir haben, um die Möglichkeit zu schließen (am 6.5.2020)
