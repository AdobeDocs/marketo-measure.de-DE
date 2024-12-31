---
unique-page-id: 37356395
description: Integration von [!DNL Marketo Engage] Personen - [!DNL Marketo Measure]
title: Integration von [!DNL Marketo Engage] Personen
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
feature: Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 2%

---

# Integration von [!DNL Marketo Engage] Personen {#marketo-engage-people-integration}

Mit der Marketo People -Integration können [!DNL Marketo Measure] Personen aus Marketo herunterladen und beginnen, die verfolgten Sitzungen mit den Kontakten zu verknüpfen und Touchpoints ihren Interaktionen zuzuordnen. Bisher war [!DNL Marketo Measure] nur in der Lage, Touchpoints einer Person aus dem CRM zuzuordnen. Dies hilft Marketing-Experten, ihre Marketing-Maßnahmen früher zu messen, anstatt auf eine Phase oder einen Trigger zu warten, um sie mit dem CRM zu synchronisieren.

## Anforderungen {#requirements}

* Marketo-Produktionsinstanz
* [!DNL Salesforce] oder [!DNL Microsoft Dynamics]
* Alle gebührenpflichtigen [!DNL Marketo Measure]
* SOLR aktiviert (wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/Support/ct-p/Support), um dieses zu aktivieren)

## Funktionsweise {#how-it-works}

Als aktueller Kunde lädt [!DNL Marketo Measure] bereits Personen aus Ihrem CRM herunter. Der Standardprozess besteht darin, dass [!DNL Marketo Measure] die Personen herunterlädt und die E-Mail-Adresse einer von uns über bizible.js verfolgten Web-Sitzung zuordnet.

Mit der Einführung des Herunterladens von Marketo People ist [!DNL Marketo Measure] jetzt in der Lage, Web-Sitzungen einem größeren Pool von Personen zuzuordnen, also denjenigen, die nicht mit dem CRM synchronisiert wurden. Wir sehen dies häufig aufgrund interner Prozesse, die warten, bis Personen einen bestimmten Status erreichen, bevor sie an das CRM gepusht werden.

Wenn [!DNL Marketo Measure] die Marketo-Person erfolgreich einer Web-Sitzung zuordnet, generiert unsere Verarbeitung alle relevanten Touchpoints für sie, die letztendlich in [!DNL Marketo Measure Discover] gemeldet werden. Wenn diese Marketo-Person an das CRM gepusht wird, handhabt [!DNL Marketo Measure] das Duplikatszenario und wir erstellen den Touchpoint für die CRM-Person neu und markieren den Anfangssatz als „Duplikat“.

Damit wir diese Duplikate erkennen können, stellen Sie sicher, dass Ihre [!DNL Marketo-Salesforce]- oder [!DNL Marketo-Dynamics]-Synchronisierung die Lead- und Kontakt-IDs für die Marketo-Person ausfüllt. Wenn die ID ordnungsgemäß synchronisiert wird, sollte die CRM-ID im Personendatensatz wie folgt angezeigt werden:

![](assets/5a.png)

![](assets/5b.png)

Kunden haben die Möglichkeit, alle Personen aus Marketo und CRM innerhalb von [!DNL Marketo Measure] Discover zu melden. Wenn Sie nur an Berichten zu CRM-Personen interessiert sind, empfehlen wir, ein Segment zu erstellen, um sie zu filtern.

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

Beim Reporting über Leads (Personen) in [!DNL Marketo Measure Discover] sehen Sie die Summe Ihrer Marketo- und CRM-Leads. Um nur über Marketo-Personen oder nur CRM-Leads zu berichten, sollten Sie eine Segmentkategorie für Ihre Quelle erstellen und dann Segmentregeln für Marketo und CRM erstellen, indem Sie das Feld &quot;Source-System“ verwenden, um die Regel zu definieren. Sobald Ihre Segmente erstellt wurden, wird die Source-Kategorie angezeigt, die für die Filterung über Ihre [!DNL Marketo Measure Discover]-Dashboards hinweg verfügbar ist.

![](assets/bizible-discover-1.png)

![](assets/bizible-discover-2.png)

