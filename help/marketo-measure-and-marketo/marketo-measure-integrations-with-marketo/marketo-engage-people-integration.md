---
unique-page-id: 37356395
description: "[!DNL Marketo Engage] Personenintegration - [!DNL Marketo Measure]"
title: "[!DNL Marketo Engage] Personenintegration"
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
feature: Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 2%

---

# [!DNL Marketo Engage] Personenintegration {#marketo-engage-people-integration}

Die Marketo-Personenintegration ermöglicht es [!DNL Marketo Measure], mit dem Herunterladen von Personen aus Marketo zu beginnen, ihre verfolgten Sitzungen mit der jeweiligen Person zu verknüpfen und Touchpoints ihrer Interaktion zuzuordnen. In der Vergangenheit konnte [!DNL Marketo Measure] einer Person aus dem CRM nur Touchpoints zuordnen. So können Marketingexperten ihre Marketing-Maßnahmen schneller messen, anstatt auf eine Phase oder einen Trigger zu warten, um sie mit dem CRM zu synchronisieren.

## Anforderungen {#requirements}

* Marketo-Produktionsinstanz
* Produktions- [!DNL Salesforce] oder [!DNL Microsoft Dynamics] -Instanz
* Beliebiges bezahltes [!DNL Marketo Measure]-Abonnement
* SOLR aktiviert (wenden Sie sich an den [Marketo-Support](https://nation.marketo.com/t5/Support/ct-p/Support) , damit dieser aktiviert wird)

## Funktionsweise {#how-it-works}

Als aktueller Kunde lädt [!DNL Marketo Measure] bereits Personen aus Ihrem CRM herunter. Der Standardprozess besteht darin, dass [!DNL Marketo Measure] die Personen herunterlädt und die E-Mail-Adresse einer Websitzung zuordnet, die wir über bizible.js verfolgt haben.

Mit der Einführung des Herunterladens von Marketo-Benutzern ist [!DNL Marketo Measure] jetzt in der Lage, Websitzungen einem größeren Individuenpool zuzuordnen, d. h. solchen, die nicht mit dem CRM synchronisiert wurden. Dies wird häufig durch interne Prozesse verursacht, die warten, bis die Benutzer einen bestimmten Status erreichen, bevor sie an das CRM-System gesendet werden.

Wenn [!DNL Marketo Measure] die Marketo-Person erfolgreich einer Websitzung zuordnet, generiert unsere Verarbeitung alle relevanten Touchpoints dafür, die letztendlich in [!DNL Marketo Measure Discover] gemeldet werden können. Wenn diese Marketo-Person an das CRM-System gesendet wird, verarbeitet [!DNL Marketo Measure] das doppelte Szenario. Wir erstellen den Touchpoint für die CRM-Person neu und markieren den ursprünglichen Satz als &quot;Duplikat&quot;.

Damit wir diese Duplikate erkennen können, stellen Sie sicher, dass Ihre [!DNL Marketo-Salesforce] - oder [!DNL Marketo-Dynamics] -Synchronisation die Lead- und Kontakt-IDs auf der Marketo-Person ausfüllt. Wenn die ID ordnungsgemäß synchronisiert wird, sollte die CRM-ID im Datensatz &quot;Person&quot;angezeigt werden, wie in diesem Beispiel:

![](assets/5a.png)

![](assets/5b.png)

Kunden haben die Möglichkeit, die gesamte Gruppe von Marketo-Personen und CRM-Personen in [!DNL Marketo Measure] Discover zu melden. Wenn Sie nur über CRM-Personen berichten möchten, empfehlen wir die Erstellung eines Segments, um diese zu filtern.

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

Bei der Berichterstellung über Leads (Personen) in [!DNL Marketo Measure Discover] sehen Sie die Gesamtzahl Ihrer Marketo- und CRM-Leads. Um nur Berichte zu Marketo-Benutzern oder nur CRM-Leads zu erstellen, sollten Sie eine Segmentkategorie für Ihre Quelle erstellen und dann Segmentregeln für Marketo und CRM mithilfe des Felds &quot;Source-System&quot;erstellen, um die Regel zu definieren. Nachdem Sie Ihre Segmente erstellt haben, wird Ihnen die Source-Kategorie angezeigt, die über Ihre [!DNL Marketo Measure Discover]-Dashboards gefiltert werden kann.

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
   <th><p><strong>biz_lead</strong></p></th> 
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
   <td><p>website</p></td> 
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

*Es gibt ein bekanntes Verhaltensproblem, bei dem Felder aus der Entität Marketo Company den Wert updatedAt der Person nicht beeinflussen. Wenn also relevante Felder wie Website oder Firma aktualisiert werden, weiß [!DNL Marketo Measure] nicht, dass diese Werte geändert werden, da der Wert updateAt date/time nicht aktualisiert wird. Dies wirkt sich auf die ABM-Funktion aus, bei der wir keine neuen Daten zur Lösung des Kontos für den Lead hätten. Es gibt derzeit keine Lösung, aber es gibt Pläne, dies in Zukunft zu beheben.

## FAQs {#faq}

**Warum unterscheiden sich meine Lead-Zahlen zwischen meinem CRM-System und [!DNL Marketo Measure Discover]?**

Da diese Integration es uns ermöglicht, Touchpoints für Leads zu erstellen, die wir direkt aus Marketo importiert haben, kann es Leads geben, die nicht mit dem CRM synchronisiert wurden. Daher könnte die Anzahl innerhalb von Discover höher sein als im CRM, da Touchpoints nur für die CRM-Leads gepusht werden.

**Wie ersetzt dies meine Daten?**

Durch diese Integration werden die Datensätze in Ihrer aktuellen [!DNL Marketo Measure]-Instanz zusammengeführt, sodass nichts ersetzt wird. Was wir von Ihren aktuellen CRM-Leads erwarten würden, ist, dass wir beim Herunterladen der zweijährigen Marketo Leads diesen Lead-Datensatz einfach aktualisieren würden, um zu zeigen, dass es auch eine Übereinstimmung mit einem Marketo Lead gab. Das alles geschieht im Backend und die Touchpoints werden voraussichtlich unverändert bleiben. Wir würden auch erwarten, dass wir mehr Touchpoints aufgrund der förderfähigen Marketo Leads sehen. Wenn wir Websitzungen finden können, die mit diesen Marketo-Personen übereinstimmen, werden die Touchpoints in [!DNL Marketo Measure] gezählt.

**Kann ich nur meine Personen von Marketo herunterladen und die CRM-Verbindung abbrechen?**

Zu diesem Zeitpunkt nein. Wir werden diese Option in der Zukunft haben, aber wir müssen andere Phasen dieser Marketo-Integration aufbauen, damit wir die Programme, Möglichkeiten und Angebote von Marketo mit [!DNL Marketo Measure] verbinden können.

**Importieren Sie ALLE meiner Marketo-Personen?**

Im Moment importieren wir frühestens ab dem 1.1.2018 Daten, sodass wir mindestens 2 Jahre lang Daten haben. Das ist dasselbe Verhalten, das wir auch bei CRM-Downloads durchsetzen. Sobald die Marketo-Verbindung hergestellt ist, implementieren wir ein verbessertes Verhalten zum Herunterladen eines rollierenden 2-Jahres-Fensters.

Wir filtern auch nicht nach Personentypen, sodass alle Personen innerhalb des zweijährigen Fensters importiert werden und Touchpoints erhalten.

**Was ist SOLR und warum muss ich es aktivieren lassen, damit diese Funktion verwendet werden kann?**

Die Aktivierung von SOLR für Ihre Marketo-Instanz ist ein trivialer Schritt, der in Marketo Hardware-Speicherplatz eröffnet, sodass Ihr Abonnement die [!DNL Marketo Measure] -Integration nutzen kann. Ohne Aktivierung von SOLR haben wir keinen Zugriff auf bestimmte Anrufe, die es uns sonst ermöglichen würden, die entsprechenden Personen von Ihrer Marketo-Instanz herunterzuladen.
