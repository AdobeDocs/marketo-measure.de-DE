---
description: "[!DNL Marketo Measure] Reporting-Handbuch - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Reporting-Handbuch"
exl-id: 9b991f9e-c187-4b43-b0a8-8ed3e9a6056b
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '6431'
ht-degree: 2%

---

# [!DNL Marketo Measure] Reporting-Handbuch {#marketo-measure-reporting-guide}

>[!NOTE]
>
>Es werden möglicherweise Anweisungen mit den folgenden Eigenschaften angezeigt:[!DNL Marketo Measure]&quot; in der Dokumentation, sehen aber trotzdem &quot;Bizible&quot;in Ihrem CRM. Wir arbeiten an dieser Aktualisierung, und das Rebranding wird bald in Ihrem CRM zu sehen sein.

Vor dem Erstellen einer [!DNL Marketo Measure] -Bericht, ist es äußerst wichtig, Ihre [!DNL Marketo Measure] Die Kontoeinstellungen wurden überprüft und konfiguriert, um sicherzustellen, dass die Daten in den Berichten korrekt sind und die Besonderheiten Ihres Unternehmens widerspiegeln. Darüber hinaus funktionieren Reporting-Projekte am besten, wenn sie einem strukturierten Prozess folgen. Justin Norris, [!DNL Marketo Measure] Power-User, Advocate und Partner von [Perkuto](https://perkuto.com/) sachkundig zusammengefasst [Vorgehensweise bei der Berichterstellung in [!DNL Marketo Measure]](https://perkuto.com/blog/turning-attribution-data-into-actionable-insights/):

**Ziele festlegen**: &quot;Die erste Frage lautet: &quot;Warum messen wir?&quot; Lori Wizdo of [Forrester Research](https://go.forrester.com/) Sie wurde in einer [Marketo-Webinar](https://www.marketo.com/webinars/beyond-revenue-performance-real-kpis-of-b2b-marketing/). Ihr zufolge &quot;messen wir, um eine Entscheidung oder den Wert des Marketings zu beweisen oder zu validieren oder besser zu werden (Prozessverbesserung)&quot;. Wir würden hinzufügen, dass die Erkenntnisse aus einer guten Messung auch einen Beitrag und eine Anleitung zum Marketing-Planungsprozess liefern.

Bevor Sie also anfangen, ist es wichtig, klar über Ihre Ziele, die Fragen, die Sie zu beantworten versuchen, oder die Probleme, die Sie zu lösen versuchen, zu sein. Welche Geschichte willst du erzählen? Welche Entscheidungen werden sich daraus ergeben? Allzu oft sind diese Grundlagen schlecht durchdacht, was zu Frustration für alle Beteiligten führt.&quot;

**Berichtsdesign**: &quot;Als Nächstes müssen Sie den Bericht entwerfen und die spezifischen Dimensionen, Metriken und Datensätze bestimmen, die er enthalten wird. Eine gängige Erfahrung besteht darin, einem Business-Anwender genau das zu bieten, was er verlangt, nur damit er immer noch das Gefühl hat, dass seine Bedürfnisse nicht erfüllt werden. Dies liegt daran, dass der Einblick, den ein Business-Anwender tatsächlich sucht, nicht immer in dem von ihm angeforderten Bericht enthalten ist. Ein guter Analytiker (oder eine MOPS-Person mit einem Analysten, der aktiv ist) wird Fragen zur Klärung stellen, gemeinsame Definitionen festlegen (&quot;so, was meinen Sie wirklich mit Lead?&quot;) und sogar eine Visualisierung des Abschlussberichts entwerfen, um sicherzustellen, dass eine Anpassung erfolgt. Erst dann erstellen Sie den Bericht in dem Wissen, dass Sie über eine Reihe von Anforderungen verfügen.&quot;

**Berichterstellung**: &quot;Sobald Sie zum Erstellen übergegangen sind, ist es nicht ungewöhnlich, auf Straßenblockaden oder Sackgassen zu stoßen. Sie können beispielsweise feststellen, dass Ihnen ein wichtiger Datenpunkt fehlt oder dass Ihre Objekte nicht so miteinander verknüpft sind, wie Sie es benötigen. Um diese Probleme zu lösen, denke ich auch, dass es wichtig ist zu verstehen, was &quot;unter der Haube&quot; in Ihrer Berichterstellungsmaschine &quot;passiert&quot;. Mit dieser Flexibilität können Sie eine Berichterstellungsanforderung schnell aufstocken und bewerten, ob sie erreichbar ist (und kreative Lösungen leichter entwickeln können, wenn dies nicht möglich ist).&quot;

Sehen wir uns &quot;unter der Haube&quot;an, um besser zu verstehen, was die [!DNL Marketo Measure] Attributionsberichtsrechner ausgeführt werden.

## Touchpoint-Objekte des Käufers (CRM) {#buyer-touchpoint-objects-crm}

Auf der höchsten Ebene gibt es zwei Berichterstellungskategorien, die auf den beiden verschiedenen Touchpoint-Objekten des Käufers basieren: Diese Kategorien bestimmen, welcher Typ von [!DNL Marketo Measure] Daten, über die Sie Berichte erstellen möchten: Daten zu einer _Kontakt_ oder Daten, die sich auf eine _Opportunity_.

1. **Touchpoints des Käufers** (BTs)/Individuelle/Interaktion insgesamt

   * Wird häufig für TOFU-Metriken (Top of the Trichter) und Berichte verwendet, die sich auf _Personen_ (Interessenten, Ansprechpartner, [!DNL Marketo Measure] Personen)
   * BTs werden verwendet, um alle mit **Personen**, da sie den vollständigen Touchpoint-Verlauf für jede Person enthalten. Zur Erinnerung: Diese Touchpoints werden im CRM für den anonymen Erstkontakt, den Lead-Erstellungs-Touch und alle nachfolgenden Formularübermittlungen oder Touchpoints erstellt, die Sie über eine Offline-Kampagne oder -Aktivität synchronisieren möchten.

1. **Touchpoints der Käuferzuordnung** (BVT) / Chancen / Kontoebene / Umsatz

   * Wird häufig für Metriken für &quot;Mittel und/oder unteren Teil des Trichters&quot;(MOFU und BOFU) und Berichte verwendet, die sich auf _Chancen_.
   * Die BVT stellen die relevanten Touchpoints aller Personen dar, die mit dem **Opportunity** (entweder über die Kontaktrollen der Möglichkeiten oder über eine gemeinsam genutzte Konto-ID, je nach Ihren Einstellungen). Im Gegensatz zu BT, die sich nur auf Personen beziehen, können BVT auch mit **Umsatz**. Daher werden Sie BVTs verwenden, um Fragen im Zusammenhang mit Chancen zu beantworten, darunter die Anzahl der eröffneten oder geschlossenen Möglichkeiten oder den Pipeline-Wert und den erzielten Umsatz.

>[!NOTE]
>
>BVT werden aus BTs erstellt. Im Wesentlichen beginnt das Tracking auf individueller Ebene über die BTs. Sobald eine Gelegenheit für ein Konto erstellt wurde, werden alle BTs aus Kontakten unter demselben Konto referenziert und können BATs erstellen, die sich auf die Gelegenheit beziehen. Daher sollten Sie je nachdem, welche Fragen Sie beantworten möchten, eine der beiden verwenden: Fragen zu &quot;Personen&quot;-Metriken (BT-Berichte) oder Fragen zu &quot;Chancen&quot;-Metriken (BAT-Berichte).

Support-Artikel: [Unterschiede zwischen Touchpoints der Käuferzuordnung und Touchpoints der Käuferzuordnung](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md#configuration-and-setup)

## Buyer Touchpoint (BT) {#buyer-touchpoint-bt}

Der Käufer-Touchpoint (BT) ist das Objekt, mit dem jede Marketing-Interaktion verfolgt wird, die jemand mit Ihren Marketing-Materialien hat. Jeder Kontakt (Lead/Kontakt/[!DNL Marketo Measure] Person) Journey würde durch ihre verbundenen BTs vertreten. In [!DNL Marketo Measure], besteht die Journey einer Person aus:

1. Wie hat diese Person zuerst mit unserer Marke interagiert? (Erstkontakt oder _FT_)
1. Wie hat sich diese Person umgestellt / bekannt geworden / ist Lead geworden? (Lead-Erstellung oder _LC_)
1. Wie sonst hat diese Person mit unserer Marke und unseren Marketingmaterialien interagiert, seit sie Lead geworden ist? (_PostLC_)

Touchpoints des Käufers dienen zur Beantwortung von Fragen im Zusammenhang mit _Personen_ (&quot;Personen&quot;werden entweder durch Leads oder Kontakte in einem CRM-System repräsentiert), z. B. durch die Generierung von Leads/Kontakten oder durch Akquise-Metriken, anstatt durch Metriken im Zusammenhang mit Chancen. Beispiel:

* Welche Kanäle liefern die meisten Leads?
* Welche Kanäle sind mehr oder weniger kostspielig, um einen neuen Lead zu erstellen?
* Mit welchem Inhalt beschäftigen sich meine Leads/Kontakte?
* Was ist die Marketing-Geschichte bestimmter Titel, Rollen und Personas?
* Welche Kanäle verhelfen zu MQLs oder anderen Status von Lead/Kontakt?

In erster Linie müssen Unternehmen wissen, &quot;woher kommen meine Leads/Kontakte?&quot; Historisch gesehen wurde dies mit einem einzigen, eindimensionalen Wert beantwortet (z. B. Lead Source). Wie jedoch in den obigen Nummern 1 und 2 beschrieben, wissen wir, dass Leads mehrere Touchpoints während ihrer Journey des Leads haben können. Der Touchpoint des Käufers ermöglicht es uns, einen Einblick in die beiden wichtigsten Interaktionen zu erhalten, die zeigen, wie ein Lead generiert wurde: seinen Erstkontakt und seinen Lead-Kreations-Touch. Touchpoints des Käufers _multidimensional_ bedeutet, dass sie eine Vielzahl von Marketing-Daten übertragen, in erster Linie dort, wo die Person herkam (Marketingkanal) und mit welcher Person sie interagiert hat (Inhalt).

Die [Attributionsmodelle](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md) bieten die besten Einblicke in benutzerbasierte Metriken:

* **Erstkontakt** - 100 %-Attribution zum Erstkontakt (FT) des Leads
* **Lead-Erstellung** - 100 %-Attribution zum Lead-Creation-Touch (LC) des Leads
* **U-förmig** - Multi-Touch-Ansatz, bei dem der FT 40 %, der LC 40 % zugeschrieben werden

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-1.png"></td> 
   <td>Das U-Shape-Modell wurde entwickelt, um jedem Käufer Touchpoints zuzuschreiben, die zusammenfassen, wie ein Lead zu einem Lead wurde. Nachfolgende Touchpoints aus diesen Leads können zwar auch gemeldet werden, um zusätzliche Interaktionen zu verstehen (Post LC), sind jedoch nicht Teil der <strong>Journey zur Lead-Erstellung</strong> sodass sie keine Zuordnungsgutschriften in den FT-, LC- oder U-förmigen Modellen erhalten.<p>

&#42;In den meisten Fällen spiegelt die U-förmige Attribution eine gerade 50/50-Aufteilung zwischen FT und LC wider. Wenn der Lead in derselben Sitzung wie der Erstkontakt konvertiert wird, stellt ein einzelner Touchpoint sowohl die FT- als auch die LC-Touchpoint-Position dar. Daher würden 100 % der Attribution an einen einzelnen Touchpoint vergeben.</td>
</tr>
 </tbody>
</table>

Diese Modelle legen großen Wert auf Interaktionen in der Anfangsphase und auf die Trichterinteraktion. Die U-förmige Attribution ist das empfohlene Modell, da sie sowohl an den FT- als auch an den LC-Touchpoints berücksichtigt wird, um sicherzustellen, dass alle Berührungen, die den Lead bei der Erstellung beeinflusst haben, mit Guthaben versehen werden. Weitere Einblicke erhalten Sie jedoch bei den Modellen Erstkontakt und Lead-Erstellung Touch , wenn Sie diese spezifischen Teile des Lead-Journey genauer verstehen möchten.

## Empfohlene Berichte mit dem Käufer-Touchpoint (BT) {#recommended-reports-using-the-buyer-touchpoint-bt}

1. **LEADS MIT BUYER TOUCHPOINTS**

**1,1 | Neue Leads nach Marketing-Kanal**

Die Zusammenfassung der Touchpoint-Daten des Interessenten-Käufers durch das Feld &quot;Marketing-Kanal&quot;ist die Ansicht auf oberster Ebene, die angibt, welche Kanäle/Taktiken neue Leads bei der Erstellung beeinflussen. Wenn Sie diesen Bericht auf einen Datumstyp (&quot;Erstellungsdatum&quot;) umstellen, wird im Bericht eine Kohorte von &quot;Netto-neue Leads&quot;(wenn der Lead in Ihrem CRM-System erstellt wurde) eingerichtet.

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche Marketingkanäle beeinflussen Leads zur Erstellung?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Interessenten und Käufer-Touchpoints (CRM)<br>
   Metrik: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>Lead-Erstellungsdatum (CRM) / Erstellungsdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Erstkontakt, Lead-Erstellung, <strong>U-förmig</strong><br>
   * Setzen Sie die Felder "Zählung"in Ihre CRM-Berichte (Zählung - Erstkontakt, Zählung - Lead-Erstellung, Zählung - U-förmig).</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Beginnen Sie bei allen Berichtstypen &quot;Leads mit Käufer-Touchpoints&quot;mit der Anpassung des vordefinierten Berichts mit dem Titel &quot;[!DNL Marketo Measure] 101 | Leads nach Kanal&quot;. Dieser Bericht ist standardmäßig verfügbar und ist eine großartige, vorkonfigurierte Sandbox, wie in der obigen Tabelle beschrieben, und kann schnell für spezifischere Berichtsanforderungen angepasst werden.

**1,2 | Neue Leads nach Campaign (oder detailliertere Einblicke)**

Für einen detaillierteren Einblick in die Daten, die im Bericht &quot;Neue Leads nach Marketing-Kanal&quot;(1.1) zusammengefasst sind, fügen Sie eine zusätzliche Zusammenfassung auf Kampagnenebene hinzu. Auf diese Weise können Sie nicht nur verstehen, welche &quot;Marketing-Kanäle&quot;neue Leads zur Erstellung bringen, sondern insbesondere, welche Kampagnen innerhalb dieser Kanäle die beste Leistung erzielen:

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Was <i>Kampagnen</i> beeinflussen Leads in die Erstellung?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Interessenten und Käufer-Touchpoints (CRM)<br>
   Metrik: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>Lead-Erstellungsdatum (CRM) / Erstellungsdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Name der Anzeigenkampagne (CRM)</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Erstkontakt, Lead-Erstellung, <strong>U-förmig</strong><br>
   * Setzen Sie die Felder "Zählung"in Ihre CRM-Berichte (Zählung - Erstkontakt, Zählung - Lead-Erstellung, Zählung - U-förmig).</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Erhalten Sie noch detailliertere Einblicke, indem Sie den Bericht mit anderen verfügbaren Feldern aus dem Touchpoint-Objekt &quot;Käufer&quot;zusammenfassen. Setzen Sie dazu zusätzliche Gruppierungen (CRM) oder Dimensionen (Discover) ein. Abhängig vom Kanal (der möglicherweise für Ihre Rolle repräsentativ ist) können über die Kampagnenebene hinaus weitere Details angezeigt werden, über die Sie Einblicke gewinnen möchten. Gehen wir zum Beispiel in die &quot;Paid Search&quot;-Tabelle unten...

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Was <i>Schlüsselwörter</i> beeinflussen Leads in die Erstellung?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Interessenten und Käufer-Touchpoints (CRM)<br>
   Metrik: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>Marketing-Kanal = Gebührenpflichtige Suche</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>Lead-Erstellungsdatum (CRM) / Erstellungsdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Schlüsselworttext (CRM)/Suchbegriff (Discover)</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Erstkontakt, Lead-Erstellung, <strong>U-förmig</strong><br>
   * Setzen Sie die Felder "Zählung"in Ihre CRM-Berichte (Zählung - Erstkontakt, Zählung - Lead-Erstellung, Zählung - U-förmig).</td> 
  </tr>
 </tbody>
</table>

Die Granularität kann je nach Kanal variieren. Der empfohlene Ansatz wäre, sich zu fragen: &quot;Was ist mit &#39;channel X&#39;, den ich genauer verstehen möchte?&quot; Manager für gebührenpflichtige Suchvorgänge können auch an zusätzlichen Dimensionen wie folgenden interessiert sein:

* Name der Anzeigenkampagne
* Anzeigeninhalt
* Anzeigengruppe

Eventmanager können jedoch mehr daran interessiert sein, welche bestimmten Ereignisse oder welche Arten von Ereignissen die meisten Interessenten bei der Erstellung beeinflusst haben:

* Anzeigenkampagnenname / Salesforce-Kampagne = spezifisches Ereignis
* Mittel = Kampagne &#39;Typ&#39;

**ERINNERUNG**: Zusätzliche Filter müssen ggf. zu den oben oder unten beschriebenen Berichtsvarianten hinzugefügt werden. Diese Filter sind unternehmensspezifisch und können von Ihren Marketing Ops- oder Sales Ops-Teams empfohlen werden. Es ist nicht ungewöhnlich, dass eine Organisation dieselben Filter für alle Berichte durchführt, um sicherzustellen, dass der Bericht so sauber und präzise wie möglich ist. Häufige Beispiele sind:

* Filtern interner Datensätze aus Tests, in der Regel nach E-Mail-Adresse
* Filterung anhand bestimmter &quot;Datensatztypen&quot;, die für Ihr Geschäftsfeld spezifisch sein können

**1,3 | Neue Leads nach Inhalt (nur CRM-Berichte)**

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Was <i>content</i> beeinflussen Leads in die Erstellung?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Interessenten und Käufer-Touchpoints (CRM)</td> 
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
   <td>Gruppe/Dimension</td> 
   <td>Landingpage<br> 
   Formular-URL</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Erstkontakt, Lead-Erstellung, <strong>U-förmig</strong><br></td> 
  </tr>
 </tbody>
</table>

**ERINNERUNG**: Die beiden Hauptfelder für die Berichterstellung über digitale Inhalte/Assets sind &quot;Landingpage&quot;und &quot;Formular-URL&quot;. Diese beiden Werte können identisch sein, wenn der Lead auf derselben Seite, auf der er &quot;gelandet&quot; hat (Landingpage) konvertiert (ein Formular sendet), _jedoch_, sind diese Werte manchmal anders. Beispielsweise kann der Lead auf einen Link in Facebook klicken, über den sie zu einer Seite Ihrer Website gelangen (dies wäre der Wert &quot;Landingpage&quot;). Der Lead kann dann von dieser Seite weg navigieren, seine Sitzung auf der Site fortsetzen und schließlich ein Formular auf einer anderen Seite senden (Formular-URL). Dies würde in einem einzigen Touchpoint zusammengefasst, der angibt, woher der Lead stammt (Marketingkanal), welcher Inhalt ihn zur Site brachte (Landingpage) und welcher Inhalt schließlich heruntergeladen wurde (Formular-URL). &quot;Formular-URL&quot;ist auch das Zielfeld für die Berichterstellung zu anderen Formularen, die nicht mit herunterladbaren Inhalten wie &quot;Kontakt&quot;oder &quot;Demo-Anfrage&quot;verknüpft sind.

>[!TIP]
>
>Hier erhalten Sie Einblicke in bestimmte &quot;Inhalte&quot;mit zusätzlichen Filtern.
>
>* Filtern nach: &quot;Landingpage&quot;ENTHÄLT (z. B.:
>   * /blog
>   * /ebook
>   * /webinar
>
>* ODER: &quot;Formular-URL&quot;ENTHÄLT (z. B.)
>   * /contact
>   * /demo

Inhaltsbasierte Berichte bieten bei der Berichterstellung für einen beliebigen Teil des Trichters einen großen Wert. Sie werden jedoch am häufigsten oben im Trichter verwendet, um zusätzliche Einblicke in die anfängliche Interaktion der Leads zu erhalten. Wenn man bedenkt, dass &quot;Organische Suche&quot;der stärkste Kanal bei der Förderung der anfänglichen Interaktion ist, gibt es nicht so viele Daten auf Kampagnenebene.

Inhaltsbasierte Berichte eignen sich hervorragend, um Einblicke in die treibenden Faktoren von Leads im übergeordneten Marketingkanal zu erhalten, in diesem Fall &quot;Organische Suche&quot;.

**1,4 | Gesamte Lead-Interaktion in einem bestimmten Datumsbereich**

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche Marketing-Kanäle hatten die meisten <i>Gesamte Lead-Interaktion</i> in der Vergangenheit (Woche/Monat/Quartal)?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Interessenten und Käufer-Touchpoints (CRM)<br> 
   Metrik: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>Touchpoint-Datum</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Marketingkanal (oder granularer)</td> 
  </tr>
  <tr>
   <td>Optimale Modelle*</td> 
   <td>*Bei diesem Bericht geht es weniger darum zu messen, woher Leads mit einem Attributionsmodell stammen, sondern mehr um die <i>Gesamtzahl der Touchpoints (Interaktionsmenge)</i>, inklusive derer nach dem Lead-Kreationstreffen. Die Gesamtzahl der Touchpoints in den Datensätzen würde widerspiegeln, welche Kanäle die am meisten Interessenten-Interaktion gesehen haben.</td> 
  </tr>
 </tbody>
</table>

**ERINNERUNG**: Die Stützung Ihrer Berichte auf das &quot;Touchpoint-Datum&quot;ist die beste Methode, die Marketing-Performance in einem bestimmten Datumsbereich zu verstehen. &quot;Touchpoint-Datum&quot;strukturiert den Bericht so, dass die Attribution nicht nur mit dem Kanal, der Kampagne oder dem Inhalt in Beziehung steht, sondern auch anzeigt, wann der Touchpoint aufgetreten ist. Dies ist die effektivste Methode, um zu verstehen, welche Marketing-Interaktionen zu einem bestimmten Zeitpunkt stattfanden, und auch die empfohlene Methode zur Messung der Auswirkungen des Marketing, da sie mit den gleichzeitig investierten Marketing-Ausgaben verglichen werden. Es wird empfohlen, Marketingausgaben oder ROI-Analysen zu verwenden (siehe 5.1).

**2. MARKETING QUALIFIZIERTER LEADS MIT KÄUFERTOUCHPOINTS**

Einer der häufigsten Berichte konzentriert sich nicht nur auf neue Leads oder Interaktionen auf Lead-Ebene, sondern insbesondere auf &quot;Marketing-qualifizierte Leads&quot;(MQLs). Es gibt verschiedene Ansätze für die Berichterstellung über MQLs, je nachdem, was [!DNL Marketo Measure] Funktionen, auf die Sie Zugriff haben.

**2,1 | Marketing-qualifizierte Leads nach Kanal (Multi-Touch)**

Dieser Ansatz zur Messung der Auswirkungen des Marketing auf die Einflussnahme auf MQLs ist im Wesentlichen eine Fortsetzung des Berichts &quot;Neue Leads nach Marketing-Kanal&quot;(1.1), jedoch mit den zusätzlichen Kriterien, die bei den gemessenen Leads gemessen werden, handelt es sich um spezifischere MQLs. Das U-förmige Attributionsmodell wird hier weiterhin empfohlen, um zu ermitteln, welche Marketing-Kanäle und Inhalte zu Leads führen, die dann generiert werden _wahrscheinlich_ So werden Sie zu einer MQL:

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche Marketing-Kanäle eignen sich am besten, um neue Leads zu generieren, die zu <i>MQs</i>?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Interessenten und Käufer-Touchpoints (CRM)<br> 
   Metrik: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>MQL = true*<br>
   *<i>MQLs können für jede Organisation unterschiedlich definiert werden. Stellen Sie die [!DNL Marketo Measure] nach MQLs gefiltert werden, indem dieselben Felder verwendet werden wie bei anderen MQL-basierten Berichten. Für die Berichterstellung zu MQLs in muss auf die gleiche Weise ein Segmentfilter erstellt werden [!DNL Marketo Measure] Entdecken Sie.</i></td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>MQL-Datum (oder gleichwertiges Datum) / Erstellungsdatum ([!DNL Marketo Measure] Discover)<br> <i>Das Lead-Erstellungsdatum kann auch in CRM-Berichten verwendet werden, wenn das MQL-Datum keine Option in Ihrem CRM-System ist. Beachten Sie dabei, welches Datumsfeld Sie verwenden, um den kohortierten Datensatz zu definieren.</i></td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>Erstkontakt, Lead-Erstellung, <strong>U-förmig</strong><br> 
   Setzen Sie die Felder "Zählung"in Ihre CRM-Berichte ein (Zählung - Erstkontakt, Zählung - Lead-Erstellung, Zählung - U-förmig).</td> 
  </tr>
 </tbody>
</table>

**2,2 | Marketing-qualifizierte Leads nach Kanal (nur Einzelkontakt, CRM)**

Dieser Ansatz zur Messung der Auswirkungen des Marketing auf die Einflussnahme auf MQLs konzentriert sich mehr auf die Ermittlung, welche _einzelner Touchpoint_ war der letzte Kontakt, bevor der Lead die MQL erreichte.

>[!NOTE]
>
>Um diesen Bericht auszuführen, ist der Wert &quot;Lead-Status&quot;von &quot;MQL&quot;erforderlich, um die MQL-Phase zu Tracking-Zwecken (Trichterphase) zu definieren. Wenn MQLs nicht über das Feld &quot;Lead-Status&quot;verfolgt werden, ist die Funktion Benutzerdefiniertes Attributionsmodell mit benutzerdefinierten Phasen erforderlich, um eine benutzerdefinierte &quot;MQL&quot;-Phase im [!DNL Marketo Measure] Kontoeinstellungen.

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche Marketing-Kanäle bringen Leads am stärksten zum Erreichen des MQL-Status?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Interessenten und Käufer-Touchpoints (CRM)<br>
   <i>Dieser Bericht ist nur in CRM-Berichten möglich. Es ist nicht möglich, bestimmte Werte der "Touchpoint-Position"unter [!DNL Marketo Measure] Discover</i></td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td><strong>Touchpoint-Position ENTHÄLT "MQL"</strong></td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>MQL-Datum (oder gleichwertiges Datum)</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td><i>Da dieser Bericht nach einem einzelnen Touchpoint gefiltert wird, sind die Attributionsmodelle auf Lead-Ebene nicht so relevant. Wie der "Bericht zur Lead-Interaktion"(1.4) würde hier die Anzahl der Touchpoint-Datensätze verwendet, um zu verstehen, welche Kanäle am stärksten sind (jeder Lead hätte nur einen MQL-Touchpoint).</i></td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Erkunden Sie andere Gruppierungen oder Dimensionen, um weitere Einblicke in MQLs zu erhalten. Wie in den anderen Berichten &quot;Interessenten mit Kunden-Touchpoints&quot;erwähnt, bietet der Käufer-Touchpoint deutlich mehr Granularität als nur der Marketing-Kanal. Ein &quot;Content&quot;-basierter Bericht könnte auch mit einem der oben genannten MQL-Berichte kombiniert werden, um besser zu verstehen, welchen Inhalt MQLs am besten beeinflusst.

**3. [!DNL MARKETO MEASURE] PERSONEN MIT KÄUFERTOUCHPOINTS**

Es gibt einen dritten Brauch [!DNL Marketo Measure] -Objekt in Salesforce verwenden, das bei der Berichterstellung zu personenbezogenen Metriken sehr nützlich sein kann: **die [!DNL Marketo Measure] Person (BP)**. Das BP löst das jahrhundertealte Problem, wie die Leads- und Kontaktinformationen im selben Bericht dargestellt werden. Sie vereint alle BTs, die mit einer &quot;Person&quot; (einer [!DNL Marketo Measure] Die Kennung der Person ist ihre E-Mail-Adresse). Unabhängig davon, ob sie als Lead oder Kontakt existieren, fungiert das BP als Brückenobjekt, um Berichte über Lead und Kontakt hinweg zu ermöglichen, und ist sehr nützlich bei der Erstellung komplexerer Personenberichte.

Die [!DNL Marketo Measure] Person bezieht sich nur auf eines der Touchpoint-Objekte, den Käufer Touchpoint (BT). Dies bedeutet, dass sie nicht für eine Metrik im Zusammenhang mit Chancen oder Umsatz verwendet werden kann. A &#39;[!DNL Marketo Measure] Der Berichtstyp &quot;Touchpoints&quot;vom Typ &quot;Person&quot;und &quot;Käufer&quot;eignet sich hervorragend zum Verständnis _Gesamtinteraktion_ da sie alle BTs überdeckt, ob sich der BT auf einen Lead oder Kontakt bezieht. Wenn beispielsweise eine Salesforce-Kampagne zur Verfolgung eines Ereignisses verwendet wird, können Kampagnenmitglieder in der CRM-Kampagne vorhanden sein, die entweder als Leads ODER Kontakte bestehen. [!DNL Marketo Measure] Touchpoints für die Kampagnenmitglieder erstellen, unabhängig davon, aber ohne [!DNL Marketo Measure] Für die standardmäßige Salesforce-Berichterstellung wären zwei separate Berichte erforderlich, um zu verstehen, wie viele _total_ Touchpoints, die Sie aus dem Event haben, sind &quot;Leads mit Kunden-Touchpoints&quot;und &quot;Kontakte mit Kunden-Touchpoints&quot;. Einige andere [!DNL Marketo Measure] Unten finden Sie die Anwendungsfälle für personenbasierte Berichte:

**3,1 [!DNL Marketo Measure] Personen, die &quot;ebooks&quot;oder &quot;whitepapers&quot;heruntergeladen haben (Gesamtzahl der Downloads)**

Dieser Bericht wäre mit einem inhaltsbasierten Bericht auf Lead-Ebene identisch. Anstatt jedoch die Anzahl der zurechenbaren Leads für jeden Inhalt zu messen, verwenden Sie eine [!DNL Marketo Measure] Der Personenbericht ist hilfreich beim Verständnis der Gesamtsumme _Anzahl der Downloads_ wenn das Asset erfasst wird (die Gesamtzahl der Touchpoints entspricht der Gesamtanzahl der Downloads/Formularübermittlungen).

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
   <td>"Formular-URL"ENTHÄLT (Beispiel)<br>
   <li>/ebook</li>
   <li>/whitepaper</li>
   <i>Die oben genannten Filterwerte sind nur Beispiele. Der tatsächliche Wert basiert auf der URL-Struktur jedes Unternehmens.</i></td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>Touchpoint-Datum <i>(wann wurde das Asset heruntergeladen)</i></td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Formular/URL</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>In diesem Bericht geht es weniger darum zu messen, woher die Leads oder Kontakte mit einem Attributionsmodell kommen, sondern mehr um die <i>Gesamtzahl der Touchpoints (Interaktionsmenge)</i>, inklusive derer nach dem Lead-Kreationstreffen. Mit diesem Bericht möchten wir die <i>Interaktionsbetrag insgesamt</i>. Die Gesamtzahl der Touchpoints im Datensatz gibt an, welche Assets am häufigsten heruntergeladen wurden.</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Für &quot;Leads mit&quot; [!DNL Marketo Measure] Berichtstyp der Person, beginnen Sie mit der Anpassung des vordefinierten Berichts mit dem Titel &#39;**[!DNL Marketo Measure]101 | Leads/Kontakte nach Kanal**&quot;. Dieser Bericht ist vorkonfiguriert verfügbar und ist eine großartige [!DNL Marketo Measure] Personalisierte Sandbox. Sie ist vorkonfiguriert und kann schnell für spezifischere Berichtsanforderungen angepasst werden.

>[!TIP]
>
>Sie können diesen Bericht verwenden, um Einblicke in die Gesamtinteraktion einer Marketing-Dimension vom Touchpoint-Objekt des Käufers zu erhalten, nicht nur in die im Beispiel dargestellten Inhalts-Downloads. Stattdessen kann der Bericht nach Dimensionen wie &quot;Marketing-Kanal&quot;oder &quot;Anzeigenkampagnenname&quot;gruppiert oder gefiltert werden, um die Gesamtinteraktion sowohl von Leads als auch von Kontakten in Ihrer Datenbank besser zu verstehen. Ändern Sie einfach die Filter oder Gruppierungen im Bericht in anderen Dimensionen, die durch andere Felder des Touchpoint-Objekts dargestellt werden, auf null.

**3,2 [!DNL Marketo Measure] Personen, die sich für ein Ereignis registriert haben (nur CRM)**

_Dieser Bericht ist nur anwendbar, wenn Registrierungsformulare auf Ihrer Website gehostet werden, die [!DNL Marketo Measure] kann digital nachverfolgen._

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welche Marketingkanäle lenken meine Ereignisregistrierungen?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>[!DNL Marketo Measure] Personen und Käufer-Touchpoints (CRM)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>"Formular-URL"ENTHÄLT (Beispiel)<br>
   <li>/event</li>
   <i>Der obige Filterwert ist nur Beispiele. Der tatsächliche Wert basiert auf der URL-Struktur jedes Unternehmens.</i></td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>Touchpoint-Datum <i>(Zeitpunkt der Übermittlung des Registrierungsformulars)</i></td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Formular-URL<br>
   Marketingkanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td>In diesem Bericht geht es weniger darum zu messen, woher die Leads oder Kontakte mit einem Attributionsmodell kommen, sondern mehr um die <i>Gesamtzahl der Touchpoints (Anzahl der Registrierungen)</i>, inklusive derer nach dem Lead-Kreationstreffen. Mit diesem Bericht möchten wir Einblicke in die Ursachen von Ereignisregistrierungen erhalten. Die Gesamtzahl der Touchpoints pro "Marketing-Kanal"würde widerspiegeln, welche Kanäle zu den meisten Registrierungen geführt haben.</td> 
  </tr>
 </tbody>
</table>

Der Hauptgrund für diesen Bericht besteht darin, dass die Käufer-Touchpoint-Daten auch Marketingkanaldaten bereitstellen. Vielleicht haben Sie bereits Einblicke in die Anzahl der Personen, die sich für Ihre Veranstaltungen registriert haben, aber dieser Bericht bietet auch Einblicke in die digitalen Marketing-Kanäle, Quellen und/oder Kampagnen, die Menschen auf Ihre Website bringen und sich dann für die Veranstaltung registrieren lassen.

>[!TIP]
>
>Dieser Ansatz ist auch möglich, wenn Sie Einblicke in Webinar-Registrierungen oder möglicherweise On-Demand-Webinar-Downloads erhalten möchten (wenn es sich um ein abgegrenztes Asset handelt). Der einzige Unterschied wäre der Filterwert in der Formular-URL, wenn diese Formulare auf eindeutigen Seiten Ihrer Website gehostet werden. Das Ziel ist jedoch dasselbe. Es beantwortet die Fragen, &quot;welche meiner Marketing-Kanäle zu den meisten Registrierungen/On-Demand-Webinar-Downloads führen.

**3,3 [!DNL Marketo Measure] Personen mit Touchpoints des Käufers (Touchpoint-Überprüfung)**

Beachten Sie die [!DNL Marketo Measure] Personen ermöglicht es uns, über alle Touchpoints in einem einzigen Bericht zu berichten. Dies ist der ideale Berichtstyp, der bei der Überprüfung Ihrer Daten verwendet werden sollte. Wir möchten sicherstellen, dass wir keine Touchpoints übersehen, die zeigen könnten, wo beispielsweise ein Problem in der Konfiguration Ihrer &quot;Marketing-Kanäle&quot;liegt (weitere Informationen zur Konfiguration Ihrer &quot;Marketing-Kanäle&quot;finden Sie in den unten verlinkten Support-Artikeln ).

* [Online-Einrichtung benutzerdefinierter Kanäle](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
* [Offline-Einrichtung benutzerdefinierter Kanäle](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)

Im Grunde spiegeln die Touchpoint-Daten wider, von welchen [!DNL Marketo Measure] und können geprüft werden, um sicherzustellen, dass Ihre Konfiguration Eingaben basierend auf Folgendem abgleicht: UTM-Parameterwerte, verweisende Seiten oder Kampagnentypen. Wenn die Touchpoint-Daten nicht mit Ihrer Konfiguration übereinstimmen, muss höchstwahrscheinlich etwas angepasst werden. Über das Setup des Marketing-Kanals hinaus können Sie sich Touchpoint-Daten ansehen, um zu bestimmen, welche Touchpoints möglicherweise benötigt werden [unterdrückt](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md) oder [segmentiert](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md). Es wird empfohlen, Ihre Touchpoint-Daten in einem[!DNL Marketo Measure] Personen und Kunden-Touchpoints-Bericht am Ende jedes Monats oder Quartals, sofern möglich. Dadurch wird sichergestellt, dass Ihre Attribution so präzise wie möglich ist. Der[!DNL Marketo Measure] 101 | Der vordefinierte Bericht Leads/Kontakte nach Kanal ist ein guter Ausgangspunkt. Schließen Sie die folgenden Felder ein, wenn sie noch nicht enthalten sind, um einige der wichtigsten Konfigurationselemente zu überprüfen:

* **Marketingkanal** - Path = Marketing Channel.Subchannel (Werte festgelegt in [!DNL Marketo Measure])
* **Touchpoint-Quelle** = utm_source
* **Mittel** = utm_medium (Online-Touchpoints) ODER CRM-Kampagnentyp (Offline-Touchpoints)
* **Referrer Page** (Verwendung der Konfiguration &quot;Online-Kanäle&quot;)
* **Landingpage - Roh** (über die Konfiguration &quot;Online-Kanäle&quot;) auch eine allgemeine Eingabe für die Touchpoint-Unterdrückung auf der Registerkarte &quot;Touchpoint-Einstellungen&quot;Ihrer Einstellungen)
* **Formular-URL** (eine allgemeine Eingabe für die Unterdrückung von Touchpoints auf der Registerkarte &quot;Touchpoint-Einstellungen&quot;Ihrer Einstellungen)

**TOUCHPOINT (BAT) DER KÄUFERATTRIBUTION**

Die &quot;Buyer Attribution Touchpoints&quot;(BAT) stellen die relevanten Touchpoints aller Kontakte dar, die mit der Möglichkeit verbunden sind (entweder über die Kontaktrollen der Opportunity oder über eine gemeinsam genutzte Konto-ID, je nach Ihren Einstellungen). Im Gegensatz zu BTs (die hauptsächlich mit Personen verbunden sind) können BVTs mit Umsätzen verknüpft werden. Daher werden Sie BVT verwenden, um Fragen im Zusammenhang mit Chancen zu beantworten, in erster Linie offene _Chancen/Pipeline-Umsatz_ und geschlossen _Chancen/Angebote/Umsatz_. Ein BVT wird über die BT-Datensätze eines Kontakts erstellt, sobald eine Möglichkeit unter demselben Konto wie der Kontakt erstellt wird (der BT wird nicht in ein BVT umgewandelt. Auf die BT-Daten wird einfach verwiesen, um einen zusätzlichen Datensatz zu erstellen - die BVT, die sich dann auf die Möglichkeit bezieht).

Mit dem Touchpoint &quot;Käuferzuordnung&quot;können wir die Wirkung des Marketing-Systems im Trichter tiefer messen. _Die Tiefe des Trichters, mit dem Sie messen möchten, kann durch die verschiedenen Multi-Touch-Attributionsmodelle dargestellt werden_.

In Anbetracht der Tatsache, dass die BVT in erster Linie mit der Chance in Beziehung steht, werden sie zur Beantwortung von Fragen wie etwa:

* Welche meiner Marketing-Maßnahmen haben die meisten Chancen beeinflusst?
* Wie viel neuer Pipeline-Umsatz kann ich jedem meiner Marketing-Kanäle zuordnen?
* Welche meiner Kampagnen verzeichneten den größten ROI im letzten Quartal?

Die [Attributionsmodelle](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md) bieten beste Einblicke in Opportunity-basierte Metriken:

**W-förmig** - &quot;_Pipeline-Modell_&quot;. Das W-förmige Modell umfasst drei Meilensteinkontaktpunkte. In diesem Modell werden den Touchpoints FT, LC und OC jeweils 30 % des Attributionskredits zugeordnet. Die verbleibenden 10 % werden zu gleichen Teilen allen zwischengeschalteten Touchpoints zugeordnet, die zwischen den drei Meilenstein-Touchpoints auftreten.

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-2.png"></td> 
   <td>Dieses Modell fasst im Wesentlichen die Journey einer neuen Chance zusammen, die normalerweise mit der Generierung neuer Pipeline-Umsätze synonym ist.<p>
   <p>
   Wenn Sie die Auswirkungen des Marketing auf neue Chancen oder neu generierte Pipeline messen möchten, wird das W-förmige Modell empfohlen.</td> 
  </tr>
 </tbody>
</table>

**Vollständiger Pfad** - &quot;_Geschlossenes Won-Modell_&quot;. Dieses Modell umfasst die vier Meilensteinkontaktpunkte FT, LC, OC und Closed. Jeder erhält 22,5% des Opportunity-Kredits, und die verbleibenden 10% werden gleichmäßig auf die zwischengeschalteten Touches verteilt.

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-3.png"></td> 
   <td>Dieses Modell fasst im Wesentlichen die Journey eines geschlossenen Gewinnergeschäfts zusammen, das typischerweise mit geschlossenen Gewinnen Umsatz/Buchungen gleichgesetzt wird.<p>
   <p>
   Wenn Sie die Auswirkungen des Marketing auf geschlossene Angebote oder geschlossene Gewinne messen möchten, wird das vollständige Pfadmodell empfohlen.</td> 
  </tr>
 </tbody>
</table>

Dieses Modell fasst im Wesentlichen die Journey eines geschlossenen Gewinnergeschäfts zusammen, das typischerweise mit geschlossenen Gewinnen Umsatz/Buchungen gleichgesetzt wird.

Wenn Sie die Auswirkungen des Marketing auf geschlossene Angebote oder geschlossene Gewinne messen möchten, wird das vollständige Pfadmodell empfohlen.

**Benutzerdefiniert** - [!DNL Marketo Measure] bietet außerdem ein Custom Attribution-Modell, mit dem Benutzer auswählen können, welche Touchpoints oder benutzerdefinierten Bühnen in ihr Modell aufgenommen werden sollen. Darüber hinaus können Benutzer den Prozentsatz des Attributionszuschreibens steuern, der diesen Touchpoints und Phasen zugeordnet wird. Je nach Einrichtung Ihres benutzerdefinierten Modells kann es am besten verwendet werden, um entweder Chancen und Pipeline-ODER-, Angebote- und geschlossene Umsatz zu messen. Beachten Sie dies bei der Verwendung in Ihren Berichten.

>[!NOTE]
>
>Das benutzerdefinierte Attributionsmodell ist eine zusätzliche Funktion, die nicht allen Kunden zur Verfügung steht. Wenden Sie sich an das Adobe Account Team (Ihren Kundenbetreuer), um mehr über das Hinzufügen dieser Funktion zu Ihrem Konto zu erfahren.

Im Allgemeinen müssen Marketing-Experten wissen, &quot;woher kommen meine Chancen?&quot; Ähnlich wie bei Berichten auf Lead-Ebene wurde diese Frage historisch mit einem einzigen eindimensionalen Wert beantwortet (z. B. Primäre Kampagnenquelle). Wir wissen jedoch, dass viel mehr in die Entwicklung einer Chance geht als ein einzelner Kontaktpunkt aus einem einzigen Kontakt. Es gibt in der Regel mehrere Touchpoints aus verschiedenen Kanälen und von mehreren Interessengruppen, die eine Chance zur Erstellung beeinflussen. Mit [!DNL Marketo Measure]können wir alle Touchpoints aus einem Konto aufdecken, um am besten zu verstehen, woher eine Gelegenheit kam. Darüber hinaus können wir jedoch weiterhin jeden Touchpoint aufdecken, der nach der Erstellung der Opportunity aufgetreten ist und bis zu dem Zeitpunkt, an dem die Opportunity geschlossen ist. Dies ermöglicht es uns nicht nur, einen Multi-Touch-Ansatz zu verfolgen, um zu verstehen, woher eine Chance kam, sondern auch, was sie zur Schließung und letztendlich zur Darstellung geschlossener Erlöse beeinflusste. Dies gibt Einblicke in verschiedene Fragen, wie z. B. &quot;Welche Auswirkungen hat das Marketing auf die Beeinflussung von Deals zum Schließen?&quot;, &quot;Welches Marketing treibt den geschlossenen Umsatz voran?&quot; und schließlich &quot;Welche meiner Marketing-Maßnahmen erzielen den höchsten ROI?&quot;

## EMPFOHLENE BERICHTE MIT DEM BUYER ATTRIBUTION TOUCHPOINT (BAT) {#recommended-reports-using-the-buyer-attribution-touchpoint}

**4,1 | Neue Möglichkeiten nach Marketing-Kanal**

Die Zusammenfassung der Touchpoint-Daten der Käuferzuordnung Ihrer Chancen nach dem Feld &quot;Marketing-Kanal&quot;ist die Ansicht auf höchster Ebene, die angibt, welche Kanäle/Taktiken neue Möglichkeiten zur Erstellung beeinflussen. Wenn Sie diesen Bericht auf einen Datumstyp (&quot;Erstellungsdatum der Chance&quot;) umstellen, wird sichergestellt, dass wir den Bericht auch auf Grundlage des Zeitpunkts zusammenfassen, zu dem die Möglichkeit in Ihrem CRM-System tatsächlich erstellt wurde. Die Touchpoints stammen möglicherweise aus einer früheren Zeit, beziehen sich jedoch weiterhin auf die im definierten Datumsbereich erstellten Möglichkeiten und erhalten daher Zuordnungsgutschriften, da sie erkannt werden, dass sie die Chance beeinflussen.

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Was <i>Marketing-Kanäle</i> beeinflussen Chancen zur Schöpfung?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Touchpoints der Käuferzuordnung mit Chancen (CRM)<br> 
   Metrik: Chancen ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>
   <li>Opportunity Stage* <i>(optional, je nachdem, welche speziellen Möglichkeiten Sie auf den Bericht beschränken möchten. Sie können nur BVT-Berichte erstellen, die noch mit "Open"-Chancen verknüpft sind (z. B.)</i></li>
   <li>Opportunity type (es ist üblich, nach bestimmten Opportunities zu filtern, d. h. "New Business"anstatt <i>all</i> Möglichkeiten)</li><br>
   *Ein Segmentfilter für "Opportunity Type"sollte in [!DNL Marketo Measure] Discover</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>Erstellungsdatum (CRM)/Erstellungsdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td><strong>W-förmig</strong><br>
   SUM die Felder "W-förmig"in Ihren CRM-Berichten (Anzahl - W-förmig, Umsatz - W-förmig)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Beginnen Sie für jeden Berichtstyp &quot;Touchpoints der Käuferzuordnung mit Chancen&quot;mit der Anpassung des vordefinierten Berichts mit dem Titel &quot;[!DNL Marketo Measure] 101 | Möglichkeiten nach Kanal&quot;. Dieser Bericht ist standardmäßig verfügbar und ist eine großartige Sandbox, die wie in der obigen Tabelle beschrieben vorkonfiguriert ist. Er kann schnell für spezifischere Berichtsanforderungen angepasst werden. (Der Bericht verwendet standardmäßig ein Modell für vollständigen Pfad, sodass Sie den Bericht so anpassen können, dass jedes andere Attributionsmodell, in diesem Fall das W-förmige Modell, einbezogen wird.)

>[!TIP]
>
>Der oben beschriebene Bericht würde auch verwendet, um zu verstehen, wie viel Währung auch zugeschrieben werden sollte. Bei der Berichterstellung auf Opportunity-Ebene mithilfe von BVTs werden zwei Schlüsselmetriken zusammengefasst: die Währung (der Umfang der Chancen) und der Datensatz Opportunity selbst. Im obigen Beispiel messen wir eher offene Chancen und neue Pipeline-Umsätze.

>[!TIP]
>
>Erhalten Sie noch detailliertere Einblicke, indem Sie den Bericht mit anderen verfügbaren Feldern aus dem Touchpoint-Objekt &quot;Käuferzuordnung&quot;zusammenfassen. Dies geschieht auf die gleiche Weise wie auf Lead-Ebene mit Käufer Touchpoints (1.2). Fügen Sie dazu zusätzliche Gruppierungen (CRM) oder Dimensionen (Discover) hinzu. Je nach Kanal (der möglicherweise für Ihre Rolle repräsentativ ist) können über die Kampagnenebene hinaus weitere Details angezeigt werden, über die Sie weitere Einblicke erhalten möchten. Gehen wir wie folgt in &quot;Paid Search&quot;:

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Welcher <i>Schlüsselwörter</i> aus meinen gebührenpflichtigen Suchanzeigen den meisten Pipeline-Umsatz generieren?
</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Touchpoints der Käuferzuordnung mit Chancen (CRM)<br> 
   Metrik: Chancen ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>
   <li>Marketing-Kanal = Gebührenpflichtige Suche</li>
   <li>Opportunity Stage* <i>(optional, je nachdem, welche speziellen Möglichkeiten Sie auf den Bericht beschränken möchten. Dieses Beispiel basiert auf dem Pipeline-Umsatz , der in [!DNL Marketo Measure] nach "Offene"Möglichkeiten, die potenzielle Einnahmen/offene Pipeline darstellen)</i></li>
   <li>Opportunity type (es ist üblich, nach bestimmten Opportunities zu filtern, d. h. "New Business"anstatt <i>all</i> Möglichkeiten)</li><br>
   *Ein Segmentfilter für "Opportunity Type"sollte in [!DNL Marketo Measure] Discover</td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>Opportunity-Erstellungsdatum</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Schlüsselworttext (CRM)<br> 
   Suchbegriff (Discover)</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td><strong>W-förmig</strong><br>
   SUM die Felder "W-förmig"in Ihren CRM-Berichten (Anzahl - W-förmig, Umsatz - W-förmig)</td> 
  </tr>
 </tbody>
</table>

**4,2 | Angebote nach Marketing-Kanal**

Dieser Bericht wäre im Wesentlichen mit dem ersten Buyer Attribution Touchpoint-Beispiel (4.1) identisch, mit der Ausnahme, dass sich die Metrik jetzt von &quot;Offene Chancen&quot;zu &quot;Geschlossene Angebote&quot;geändert hat. Die Metrik sollte immer angeben, welches Attributionsmodell verwendet werden soll. In Anbetracht der Tatsache, dass wir uns jetzt mit geschlossenen &quot;Won Deals&quot;und den zugehörigen BVTs beschäftigen, sollten wir ein Modell verwenden, das die Journey des gesamten Käufers (Deal) darstellt. Dadurch wird sichergestellt, dass jeder Marketing-Touch-Track während der Journey des Käufers eine Zuordnungsgutschrift erhält:

<table> 
 <tbody>
  <tr>
   <td>Frage</td> 
   <td>Was <i>Marketing-Kanäle</i> beeinflussen Deals zu schließen?</td> 
  </tr>
  <tr>
   <td>Berichtstyp</td> 
   <td>Touchpoints der Käuferzuordnung mit Chancen (CRM)<br> 
   Metrik: Angebote ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filter</td> 
   <td>
   <li>Opportunity Stage (<i>Nur geschlossene Chancen sollten im Bericht aufgeführt werden</i>) ODER</li>
   <li>Opportunity Won = true</li>
   <li>Opportunity type (es ist üblich, nach bestimmten Opportunities zu filtern, d. h. "New Business"im Gegensatz zu allen Opportunities)<br>
   </td> 
  </tr>
  <tr>
   <td>Datumsfeld/Datumstyp</td> 
   <td>Opportunity Closed Date</td> 
  </tr>
  <tr>
   <td>Datumsbereich</td> 
   <td><i>gewünschten Datumsbereich auswählen</i></td> 
  </tr>
  <tr>
   <td>Gruppe/Dimension</td> 
   <td>Marketing-Kanal</td> 
  </tr>
  <tr>
   <td>Optimale Modelle</td> 
   <td><strong>Vollständiger Pfad</strong><br>
   Setzen Sie die Felder "Vollständiger Pfad"in Ihre CRM-Berichte ein (Zählung - Vollständiger Pfad, Umsatz - Vollständiger Pfad)</td> 
  </tr>
 </tbody>
</table>

**ERINNERUNG**: Es ist wichtig, dass Sie sich daran erinnern, nach den spezifischen Möglichkeiten zu filtern, die Sie in BAT-basierte Berichte einbeziehen möchten, insbesondere wenn es um &quot;Offene Chancen und Pipeline-Umsatz&quot;vs. &quot;Angebote und geschlossener Umsatz&quot;geht. Dies geschieht normalerweise über einen Filter &quot;Opportunity Stage&quot;(Opportunity Won = true/false).

**5. ROI ([!DNL Marketo Measure] Nur Discover)**

Die [!DNL Marketo Measure] Discover-Dashboards bieten einen allgemeinen Überblick über Ihre Marketing-Leistung mithilfe von [!DNL Marketo Measure] Attributionsdaten. Diese aggregierten Dashboards bieten wichtige Marketing-Ausgaben und ROI-Daten, die in Ihren CRM-Berichten nicht verfügbar sind. Diese vordefinierte Umgebung ermöglicht es Ihnen, Ihre Marketing-Performance in Abstimmung mit Ihren ROI-Daten anzuzeigen, damit Sie umsetzbare Entscheidungen in Bezug auf Ihr Marketing treffen können.

>[!TIP]
>
>Wann immer Sie Fragen zu ROI, Ausgaben oder Kosten haben, [!DNL Marketo Measure] Discover wird der beste Ort für die Berichterstellung sein!

Die [!DNL Marketo Measure] Discover-Dashboards bestehen aus Touchpoints-Daten der Käuferzuordnung und den Touchpoints der Käuferzuordnung sowie aus wichtigen CRM-Daten. Der Hauptunterschied zwischen CRM-Reporting und Reporting in [!DNL Marketo Measure] Discover stellt fest, dass die Touchpoint-Daten in Discover häufiger &quot;aggregiert&quot;und nach Dimension (Marketing-Kanal, Kampagne usw.) zusammengefasst werden. im Gegensatz zu einzelnen Touchpoint-Datensätzen, die dann zusammengefasst werden können. [!DNL Marketo Measure] Discover wird verwendet, um auf hoher Ebene zu verstehen, welche Ihrer Bemühungen den größten Einfluss auf Leads, Opps, Deals haben und wie viel Umsatz ihnen zugeschrieben werden sollte. Sobald wir den anhand der verschiedenen Attributionsmodelle berechneten Umsatz ermittelt haben (für die Zuweisung geschlossener Gewinne/Buchungen wird der vollständige Pfad empfohlen), können wir ihn anhand der in derselben Dimension (Marketing-Kanal, Subkanal oder Kampagne) getätigten Ausgaben messen. Dies gibt uns dann die **ROI**.

>[!TIP]
>
>Eines der wichtigsten Elemente bei der Berichterstellung in Discover ist, welcher Datentyp gefiltert werden soll. Der Datumstyp bestimmt, welcher Datensatz [!DNL Marketo Measure] verwendet in den verschiedenen Kacheln.

* **Touchpoint-Datum**: Zeigt die zugehörigen Daten an, die im angegebenen Zeitrahmen ein &quot;Touchpoint-Datum&quot;hatten.
* **Erstellungsdatum**: Zeigt die zugehörigen Daten an, die im angegebenen Zeitrahmen ein &quot;Erstellungsdatum&quot;hatten.
* **Geschlossenes Datum**: Zeigt die zugehörigen Daten an, die im angegebenen Zeitrahmen über ein &quot;Datum schließen&quot;verfügten

Bei der Berichterstellung zum ROI in [!DNL Marketo Measure] In Discover wird empfohlen, einen Datumstyp = &quot;Touchpoint-Datum&quot;zu verwenden. Um die Rendite jedes investierten Dollars zu bestimmen, müssen wir sicherstellen, dass die Einnahmen dem Zeitpunkt zugeordnet werden, an dem die Investition getätigt wurde. &quot;Datumstyp&quot;= &quot;Touchpoint-Datum&quot; stellt sicher, dass die Berichte auf diese Weise strukturiert sind, anders als bei der Erstellung (Erstellungsdatum) oder der Schließung (Geschlossenes Datum) der Option. Sehen wir uns Folgendes genauer an:

Die unten hervorgehobenen Filter sind für einen ROI-orientierten Bericht in [!DNL Marketo Measure] (höchstwahrscheinlich werden Sie diese Filter in den Pinnwänden &quot;Übersicht&quot;, &quot;CMO&quot;oder &quot;ROI&quot;festlegen):

**5,1 | ROI in der &quot;Übersichtskarte&quot;**

![](assets/bizible-reporting-guide-4.png)

Der Bereich &quot;Datum&quot;legt nicht nur die Kohorte der Touchpoints (nach Touchpoint-Datum) fest, die eine Attribution erhalten, sondern definiert auch den Bereich, den die Kachel &quot;Ausgaben&quot;oder die Spalten darstellen.
[!DNL Marketo Measure] Betrachtet einfach den Datumsbereich, um festzustellen, wie viel entweder insgesamt oder auf Marketing-, Subkanal- oder Kampagnenebene ausgegeben wurde Siehe unten:

![](assets/bizible-reporting-guide-5.png)

Der obige Screenshot zeigt die Marketing-Ausgabedaten der letzten 3 vollständigen Monate. In diesem Beispiel wurden 12.970 USD für alle Kanäle ausgegeben. Diese Zahl setzt sich aus den Marketing-Ausgabedaten zusammen. [!DNL Marketo Measure] hat sich aus Integrationen mit einem Ihrer verbundenen Anzeigen-Konten (Google AdWords, Bing Ads, Facebook Ads, LinkedIn, DoubleClick) und allen zusätzlichen Marketing-Ausgaben ergeben, die innerhalb Ihres Kontos hochgeladen oder automatisch aus Campaign-Datensätzen in Ihrem CRM abgerufen wurden. Das Beispiel zeigt auch, wie viel geschlossene Gewinner &quot;Umsatz&quot;auch Touchpoints zugeordnet werden können, die im selben Datumsbereich aufgetreten sind (grüne Kästchen). So wird der ROI berechnet: Umsatz, der Touchpoints zugeordnet wird, die aus Investitionen im selben Datumsbereich stammen:

![](assets/bizible-reporting-guide-6.png)

**ERINNERUNG**: [!DNL Marketo Measure] definiert &quot;Umsatz&quot;als &quot;Geschlossener Umsatz&quot;oder &quot;Buchungen&quot;und definiert &quot;Pipeline-Umsatz&quot;als _offene/potenzielle Einnahmen aus offenen Chancen_.

Ein weiterer wichtiger Schritt aus dem obigen ROI-Bericht ist der &quot;Pipeline-Umsatz&quot;, der im roten Feld dargestellt wird. Das bedeutet, dass wir von den 12.970 USD, die wir in den letzten drei kompletten Monaten investiert haben, derzeit 705.199 USD des geschlossenen &quot;Umsatzes&quot;zuordnen, aber wir auch 6.905.532 USD des offenen, potenziellen Umsatzes (&#39;Pipeline Revenue&#39;) auf Touchpoints zurechnen, die aus derselben Investition erstellt wurden! Was wir erwarten würden, ist ein Teil des &quot;Pipeline-Umsatzes&quot;im Laufe der Zeit, der die &quot;Umsatz&quot;-Zahl nährt, und daher würde sich die ROI-Zahl im Laufe der Zeit erhöhen. Die &#39;Spend&#39;-Zahl ist festgelegt, da wir nicht in der Zeit zurückgehen können, um in den letzten drei vollständigen Monaten mehr auszugeben. Dies ist die Wichtigkeit der Verwendung eines &quot;Datumstyps&quot;vom &quot;Touchpoint-Datum&quot;in jeder ROI-Berichterstellung: Er definiert den Betrag (**I**) und stellt sicher, dass die Menge (**R**)Der zugeordnete Umsatz wird denselben Touchpoints zugeordnet, die aus der Investition bezogen wurden (für jeden ausgegebenen Dollar, wie viel wurde getätigt?).

>[!TIP]
>
>Filtern Sie nach Marketing-Kanälen, Subkanälen und/oder Kampagnen, von denen Sie wissen, dass die Marketing-Ausgabedaten vollständig und korrekt sind. Das obige Beispiel gilt für alle Marketing-Kanäle. Wenn jedoch bei einigen Kanälen nicht die zugehörigen Marketing-Ausgabedaten hochgeladen wurden, kann das ROI-Reporting ungenau sein. Im folgenden Beispiel sehen Sie dieses Mal im &quot;ROI&quot;-Forum, das sich auf die Kampagnen im Marketingkanal von &quot;Paid Search&quot; konzentriert, einem Kanal mit sehr detaillierten Marketing-Ausgabedaten über die Integrationen.

![](assets/bizible-reporting-guide-7.png)