## Feldzuordnungen {#field-mappings}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>Biz_Leads</strong></p></th> 
   <th><p><strong>Marketo</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>ID</p></td> 
  </tr> 
  <tr> 
   <td><p>MODIFIED_DATE</p></td> 
   <td><p>updatedAt<strong>*</strong></p></td> 
  </tr> 
  <tr> 
   <td><p>CREATED_DATE</p></td> 
   <td><p>createdAt</p></td> 
  </tr> 
  <tr> 
   <td><p>EMAIL</p></td> 
   <td><p>E-Mail</p></td> 
  </tr> 
  <tr> 
   <td><p>WEB_SITE</p></td> 
   <td><p>Website</p></td> 
  </tr> 
  <tr> 
   <td><p>COMPANY</p></td> 
   <td><p>Unternehmen</p></td> 
  </tr> 
  <tr> 
   <td><p>IS_CONVERTED</p></td> 
   <td><p>Nicht zutreffend</p></td> 
  </tr> 
  <tr> 
   <td><p>ACCOUNT_ID</p></td> 
   <td><p>Konto-ID (L2A)</p></td> 
  </tr> 
  <tr> 
   <td><p>BIZIBLE_STAGE</p></td> 
   <td><p>Status</p></td> 
  </tr> 
  <tr> 
   <td><p>IS_DELETED</p></td> 
   <td><p>true/false</p></td> 
  </tr> 
 </tbody> 
</table>

*Es gibt ein bekanntes Verhaltensproblem, bei dem Felder aus der Marketo-Unternehmensentität keinen Einfluss auf den updateAt-Wert der Person haben. Wenn also relevante Felder wie Website oder Unternehmen aktualisiert werden, wissen [!DNL Marketo Measure] nicht, dass diese Werte geändert werden, da der date/time-Wert von updatedAt nicht aktualisiert wird. Dies wirkt sich auf die ABM-Funktion aus, bei der wir keine neuen Daten hätten, um das Konto für den Lead aufzulösen. Es gibt derzeit keine Problemumgehung, aber es gibt Pläne, dies in Zukunft anzugehen.

## FAQs {#faq}

**Warum unterscheiden sich meine Lead-Zahlen zwischen meinem CRM und [!DNL Marketo Measure Discover]?**

Da wir mit dieser Integration Touchpoints für Leads erstellen können, die wir direkt aus Marketo importiert haben, kann es Leads geben, die nicht mit dem CRM synchronisiert wurden, sodass daher die Anzahl in Discover höher sein könnte als im CRM, da Touchpoints nur für die CRM-Leads gepusht werden.

**Wie ersetzt dies meine Daten?**

Bei dieser Integration werden die Datensätze in der aktuellen [!DNL Marketo Measure] zusammengeführt, sodass nichts ersetzt wird. Was wir von Ihren aktuellen CRM-Leads erwarten würden, ist, dass wir beim Herunterladen der Marketo-Leads im Wert von 2 Jahren einfach diesen Lead-Datensatz aktualisieren würden, um zu zeigen, dass auch ein Marketo-Lead berücksichtigt wurde. Dass alles im Backend geschieht und die Touchpoints voraussichtlich unverändert bleiben. Wir gehen auch davon aus, dass wir aufgrund der zulässigen Marketo Leads mehr Touchpoints sehen werden. Wenn wir Web-Sitzungen finden können, die auf diese Marketo-Personen abgestimmt sind, werden die Touchpoints in [!DNL Marketo Measure] gezählt.

**Kann ich nur meine Mitarbeiter von Marketo herunterladen und die CRM-Verbindung abschalten?**

Derzeit nicht. Wir werden diese Option in Zukunft haben, aber wir müssen andere Phasen dieser Marketo-Integration aufbauen, damit wir die Programme, Chancen und Angebote von Marketo mit [!DNL Marketo Measure] verbinden können.

**Importieren Sie ALLE meine Marketo-Benutzer?**

Im Moment werden wir Personen frühestens ab dem 1/1/2018 importieren, sodass wir mindestens 2 Jahre Daten haben. Dies ist das gleiche Verhalten, das wir von CRM-Downloads erzwingen. Wir werden ein verbessertes Verhalten implementieren, um ein rollierendes 2-Jahres-Fenster herunterzuladen, sobald die Marketo-Verbindung hergestellt wurde.

Wir filtern auch nicht nach Personentypen, sodass alle Personen innerhalb des Zweijahresfensters importiert werden und für Touchpoints infrage kommen.

**Was ist SOLR und warum muss ich es aktivieren lassen, um diese Funktion nutzen zu können?**

Die Aktivierung von SOLR für Ihre Marketo-Instanz ist ein trivialer Schritt, durch den in Marketo Hardware-Speicherplatz frei wird, sodass Ihr Abonnement die [!DNL Marketo Measure] Integration nutzen kann. Ohne aktiviertes SOLR haben wir keinen Zugriff auf bestimmte Aufrufe, mit denen wir sonst die entsprechenden Personen aus Ihrer Marketo-Instanz herunterladen könnten.
