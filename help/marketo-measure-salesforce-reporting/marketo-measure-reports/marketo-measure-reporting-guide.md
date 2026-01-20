---
description: Handbuch zur [!DNL Marketo Measure]-Berichterstellung - [!DNL Marketo Measure]
title: '[!DNL Marketo Measure] Reporting-Handbuch'
exl-id: 9b991f9e-c187-4b43-b0a8-8ed3e9a6056b
feature: Reporting
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '5602'
ht-degree: 2%

---

# [!DNL Marketo Measure] Reporting-Handbuch {#marketo-measure-reporting-guide}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in der Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Bevor Sie einen [!DNL Marketo Measure] erstellen, müssen Sie unbedingt überprüfen, ob Ihre [!DNL Marketo Measure] Kontoeinstellungen überprüft und konfiguriert wurden, um sicherzustellen, dass die Daten in den Berichten korrekt sind und die Besonderheiten Ihres Unternehmens widerspiegeln. Darüber hinaus funktionieren Reporting-Projekte am besten, wenn sie einem strukturierten Prozess folgen. Justin Norris, ein [!DNL Marketo Measure] Power-User, Fürsprecher und Partner aus [Perkuto](https://perkuto.com/){target="_blank"} fasst gut zusammen [wie man an Berichte herangeht [!DNL Marketo Measure]](https://perkuto.com/blog/turning-attribution-data-into-actionable-insights/){target="_blank"}:

**Ziele festlegen**: „Die erste Frage, die gestellt werden muss, lautet: „Warum messen wir?“ Lori Wizdo von [Forrester Research](https://go.forrester.com/) fasste es in einem [Marketo-Webinar](https://www.marketo.com/webinars/beyond-revenue-performance-real-kpis-of-b2b-marketing/){target="_blank"} treffend zusammen. Ihr zufolge „messen wir, um eine Entscheidung oder den Wert des Marketings nachzuweisen oder zu validieren oder um besser zu werden (Prozessverbesserung).“ Wir möchten hinzufügen, dass die Erkenntnisse aus guter Messung auch einen Input und eine Anleitung für den Marketing-Planungsprozess liefern.

Bevor Sie also beginnen, müssen Sie sich über Ihre Ziele, die Fragen, die Sie zu beantworten versuchen, oder die Probleme, die Sie zu lösen versuchen, im Klaren sein. Welche Geschichte möchtest du erzählen? Welche Entscheidungen werden dann getroffen? Allzu oft sind diese Grundlagen schlecht durchdacht, was zu Frustration bei allen Beteiligten führt.“

**Berichtsdesign**: „Als Nächstes müssen Sie den Bericht entwerfen und die spezifischen Dimensionen, Metriken und Datensätze bestimmen, die er enthalten soll. Ein gängiges Erlebnis besteht darin, Geschäftsbenutzern genau das zu bieten, was sie verlangen, nur damit sie immer noch das Gefühl haben, dass ihre Bedürfnisse nicht erfüllt werden. Der Grund dafür ist, dass die insight, nach der ein Business-Anwender tatsächlich sucht, nicht immer in dem angeforderten Bericht enthalten ist. Ein guter Analytiker (oder eine MOPS-Person mit einem Analytiker, der bzw. die eine Funktion hat) wird klärende Fragen stellen, gemeinsame Definitionen festlegen („Was meinen Sie wirklich mit Lead? „) und sogar ein Bild des endgültigen Berichts skizzieren, um sicherzustellen, dass eine Abstimmung erfolgt. Erst dann erstellen Sie den Bericht in dem Wissen, dass Sie über solide Anforderungen verfügen.“

**Report Build**: „Wenn Sie einmal einen Build erstellt haben, ist es nicht ungewöhnlich, dass Sie auf Hindernisse oder Sackgassen stoßen. So können Sie beispielsweise feststellen, dass kein wesentlicher Datenpunkt vorhanden ist oder die Objekte nicht wie gewünscht verknüpft sind. Um diese Probleme zu lösen, denke ich auch, dass es wichtig ist zu verstehen, was „unter der Haube“ in Ihrem Reporting-„Rechner“ passiert. Diese Flüssigkeit ermöglicht es Ihnen, eine Berichtsanfrage schnell zu dimensionieren und zu bewerten, ob sie erreichbar ist (und einfachere kreative Lösungen zu entwickeln, wenn sie es nicht ist).“

Werfen wir einen Blick „unter die Haube“, um besser zu verstehen, was die [!DNL Marketo Measure] Attribution Reporting Machine ausführt.

## Buyer Touchpoint-Objekte (CRM) {#buyer-touchpoint-objects-crm}

Auf der höchsten Ebene gibt es zwei Berichtskategorien, die auf den beiden verschiedenen Buyer Touchpoint-Objekten basieren: Diese Kategorien bestimmen, über welchen Datentyp [!DNL Marketo Measure] Bericht erstellt werden soll: Daten, die sich auf eine _Person_, oder Daten, die sich auf eine _Opportunity_ beziehen.

1. **Kunden-Touchpoints** (BTs) / Einzelpersonen / Gesamte Interaktion

   * Wird häufig für TOFU-Metriken (Top of the funnel) und Berichte zu _Personen_ (Leads, Kontakte [!DNL Marketo Measure] Personen) verwendet
   * BTs werden zum Verständnis aller Marketing-Interaktionen im Zusammenhang mit **Personen** verwendet, da sie den vollständigen Touchpoint-Verlauf für jede Person enthalten. Zur Erinnerung: Diese Touchpoints werden im CRM für den anonymen Erstkontakt, den Touch Lead-Erstellung und jede nachfolgende Formularübermittlung oder jeden Touchpoint erstellt, aus dem Sie synchronisieren möchten
einer Offline-Kampagne oder -Aktivität.

1. **Buyer Attribution Touchpoints** (BATs) / Opportunity / Kontoebene / Umsatz

   * Wird häufig für Metriken „Mitte und/oder Ende der funnel&quot; (MOFU und BOFU) und Berichte im Zusammenhang mit &quot;_&quot;_.
   * BATs stellen die relevanten Touchpoints aller Personen dar, die mit der **Opportunity** verbunden sind (entweder über Opportunity-Kontaktrollen oder über eine freigegebene Konto-ID, je nach Ihren Einstellungen). Im Gegensatz zu BTs, die sich nur auf Personen beziehen, können BATs auch mit &quot;**&quot;** werden. Daher verwenden Sie BATs, um Fragen zu Opportunitys zu beantworten, einschließlich der Anzahl der geöffneten oder geschlossenen Opportunitys oder des Pipeline-Werts und des gewonnenen Umsatzes.

>[!NOTE]
>
>BVT werden aus BTs erstellt. Im Wesentlichen beginnt das Tracking auf individueller Ebene über die BTs. Sobald eine Opportunity für ein Konto erstellt wurde, werden alle BTs von Kontakten unter demselben Konto referenziert und können BATs erstellen, die sich auf die Opportunity beziehen. Daher sollten Sie die eine oder die andere verwenden, je nachdem, welche Fragen Sie zu beantworten versuchen: Fragen zur Metrik „Personen“ (BT-Berichte) oder Fragen zur Metrik „Opportunity“ (BAT-Berichte)

Support-Artikel: [Unterschied zwischen Käufer-Touchpoints und Käufer-Attribution-Touchpoints](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md#configuration-and-setup){target="_blank"}

## Buyer Touchpoint (BT) {#buyer-touchpoint-bt}

Buyer Touchpoint (BT) ist das Objekt, das zum Nachverfolgen jeder Marketing-Interaktion eines Benutzers mit Ihren Marketing-Materialien verwendet wird. Die Journey jeder Person (Lead/Kontakt/[!DNL Marketo Measure] Person) würde durch die jeweiligen BTs repräsentiert. [!DNL Marketo Measure] besteht die Journey eines Kontakts aus:

1. Wie hat diese Person zuerst mit unserer Marke interagiert? (First Touch oder _FT_)
1. Wie ist diese Person konvertiert / bekannt geworden / Lead geworden? (Lead Creation oder _LC_)
1. Wie hat diese Person sonst mit unserer Marke und unseren Marketing-Materialien interagiert, seit sie Lead wurde? (_PostLC_)

Käufer-Touchpoints werden verwendet, um Fragen zu _Personen_ zu beantworten („Personen“ werden entweder durch Leads oder Kontakte innerhalb eines CRM repräsentiert), z. B. Lead-/Kontaktgenerierungs- oder Akquisemetriken, anstatt Opportunity-bezogene Metriken. Beispiel:

* Welche Kanäle liefern die meisten Leads?
* Welche Kanäle sind für die Erstellung eines neuen Leads mehr oder weniger kostspielig?
* Mit welchen Inhalten befassen sich meine Leads/Kontakte?
* Was ist die Marketing-Story bestimmter Titel, Rollen und Personas?
* Welche Kanäle fördern MQLs oder andere Lead-/Kontaktstatus?

In erster Linie müssen Unternehmen wissen: „Woher kommen meine Leads/Kontakte?“. Bisher wurde dies mit einem einzigen, eindimensionalen Wert beantwortet (z. B. Lead Source). Wie bereits #1 und #2 beschrieben, wissen wir jedoch, dass Leads während ihres Journey mehrere Touchpoints haben können, um Leads zu werden. Mit der Buyer Touchpoint können wir insight in die beiden wichtigsten Interaktionen einbinden, die darstellen, wie ein Lead generiert wurde: ihren Erstkontakt und ihren Kontakt zur Lead-Erstellung. Käufer-Touchpoints sind auch _multidimensional_ d. h. sie übertragen eine Fülle von Marketing-Daten, in erster Linie, woher die Person kam (Marketing-Kanal) und womit die Person interagiert hat (Inhalt).

Die [Attributionsmodelle](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md){target="_blank"} die die beste insight für personenbasierte Metriken bieten, sind:

* **Erstkontakt** - 100 % Attribution auf den Erstkontakt (FT) des Leads
* **Lead-Erstellung** - 100 % Attribution auf den Lead Creation Touch (LC)
* **U-förmig** - Multi-Touch-Ansatz, mit 40 % Kredit an den FT, 40 % Kredit an den LC

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-1.png"></td> 
   <td>Das U-förmige Modell wurde entwickelt, um allen Kunden-Touchpoints, die zusammenfassen, wie aus einem Lead ein Lead wurde, eine Gutschrift zu verleihen. Nachfolgende Touchpoints dieser Leads können zwar auch zum Verständnis zusätzlicher Interaktionen (Post LC) gemeldet werden, sind aber nicht Teil der <strong>Lead Creation Journey</strong>, sodass sie in den FT-, LC- oder U-förmigen Modellen keine Attribution-Credits erhalten.<p>

&#42;Am häufigsten spiegelt die U-förmige Attribution eine gerade 50/50-Aufteilung zwischen FT und LC wider. Wenn der Lead in derselben Sitzung wie der erste Touch konvertiert, stellt ein einzelner Touchpoint sowohl die FT- als auch die LC-Touchpoint-Position dar. Daher würden 100 % der Attribution an einen einzelnen Touchpoint vergeben.</td>
</tr>
 </tbody>
</table>

Diese Modelle legen einen starken Schwerpunkt auf Interaktionen in der Frühphase und die optimale Interaktion mit funnel. Die U-förmige Attribution ist das empfohlene Modell, da es sowohl in den FT- als auch in den LC-Touchpoints berücksichtigt, um sicherzustellen, dass jede Berührung, die den Lead zur Erstellung beeinflusst hat, gutgeschrieben wird. Sie können jedoch zusätzliche insight mit den Modellen Erstkontakt und Lead-Erstellung-Kontakt erhalten, wenn Sie diese spezifischen Teile der Lead-Journey genauer verstehen möchten.

## Empfohlene Berichte unter Verwendung von Buyer Touchpoint (BT) {#recommended-reports-using-the-buyer-touchpoint-bt}

1. **LEADS mit KÄUFER-TOUCHPOINTS**

**,1 € | Neue Leads nach Marketing-**

Die Zusammenfassung der Buyer Touchpoint-Daten Ihres Leads durch das Feld „Marketing-Kanal“ ist die Ansicht der obersten Ebene, die angibt, welche Kanäle/Taktiken neue Leads zur Erstellung beeinflussen. Die Strukturierung dieses Berichts nach einem „Datentyp“ = „Erstellungsdatum“ stellt sicher, dass im Bericht eine Kohorte „neuer Leads“ (als der Lead in Ihrem CRM erstellt wurde) erstellt wird.

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche Marketing-Kanäle beeinflussen Leads in die Erstellung?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Leads und Käufer-Touchpoints (CRM)<br>
   Metrik: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>Lead-Erstellungsdatum (CRM) / Erstellungsdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Erstkontakt, Lead-Erstellung, <strong>U-förmig</strong><br>
   *Summe der Felder 'Anzahl' in Ihren CRM-Berichten (Anzahl - Erstkontakt, Anzahl - Lead-Erstellung, Anzahl - U-förmig)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Beginnen Sie bei jedem Berichtstyp „Leads mit Käufer-Touchpoints“ mit der Anpassung des vordefinierten Berichts mit dem Titel &quot;[!DNL Marketo Measure] 101 | Leads nach Kanal“. Dieser Bericht ist vorkonfiguriert verfügbar und ist eine hervorragende Sandbox, die wie in der obigen Tabelle beschrieben vorkonfiguriert ist und schnell für spezifischere Berichtsanforderungen angepasst werden kann.

**,2 £ | Neue Leads nach Kampagne (oder detailliertere Einblicke)**

Um die Daten, die im Bericht „Neue Leads nach Marketing-Kanal“ (1.1) zusammengefasst sind, detaillierter zu insight zu gestalten, fügen Sie eine zusätzliche Zusammenfassung auf Kampagnenebene hinzu. Auf diese Weise können Sie nicht nur verstehen, was „Marketing-Kanäle“ neue Leads in die Erstellung treiben, sondern insbesondere, welche Kampagnen innerhalb dieser Kanäle die beste Leistung erbringen:

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche <i>Kampagnen</i> beeinflussen Leads in die Erstellung?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Leads und Käufer-Touchpoints (CRM)<br>
   Metrik: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>Lead-Erstellungsdatum (CRM) / Erstellungsdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Anzeigenkampagnenname (CRM)</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Erstkontakt, Lead-Erstellung, <strong>U-förmig</strong><br>
   *Summe der Felder 'Anzahl' in Ihren CRM-Berichten (Anzahl - Erstkontakt, Anzahl - Lead-Erstellung, Anzahl - U-förmig)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Sie erhalten sogar noch detailliertere insight-Informationen, indem Sie den Bericht mit anderen verfügbaren Feldern aus dem Buyer Touchpoint-Objekt zusammenfassen. Legen Sie dazu zusätzliche Gruppierungen (CRM) oder Dimensionen (Discover) fest. Je nach Kanal (der möglicherweise für Ihre Rolle repräsentativ ist) können über die Kampagnenebene, in der Sie insight erhalten möchten, hinaus weitere Details vorhanden sein. Sehen wir uns die „Paid Search“-Liste an, z. B. in der folgenden Tabelle.

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche <i>Keywords</i> beeinflussen Leads in die Erstellung?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Leads und Käufer-Touchpoints (CRM)<br>
   Metrik: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>Marketing-Kanal = Paid Search</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>Lead-Erstellungsdatum (CRM) / Erstellungsdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Keyword Text (CRM) / Keyword (Discover)</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Erstkontakt, Lead-Erstellung, <strong>U-förmig</strong><br>
   *Summe der Felder 'Anzahl' in Ihren CRM-Berichten (Anzahl - Erstkontakt, Anzahl - Lead-Erstellung, Anzahl - U-förmig)</td> 
  </tr>
 </tbody>
</table>

Die Granularität kann je nach Kanal variieren. Es wird empfohlen, sich selbst zu fragen: „Was ist mit &#39;Channel X&#39;, den ich näher verstehen möchte?“. Paid Search-Manager können auch an zusätzlichen Dimensionen interessiert sein, z. B.:

* Name der Anzeigenkampagne
* Anzeigeninhalt
* Anzeigengruppe

Eventmanager könnten jedoch mehr daran interessiert sein, welche bestimmten Ereignisse oder welche Ereignistypen die meisten Einflüsse auf die Erstellung hatten:

* Anzeigenkampagnenname / Salesforce-Kampagne = spezifisches Ereignis
* Medium = Kampagnentyp

**ERINNERUNG**: Zu jeder der oben oder unten beschriebenen Berichtsvarianten müssen möglicherweise zusätzliche Filter hinzugefügt werden. Diese Filter sind für Ihr Unternehmen spezifisch und könnten von Ihren Marketing- oder Vertriebs-Ops-Teams empfohlen werden. Es ist nicht ungewöhnlich, dass Unternehmen dieselben Filter für alle Berichte ausführen, um sicherzustellen, dass der Bericht so sauber und präzise wie möglich ist. Häufige Beispiele:

* Herausfiltern interner Datensätze aus Tests, normalerweise nach E-Mail-Adresse
* Filterung nach bestimmten „Datensatztypen“, die für Ihre Geschäftseinheit spezifisch sein können

**,3 £ | Neue Leads nach Inhalt (nur CRM-Berichte)**

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Was <i>content</i> beeinflussen Leads bei der Erstellung?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Leads und Käufer-Touchpoints (CRM)</td> 
  </tr>
  <tr>
   <td>Datumsfeld</td> 
   <td>Lead Erstellungsdatum</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Landingpage<br> 
   Formular-URL</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Erstkontakt, Lead-Erstellung, <strong>U-förmig</strong><br></td> 
  </tr>
 </tbody>
</table>

**ERINNERUNG**: Die beiden primären Felder für das Reporting zu digitalen Inhalten/Assets sind „Landingpage“ und „Formular-URL“. Diese beiden Werte können identisch sein, wenn der Lead auf derselben Seite, auf der er „gelandet“ ist (Landingpage), konvertiert (ein Formular sendet _,_ diese Werte manchmal jedoch unterschiedlich sind. Der Lead kann beispielsweise auf einen Facebook-Link klicken, über den er zu einer Seite Ihrer Website gelangt (dies wäre der Wert „Landingpage„). Der Lead kann dann von dieser Seite wegnavigieren, seine Sitzung auf der Site fortsetzen und am Ende ein Formular auf einer anderen Seite senden (Formular-URL). Dies würde in einem einzigen Touchpoint zusammengefasst werden, der angibt, wo der Lead herkam (Marketing-Kanal), welche Inhalte sie zur Site geführt haben (Landingpage) und welche Inhalte sie letztendlich heruntergeladen haben (Formular-URL). „Formular-URL“ ist auch das Feld für die Berichterstellung über andere Formulare, die nicht mit herunterladbaren Inhalten verknüpft sind, wie z. B. „Kontakt“- oder „Demo-Anfrage“-Formulare.

>[!TIP]
>
>Insight mit zusätzlichen Filtern in bestimmte „Inhalte“ integrieren
>
>* Filtern nach: &#39;Landingpage&#39; ENTHÄLT (z. B.):
>   * /blog
>   * /ebook
>   * /Webinar
>
>* ODER: &#39;Formular-URL&#39; ENTHÄLT (zum Beispiel)
>   * /Kontakt
>   * /demo

„Inhaltsbasierte“ Berichte bieten einen großen Nutzen bei der Berichterstellung über einen beliebigen Teil der funnel. Sie werden jedoch am häufigsten oben in der funnel verwendet, um zusätzliche insight für eine erste Leads-Interaktion bereitzustellen. Wenn man bedenkt, dass die „organische Suche“ tendenziell der stärkste Kanal ist, um die anfängliche Interaktion (FT) zu fördern, gibt es nicht so viele Daten auf Kampagnenebene.

Inhaltsbasierte Berichte eignen sich hervorragend, um insight mit den Faktoren zu vertraut zu machen, die Leads spezifischerweise im übergeordneten Marketing-Kanal antreiben, in diesem Fall „organische Suche“.

**,4 £ | Gesamte Lead-Interaktion in einem bestimmten Datumsbereich**

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche Marketing-Kanäle hatten in <i> letzten Woche/Monat/Quartal </i> meisten Lead-Interaktionen?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Leads und Käufer-Touchpoints (CRM)<br> 
   Metrik: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>Touchpoint-Datum</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Marketing-Kanal (oder detaillierter)</td> 
  </tr>
  <tr>
   <td>Optimale Modelle*</td> 
   <td>*Dieser Bericht misst mit einem Attributionsmodell weniger, wo Leads herkommen, sondern mehr über die <i>Gesamtzahl der Touchpoints (Interaktionsbetrag)</i> einschließlich derjenigen nach der Touch Lead-Erstellung. Die Gesamtzahl der Touchpoints in den Datensätzen würde zeigen, welche Kanäle die meisten Lead-Interaktionen gesehen haben.</td> 
  </tr>
 </tbody>
</table>

**ERINNERUNG**: Berichte auf der Grundlage des Touchpoint-Datums zu erstellen, ist die beste Methode, die Marketing-Leistung während eines bestimmten Datumsbereichs zu verstehen. „Touchpoint-Datum“ strukturiert den Bericht so, dass die Zuordnung nicht nur zum Kanal, zur Kampagne oder zum Inhalt gehört, sondern auch anzeigt, wann der Touchpoint aufgetreten ist. Dies ist der effektivste Weg, um zu verstehen, welche Marketing-Interaktion zu einem bestimmten Zeitpunkt stattfand, und auch der empfohlene Weg, die Wirkung des Marketings zu messen, da sie mit den Marketingausgaben verglichen wird, die in der gleichen Zeit investiert wurden. Es wird empfohlen, bei der Durchführung von Marketing-Ausgaben- oder ROI-Analysen (siehe 5.1).

**2. MARKETING-QUALIFIZIERTE LEADS MIT KÄUFER-TOUCHPOINTS**

Einer der häufigsten Berichte konzentriert sich nicht nur auf neue Leads oder Interaktionen auf Lead-Ebene, sondern insbesondere auf „Marketing Qualified Leads“ (MQLs). Je nachdem, auf welche [!DNL Marketo Measure] Funktionen Sie Zugriff haben, gibt es verschiedene Ansätze für das Reporting zu MQLs.

**,1 £ | Marketing-qualifizierte Leads nach Kanal (Multi-Touch)**

Dieser Ansatz zur Messung der Wirkung von Marketing auf die Beeinflussung von MQLs ist im Wesentlichen eine Fortsetzung des Berichts „Neue Leads nach Marketing-Kanal“ (1.1), aber mit den zusätzlichen Kriterien, dass die gemessenen Leads speziell MQLs sind. Das U-förmige Attributionsmodell wird hier weiterhin empfohlen, um zu ermitteln, welche Marketing-Kanäle und -Inhalte Leads generieren, die dann (wahrscheinlich _zu_ werden:

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche Marketing-Kanäle sind am besten geeignet, um neue Leads zu generieren, die zu <i>MQLs</i> werden?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Leads und Käufer-Touchpoints (CRM)<br> 
   Metrik: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>MQL = true*<br>
   *<i>MQLs können je nach Organisation unterschiedlich definiert sein. Stellen Sie sicher, dass der [!DNL Marketo Measure]-Bericht nach MQLs gefiltert wird und dabei dieselben Felder verwendet werden wie bei anderen MQL-basierten Berichten. Ein Segmentfilter muss auf die gleiche Weise für das Reporting zu MQLs in [!DNL Marketo Measure] Discover erstellt werden.</i></td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>MQL-Datum (oder gleichwertig) / Erstellungsdatum ([!DNL Marketo Measure] Discover<br> <i>Lead-Erstellungsdatum kann auch im CRM-Reporting verwendet werden, wenn „MQL-Datum“ in Ihrem CRM keine Option ist. Beachten Sie dabei, welches Datumsfeld Sie zum Zeitpunkt verwenden, an dem es den kohortierten Datensatz definiert.</i></td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Erstkontakt, Lead-Erstellung, <strong>U-förmig</strong><br> 
   Summe der Felder 'Anzahl' in Ihren CRM-Berichten (Anzahl - Erstkontakt, Anzahl - Lead-Erstellung, Anzahl - U-förmig)</td> 
  </tr>
 </tbody>
</table>

**,2 £ | Marketing-qualifizierte Leads nach Kanal (nur für einen Kontakt, nur CRM)**

Dieser Ansatz zur Messung der Auswirkungen des Marketings auf die Beeinflussung von MQLs konzentriert sich mehr darauf, herauszufinden, welcher _einzelne Touchpoint_ der letzte Berührungspunkt war, bevor der Lead MQL erreichte.

>[!NOTE]
>
>Um diesen Bericht auszuführen, ist ein „Lead-Status“-Wert von „MQL“ erforderlich, um die MQL-Phase für Tracking-Zwecke (Funnel-Phase) zu definieren. Wenn MQLs nicht über das Feld „Lead-Status“ verfolgt werden, ist das benutzerdefinierte Attributionsmodell mit der Funktion „Benutzerdefinierte Stadien“ erforderlich, um eine benutzerdefinierte „MQL“-Phase in den [!DNL Marketo Measure] Kontoeinstellungen zu erstellen.

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche Marketing-Kanäle drücken die Leads am besten, um den MQL-Status zu erreichen?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Leads und Käufer-Touchpoints (CRM)<br>
   <i>Dieser Bericht ist nur innerhalb von CRM-Berichten möglich. Es ist nicht möglich, in [!DNL Marketo Measure] Discover nach bestimmten Werten für die „Touchpoint-Position“ zu filtern</i></td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td><strong>Touchpoint-Position enthält „MQL“</strong></td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>MQL-Datum (oder gleichwertig)</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td><i>Da dieser Bericht nach einem einzelnen Touchpoint gefiltert wird, sind die Attributionsmodelle auf Lead-Ebene nicht so relevant. Wie beim „Lead-Interaktionsbericht“ (1.4) würde hier die Anzahl der Touchpoint-Datensätze verwendet, um zu verstehen, welche Kanäle am stärksten sind (jeder Lead hätte nur einen MQL-Touchpoint).</i></td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Erkunden Sie andere Gruppierungen oder Dimensionen, um zusätzliche insight in MQLs zu erhalten. Wie bereits in anderen Berichten zum Thema „Leads mit Käufer-Touchpoints“ erwähnt, bietet die Buyer Touchpoint eine wesentlich höhere Granularität als nur ein Marketing-Kanal. Ein „inhaltsbasierter“ Bericht kann auch mit einem der beiden oben genannten MQL-Berichte kombiniert werden, um besser zu verstehen, welche Inhalte MQL am besten beeinflussen.

**3. [!DNL MARKETO MEASURE] PERSONEN MIT KÄUFER-TOUCHPOINTS**

Es gibt ein drittes benutzerdefiniertes [!DNL Marketo Measure] in Salesforce, das bei der Berichterstellung über personenbezogene Metriken sehr nützlich sein kann: **die [!DNL Marketo Measure] Person (BP)**. Der BP löst das uralte Problem, wie Lead- und Kontaktinformationen im selben Bericht dargestellt werden. Sie vereint alle BTs, die mit einer „Person“ verbunden sind (die ID einer [!DNL Marketo Measure] Person ist ihre E-Mail-Adresse). Unabhängig davon, ob es sich um einen Lead oder Kontakt handelt, dient der BP als Überbrückungsobjekt, das die Berichtserstellung über Lead und Kontakt hinweg unterstützt und bei der Erstellung komplexerer Personenberichte sehr nützlich ist.

Die [!DNL Marketo Measure] Person bezieht sich nur auf eines der Touchpoint-Objekte, die Buyer Touchpoint (BT). Das bedeutet, dass es nicht für Opportunity- oder umsatzbezogene Metriken verwendet werden kann. Der Berichtstyp &quot;[!DNL Marketo Measure] Person und Käufer-Touchpoints“ eignet sich hervorragend zum Verständnis _totalen Interaktion_ da er auf allen BTs erscheint, unabhängig davon, ob sich die BT auf einen Lead oder Kontakt bezieht, genauer gesagt. Wenn Sie beispielsweise eine Salesforce-Kampagne zum Tracking eines Ereignisses verwenden, können Sie in der CRM-Kampagne Kampagnenmitglieder haben, die entweder als Leads oder Kontakte existieren. [!DNL Marketo Measure] erstellen unabhängig davon Touchpoints für die Kampagnenmitglieder, aber ohne die [!DNL Marketo Measure] Person erfordern standardmäßige Salesforce-Berichte zwei separate Berichte, um zu verstehen, wie viele _Gesamt_-Touchpoints Sie aus dem Ereignis haben: einen, der „Leads mit Käufer-Touchpoints“ lautet, und einen, der „Kontakte mit Käufer-Touchpoints“ lautet. Einige andere [!DNL Marketo Measure] Anwendungsfälle für personenbasierte Berichte sind unten aufgeführt:

**3.1 [!DNL Marketo Measure] Personen, die „eBooks“ oder „Whitepapers“ heruntergeladen haben (Downloads insgesamt)**

Dieser Bericht entspricht einem „inhaltsbasierten“ Bericht auf Lead-Ebene. Anstatt jedoch die Anzahl der zuordenbaren Leads für jedes Inhaltselement zu messen, ist die Verwendung eines [!DNL Marketo Measure] Persons-Berichts hilfreich, um die Gesamtanzahl _Anzahl der Downloads_ zu verstehen, wenn das Asset gated ist (die Gesamtzahl der Touchpoints würde die Gesamtzahl der Downloads/Formularübermittlungen darstellen).

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Wie viele Personen haben ein bestimmtes Asset heruntergeladen?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>[!DNL Marketo Measure] Personen und Käufer-Touchpoints (CRM)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>'Formular-URL' ENTHÄLT (z. B.<br>
   <li>/ebook</li>
   <li>/Whitepaper</li>
   <i>Die oben genannten Filterwerte sind nur Beispiele. Der tatsächliche Wert basiert auf der URL-Struktur jeder Organisation.</i></td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>Touchpoint-<i> (wann wurde das Asset heruntergeladen)</i></td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Formular/URL</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Dieser Bericht misst mit einem Attributionsmodell weniger, woher die Leads oder Kontakte kommen, sondern mehr über die <i>Gesamtzahl der Touchpoints (Interaktionsbetrag)</i> einschließlich derjenigen nach der Touch Lead-Erstellung. Mit diesem Bericht möchten wir den <i>Umfang der gesamten Interaktion</i> verstehen. Die Gesamtzahl der Touchpoints in den Datensätzen würde zeigen, welche Assets am häufigsten heruntergeladen wurden.</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Beginnen Sie bei jedem Berichtstyp „Leads mit [!DNL Marketo Measure] Personen“ mit der Anpassung des vordefinierten Berichts mit dem Titel &quot;**[!DNL Marketo Measure]101 | Leads/Kontakte nach Kanal**&#39;. Dieser Bericht ist vorkonfiguriert verfügbar und stellt eine hervorragende Sandbox für [!DNL Marketo Measure] Personen dar. Sie ist vorkonfiguriert und kann schnell an spezifischere Berichtsanforderungen angepasst werden.

>[!TIP]
>
>Sie können diesen Bericht verwenden, um insight in die Gesamtinteraktion einer beliebigen Marketing-Dimension aus dem Buyer Touchpoint-Objekt zu integrieren, nicht nur in Form von Inhalts-Downloads, wie im Beispiel gezeigt. Stattdessen kann der Bericht nach Dimensionen wie „Marketing-Kanal“ oder „Anzeigenkampagnenname“ gruppiert oder gefiltert werden, um die Gesamtinteraktion sowohl der Leads als auch der Kontakte in Ihrer Datenbank zu verstehen. Ändern Sie die Filter oder Gruppierungen im Bericht in anderen Dimensionen, die durch andere Felder aus dem Touchpoint-Objekt dargestellt werden, auf Null.

**3.2 [!DNL Marketo Measure] Personen, die sich für eine Veranstaltung registriert haben (nur CRM)**

_Dieser Bericht gilt nur, wenn Registrierungsformulare auf Ihren Websites gehostet werden, die [!DNL Marketo Measure] digital verfolgen können._

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche Marketing-Kanäle treiben meine Veranstaltungsregistrierungen an?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>[!DNL Marketo Measure] Personen und Käufer-Touchpoints (CRM)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>'Formular-URL' ENTHÄLT (z. B.<br>
   <li>/event</li>
   <i>Der obige Filterwert ist nur ein Beispiel. Der tatsächliche Wert basiert auf der URL-Struktur jeder Organisation.</i></td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>Touchpoint-<i> (Zeitpunkt der Übermittlung des Registrierungsformulars)</i></td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Formular-URL<br>
   Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Dieser Bericht misst mit einem Attributionsmodell weniger, woher die Leads oder Kontakte kommen, sondern mehr über die <i>Gesamtzahl der Touchpoints (Anzahl der Registrierungen)</i> einschließlich derjenigen nach der Touch Lead-Erstellung. Mit diesem Bericht möchten wir insight in die Faktoren integrieren, die die Registrierung von Veranstaltungen fördern. Die Gesamtzahl der Touchpoints pro „Marketing-Kanal“ würde zeigen, auf welchen Kanälen die meisten Registrierungen stattfanden.</td> 
  </tr>
 </tbody>
</table>

Die wichtigste Erkenntnis aus diesem Bericht ist, dass die Buyer Touchpoint-Daten auch Daten zu Marketing-Kanälen liefern. Möglicherweise verfügen Sie bereits über insight insight etwa zur Anzahl der Personen, die sich für Ihre Veranstaltungen registriert haben. Dieser Bericht liefert Ihnen aber auch Informationen darüber, welche digitalen Marketing-Kanäle, -Quellen und/oder -Kampagnen Personen auf Ihre Website bringen, um sich dann für die Veranstaltung zu registrieren.

>[!TIP]
>
>Derselbe Ansatz kann gewählt werden, wenn insight bei der Anmeldung zu Webinaren oder bei On-Demand-Webinar-Downloads einbezogen werden soll (wenn es sich um ein gated Asset handelt). Der einzige Unterschied wäre der Filterwert in der „Formular-URL“, wenn diese Formulare auf eindeutigen Seiten Ihrer Website gehostet werden. Das Ziel ist jedoch dasselbe. Es beantwortet die Fragen: „Welche meiner Marketing-Kanäle treiben die meisten Registrierungen/On-Demand-Webinar-Downloads voran.

**3.3 [!DNL Marketo Measure] Personen mit Käufer-Touchpoints (Touchpoint-Validierung)**

In Anbetracht der [!DNL Marketo Measure] Person, die es uns ermöglicht, über alle Touchpoints in einem einzigen Bericht zu berichten, ist dies der ideale Berichtstyp für die Überprüfung Ihrer Daten. Wir möchten sicherstellen, dass wir keine Touchpoints übersehen, die beispielsweise ein Problem bei der Konfiguration Ihrer „Marketing-Kanäle“ offenbaren könnten (weitere Informationen zur Konfiguration Ihrer „Marketing-Kanäle“ finden Sie in den unten verlinkten Support-Artikeln).

* [Benutzerdefiniertes Online-Kanal-Setup](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md){target="_blank"}
* [Benutzerdefinierter Offline-Kanal-Setup](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md){target="_blank"}

Im Wesentlichen spiegeln die Touchpoint-Daten wider, was von [!DNL Marketo Measure] verfolgt wurde, und können geprüft werden, um sicherzustellen, dass Ihre Konfiguration mit Eingaben übereinstimmt, die auf Dingen basieren wie: UTM-Parameterwerten, verweisenden Seiten oder Kampagnentypen. Wenn die Touchpoint-Daten nicht mit Ihrer Konfiguration übereinstimmen, muss wahrscheinlich etwas angepasst werden. Über die Einrichtung des Marketing-Kanals hinaus können Sie sich Touchpoint-Daten ansehen, um zu bestimmen, welche Touchpoints möglicherweise [unterdrückt](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md) oder [segmentiert](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md){target="_blank"} werden müssen. Es wird empfohlen, Ihre Touchpoint-Daten am Ende jedes Monats oder Quartals in einem Bericht zu &quot;[!DNL Marketo Measure] Personen und Käufer-Touchpoints“ zu prüfen, sofern möglich. Dadurch wird sichergestellt, dass Ihre Attribution so genau wie möglich ist. Die &#39;[!DNL Marketo Measure] 101 | Der vorkonfigurierte Bericht zu Leads/Kontakten nach Kanal ist ein guter Ausgangspunkt. Schließen Sie die folgenden Felder ein, wenn sie nicht bereits enthalten sind, um einige der wichtigsten Konfigurationsschritte zu überprüfen:

* **Marketing-Kanal** - Pfad = Marketing-Kanal.UnterKanal (Werte in [!DNL Marketo Measure] festgelegt)
* **Touchpoint Source** = utm_source
* **Medium** = utm_medium (Online-Touchpoints) ODER CRM-Kampagnentyp (Offline-Touchpoints)
* **Referrer-Seite** (wird in der Konfiguration „Online-Kanäle“ verwendet)
* **Landingpage - Roh** (verwendet in der Konfiguration „Online-Kanäle„) ist auch eine gängige Eingabe für die Touchpoint-Unterdrückung in der Registerkarte „Touchpoint-Einstellungen“ Ihrer Einstellungen
* **Formular-URL** (eine gängige Eingabe für die Touchpoint-Unterdrückung auf der Registerkarte „Touchpoint-Einstellungen“ Ihrer Einstellungen)

**BUYER ATTRIBUTION TOUCHPOINT (BAT)**

Attributions-Touchpoints für Käufer (BATs) stellen die relevanten Touchpoints aller Kontakte dar, die mit der Opportunity verbunden sind (entweder über Opportunity-Kontaktrollen oder über eine freigegebene Konto-ID, je nach Ihren Einstellungen). Im Gegensatz zu BT (die hauptsächlich in Verbindung mit Menschen stehen) können BAT mit Einnahmen verbunden sein. Daher verwenden Sie BATs zur Beantwortung von Fragen zu Opportunitys, hauptsächlich offene _Opportunitys/Pipeline-Umsatz_ und geschlossene gewonnene _Opportunitys/Deals/Revenue_. Eine BAT wird über die BT-Datensätze eines Kontakts erstellt, sobald eine Opportunity unter demselben Konto wie der Kontakt erstellt wird (die BT wird nicht in eine BAT konvertiert). Auf die BT-Daten wird einfach verwiesen, um einen zusätzlichen Datensatz zu erstellen (die BAT, die sich dann auf die Opportunity bezieht).

Mit der Buyer Attribution Touchpoint können wir die Wirkung von Marketing in der funnel tiefer messen. _Die Tiefe der funnel, mit der Sie messen möchten, kann durch die verschiedenen Multi-Touch-Attributionsmodelle dargestellt werden_.

In Anbetracht der Tatsache, dass die BVT in erster Linie mit der Opportunity in Verbindung stehen, werden sie zur Beantwortung von Fragen wie den folgenden verwendet:

* Welche meiner Marketing-Maßnahmen haben die meisten Opportunities beeinflusst?
* Wie viel neuer Pipeline-Umsatz kann ich meinen Marketing-Kanälen zuordnen?
* Welche meiner Kampagnen erzielte im letzten Quartal den höchsten ROI?

Die [Attributionsmodelle](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md){target="_blank"} die die beste insight für Opportunity-basierte Metriken bieten, sind:

**W-förmig** - das &quot;_Pipeline-Modell_. Das W-förmige Modell enthält drei Meilenstein-Touchpoints. In diesem Modell werden den Touchpoints FT, LC und OC jeweils 30 % des Attributionskredits zugeordnet. Die restlichen 10 % werden gleichermaßen allen zwischengeschalteten Touchpoints zugeschrieben, die zwischen den drei Milestone-Touchpoints auftreten.

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-2.png"></td> 
   <td>Dieses Modell fasst im Wesentlichen das Journey einer neuen Opportunity zusammen, die normalerweise mit der Generierung neuer Pipeline-Umsätze gleichgesetzt wird.<p>
   <p>
   Wenn Sie die Auswirkungen des Marketings auf neue Opportunities oder die generierte neue Pipeline messen möchten, wird das W-förmige Modell empfohlen.</td> 
  </tr>
 </tbody>
</table>

**Vollständiger Pfad** - das &quot;_Closed Won-Modell_. Dieses Modell enthält die vier Meilenstein-Touchpoints FT, LC, OC und Closed. Jeder erhält 22,5 % des Opportunity-Kredits, und die restlichen 10 % werden gleichmäßig auf die zwischengeschalteten Kontakte verteilt.

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-3.png"></td> 
   <td>Dieses Modell fasst im Wesentlichen das Journey eines abgeschlossenen gewonnenen Deals zusammen, der in der Regel mit abgeschlossenen gewonnenen Umsätzen/Buchungen gleichgesetzt wird.<p>
   <p>
   Wenn Sie die Auswirkungen von Marketing auf abgeschlossene gewonnene Abschlüsse oder abgeschlossene gewonnene Umsätze messen möchten, wird das vollständige Pfadmodell empfohlen.</td> 
  </tr>
 </tbody>
</table>

Dieses Modell fasst im Wesentlichen das Journey eines abgeschlossenen gewonnenen Deals zusammen, der in der Regel mit abgeschlossenen gewonnenen Umsätzen/Buchungen gleichgesetzt wird.

Wenn Sie die Auswirkungen von Marketing auf abgeschlossene gewonnene Abschlüsse oder abgeschlossene gewonnene Umsätze messen möchten, wird das vollständige Pfadmodell empfohlen.

**Benutzerdefiniert** - [!DNL Marketo Measure] bietet auch ein benutzerdefiniertes Attributionsmodell, mit dem Benutzende auswählen können, welche Touchpoints oder benutzerdefinierten Stadien in ihr Modell aufgenommen werden sollen. Darüber hinaus können Benutzer den Prozentsatz des Attributionsguthabens steuern, der diesen Touchpoints und Stadien zugeordnet ist. Abhängig von der Einrichtung Ihres benutzerdefinierten Modells kann es am besten verwendet werden, um entweder Opportunities und Pipeline-ODER, Abschlüsse und abgeschlossene gewonnene Umsätze zu messen. Dies sollten Sie beachten, wenn Sie es in Ihrem Reporting verwenden.

>[!NOTE]
>
>Das benutzerdefinierte Attributionsmodell ist eine zusätzliche Funktion, die nicht allen Kunden zur Verfügung steht. Wenden Sie sich an das Adobe Account Team (Ihren Account Manager), um mehr darüber zu erfahren, wie Sie diese Funktion Ihrem Account hinzufügen können.

Häufig müssen Marketing-Fachleute wissen, „Woher kommen meine Chancen?“. Ähnlich wie beim Reporting auf Lead-Ebene wurde diese Frage in der Vergangenheit mit einem einzigen, eindimensionalen Wert beantwortet (z. B. Primär Campaign Source). Wir wissen jedoch, dass viel mehr in die Entwicklung einer Opportunity als ein einziger Touchpoint von einem einzigen Kontakt geht. Es gibt in der Regel mehrere Touchpoints von verschiedenen Kanälen und von mehreren Stakeholdern, die eine Opportunity in die Erstellung beeinflussen. Mit [!DNL Marketo Measure] können wir alle Touchpoints eines Kontos aufdecken, um am besten zu verstehen, wo eine Opportunity herkam. Darüber hinaus können wir jedoch weiterhin jeden Touchpoint aufdecken, der nach der Erstellung der Opportunity aufgetreten ist, und zwar bis zu dem Punkt, an dem die Opportunity geschlossen ist. Auf diese Weise können wir nicht nur anhand eines Multi-Touch-Ansatzes verstehen, woher eine Opportunity kam, sondern auch, was sie zum Abschluss beeinflusste und letztendlich abgeschlossene gewonnene Einnahmen darstellte. Dadurch wird insight in verschiedene Fragen einbezogen, z. B.: „Wie wirkt sich das Marketing auf den Abschluss von Abschlüssen aus?“, „Welches Marketing treibt den Abschluss von abgeschlossenen Gewinnen voran?“ und schließlich: „Welcher meiner Marketingbemühungen erzielt den größten ROI?“

## EMPFOHLENE BERICHTE UNTER VERWENDUNG VON BUYER ATTRIBUTION TOUCHPOINT (BAT) {#recommended-reports-using-the-buyer-attribution-touchpoint}

**,1 £ | Neue Möglichkeiten nach Marketing-Kanal**

Die Zusammenfassung der Buyer Attribution Touchpoint-Daten Ihrer Opportunities mit dem Feld „Marketing-Kanal“ ist die Ansicht der obersten Ebene, die angibt, welche Kanäle/Taktiken neue Opportunities in die Erstellung beeinflussen. Wenn Sie diesen Bericht nach einem „Datentyp“ = „Erstellungsdatum der Opportunity“ strukturieren, wird sichergestellt, dass der Bericht auch anhand des Zeitpunkts der tatsächlichen Erstellung der Opportunity in Ihrem CRM zusammengefasst wird. Die Touchpoints können aus einer früheren Zeit stammen, beziehen sich jedoch immer noch auf die Opportunitys, die innerhalb des definierten Datumsbereichs erstellt wurden, und erhalten daher eine Attribution-Credits, da sie als Einflussfaktoren auf die Opportunity erkannt werden.

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche <i>Marketing-Kanäle</i> beeinflussen Opportunities in die Kreation?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Attribution Touchpoints von Käufern mit Opportunities (CRM)<br> 
   Metrik: Opportunities ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>
   <li>Opportunity-Stadium* <i>(optional, je nachdem, welche spezifischen Opportunities Sie auf den Bericht beschränken möchten. Sie können nur Berichte zu BATs erstellen, die noch immer nur mit „offenen“ Opportunities verknüpft sind)</i></li>
   <li>Opportunity-Typ (es ist üblich, nach bestimmten Opportunitys zu filtern, d. h. „Neues Unternehmen“ im Gegensatz zu "<i>" </i> Opportunitys)</li><br>
   *In [!DNL Marketo Measure] Discover sollte ein Segmentfilter für „Opportunity-Typ“ verwendet werden.</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>Opportunity-Erstellungsdatum (CRM) / Erstellungsdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td><strong>W-förmig</strong><br>
   Summe der „W-förmigen“ Felder in Ihren CRM-Berichten (Anzahl - W-förmig, Umsatz - W-förmig)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Beginnen Sie bei jedem Berichtstyp „Attribution-Touchpoints des Käufers mit Opportunities“ mit der Anpassung des vordefinierten Berichts mit dem Titel &quot;[!DNL Marketo Measure] 101 | Opportunities nach Kanal &quot;. Dieser Bericht ist vorkonfiguriert verfügbar und ist eine hervorragende Sandbox, die wie in der obigen Tabelle beschrieben vorkonfiguriert ist und schnell an spezifischere Berichtsanforderungen angepasst werden kann (der Bericht verwendet ein vorkonfiguriertes Vollpfadmodell. Stellen Sie daher sicher, dass Sie den Bericht so anpassen, dass er jedes andere Attributionsmodell enthält, in diesem Fall das W-förmige Modell).

>[!TIP]
>
>Der oben beschriebene Bericht würde auch verwendet werden, um zu verstehen, wie viel Währung ebenfalls zugeordnet werden sollte. Bei Berichten auf Opportunity-Ebene mit BATs gibt es zwei Schlüsselmetriken, die zusammengefasst werden können: die Währung (der Betrag der Opportunity) und der Opportunity-Datensatz selbst. Im obigen Beispiel messen wir insbesondere offene Opportunitys und den Umsatz neuer Pipelines.

>[!TIP]
>
>Sie erhalten sogar noch detailliertere insight-Informationen, indem Sie den Bericht mit anderen verfügbaren Feldern aus dem Buyer Attribution Touchpoint-Objekt zusammenfassen. Dies geschieht auf die gleiche Weise wie auf der Lead-Ebene mit Käufer-Touchpoints (1.2). Dies erreichen Sie, indem Sie zusätzliche Gruppierungen (CRM) oder Dimensionen (Discover) hinzufügen. Je nach Kanal (der für Ihre Rolle repräsentativ sein kann) können über die Kampagnenebene hinaus weitere Details vorhanden sein, über die Sie weitere insight erhalten möchten. Sehen wir uns die unten stehende „Paid Search“ an:

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche <i>Keywords</i> aus meinen Paid Search-Anzeigen generieren den meisten Pipeline-Umsatz?
</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Attribution Touchpoints von Käufern mit Opportunities (CRM)<br> 
   Metrik: Opportunities ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>
   <li>Marketing-Kanal = Paid Search</li>
   <li>Opportunity-Stadium* <i>(optional, je nachdem, welche spezifischen Opportunities Sie auf den Bericht beschränken möchten. Dieses Beispiel basiert auf dem Pipeline-Umsatz, der in [!DNL Marketo Measure] durch „Offene“ Vertriebschancen definiert ist (die einen potenziellen Umsatz/eine offene Pipeline darstellen)</i></li>
   <li>Opportunity-Typ (es ist üblich, nach bestimmten Opportunitys zu filtern, d. h. „Neues Unternehmen“ im Gegensatz zu "<i>" </i> Opportunitys)</li><br>
   *In [!DNL Marketo Measure] Discover sollte ein Segmentfilter für „Opportunity-Typ“ verwendet werden.</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>Opportunity-Erstellungsdatum</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Keyword-Text (CRM)<br> 
   Keyword (Discover)</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td><strong>W-förmig</strong><br>
   Summe der „W-förmigen“ Felder in Ihren CRM-Berichten (Anzahl - W-förmig, Umsatz - W-förmig)</td> 
  </tr>
 </tbody>
</table>

**,2 £ | Angebote nach Marketing-Kanal**

Dieser Bericht entspricht im Wesentlichen dem ersten Buyer Attribution Touchpoint-Beispiel (4.1), mit der Ausnahme, dass die Metrik jetzt von „Offene Opportunitys“ zu „Abgeschlossene gewonnene Angebote“ geändert wurde. Die Metrik sollte immer das sein, was darüber aussagt, welches Attributionsmodell verwendet werden soll. Wenn wir jetzt abgeschlossene Won Deals und die zugehörigen BATs betrachten, sollten wir ein Modell verwenden, das die gesamte Journey (Deal) des Käufers darstellt. Dadurch wird sichergestellt, dass jeder Marketing-Touch-Track während der Journey des Käufers Attributionsgutschrift erhält:

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche <i>Marketing-Kanäle</i> beeinflussen den Abschluss von Deals?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Attribution Touchpoints von Käufern mit Opportunities (CRM)<br> 
   Metrik: Angebote ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>
   <li>Opportunity-Stadium (<i>nur abgeschlossene gewonnene Opportunitys sollten im Bericht enthalten sein</i>) ODER</li>
   <li>Opportunity gewonnen = true</li>
   <li>Opportunity-Typ (es ist üblich, nach bestimmten Opportunitys zu filtern, d. h. „Neues Geschäft“ im Gegensatz zu allen Opportunitys)<br>
   </td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datentyp</td> 
   <td>Opportunity Abschlussdatum</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe / Dimension</td> 
   <td>Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td><strong>Vollständiger Pfad</strong><br>
   Summe der Felder „Vollständiger Pfad“ in Ihren CRM-Berichten (Anzahl - Vollständiger Pfad, Umsatz - Vollständiger Pfad)</td> 
  </tr>
 </tbody>
</table>

**ERINNERUNG**: Es ist wichtig, sich daran zu erinnern, nach den spezifischen Opportunitys zu filtern, die in BAT-basierte Berichte aufgenommen werden sollen, insbesondere wenn es um „Offene Opportunitys und Pipeline-Umsatz“ oder „Abschlüsse und abgeschlossene gewonnene Einnahmen“ geht. Dies geschieht normalerweise über einen „Opportunity-Stadium“-Filter (der Filter „Opportunity gewonnen“ = true/false kann hier ebenfalls sehr hilfreich sein).

>[!MORELIKETHIS]
>
>[Neues Handbuch zum Entdecken von Dashboards](/help/marketo-measure-discover-ui/dashboards/new-discover-dashboard-guide.md){target="_blank"}
