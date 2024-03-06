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

Die Marketo-Personenintegration ermöglicht [!DNL Marketo Measure] , um mit dem Herunterladen von Personen aus Marketo zu beginnen und ihre verfolgten Sitzungen mit der jeweiligen Person zu verknüpfen und Touchpoints ihrer Interaktion zuzuordnen. Historisch gesehen [!DNL Marketo Measure] konnte einer Person nur Touchpoints aus dem CRM-System zuordnen. So können Marketingexperten ihre Marketing-Bemühungen schneller messen, anstatt auf eine Phase oder einen Trigger zu warten, um sie mit dem CRM zu synchronisieren.

## Anforderungen {#requirements}

* Marketo-Produktionsinstanz
* Produktion [!DNL Salesforce] oder [!DNL Microsoft Dynamics] instance
* Entrichtete [!DNL Marketo Measure] Abonnement
* SOLR aktiviert (Kontakt [Marketo-Support](https://nation.marketo.com/t5/Support/ct-p/Support) aktivieren).

## Funktionsweise {#how-it-works}

Als aktueller Kunde [!DNL Marketo Measure] lädt bereits Personen aus Ihrem CRM herunter. Der Standardprozess besteht darin, dass [!DNL Marketo Measure] lädt die Personen herunter und ordnet die E-Mail-Adresse einer Websitzung zu, die wir über bizible.js verfolgt haben.

Mit der Einführung des Herunterladens von Marketo-Mitarbeitern [!DNL Marketo Measure] ist nun in der Lage, Web-Sitzungen einem größeren Pool von Einzelanwendern zuzuordnen, also solchen, die nicht mit dem CRM synchronisiert wurden. Dies wird häufig durch interne Prozesse verursacht, die warten, bis die Benutzer einen bestimmten Status erreichen, bevor sie an das CRM-System gesendet werden.

Wann [!DNL Marketo Measure] die Marketo-Person erfolgreich einer Web-Sitzung zuordnet, generiert unsere Verarbeitung alle relevanten Touchpoints dafür, die letztendlich in [!DNL Marketo Measure Discover]. Wenn diese Marketo-Person an das CRM-System gesendet wird, [!DNL Marketo Measure] behandelt das doppelte Szenario. Wir erstellen den Touchpoint für die CRM-Person neu und markieren den anfänglichen Satz als &quot;Duplikat&quot;.

Damit wir diese Duplikate erkennen können, vergewissern Sie sich, dass Ihr [!DNL Marketo-Salesforce] oder [!DNL Marketo-Dynamics] sync füllt die Lead- und Kontaktinformationen auf der Marketo-Person. Wenn die ID ordnungsgemäß synchronisiert wird, sollte die CRM-ID im Datensatz &quot;Person&quot;angezeigt werden, wie in diesem Beispiel:

![](assets/5a.png)

![](assets/5b.png)

Kunden haben die Möglichkeit, die gesamte Gruppe von Marketo-Personen und CRM-Personen innerhalb von [!DNL Marketo Measure] Entdecken Sie. Wenn Sie nur über CRM-Personen berichten möchten, empfehlen wir die Erstellung eines Segments, um diese zu filtern.

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

Beim Reporting zu Leads (Personen) in [!DNL Marketo Measure Discover]angezeigt, sehen Sie die Gesamtzahl Ihrer Marketo- und CRM-Leads. Um nur Berichte zu Marketo-Benutzern oder nur CRM-Leads zu erstellen, sollten Sie eine Segmentkategorie für Ihre Quelle erstellen und dann Segmentregeln für Marketo und CRM mithilfe des Felds &quot;Quellsystem&quot;erstellen, um die Regel zu definieren. Sobald Ihre Segmente erstellt wurden, wird die Kategorie Quelle angezeigt, die für die Filterung Ihrer [!DNL Marketo Measure Discover] Dashboards.

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

*Es gibt ein bekanntes Verhaltensproblem, bei dem Felder aus der Entität &quot;Marketo Company&quot;den Wert &quot;updatedAt&quot;der Person nicht beeinflussen. Wenn also relevante Felder wie Website oder Firma aktualisiert werden, [!DNL Marketo Measure] erkennt nicht, dass diese Werte geändert werden, da der Wert für &quot;updatedAt&quot;date/time nicht aktualisiert wird. Dies wirkt sich auf die ABM-Funktion aus, bei der wir keine neuen Daten zur Lösung des Kontos für den Lead hätten. Es gibt derzeit keine Lösung, aber es gibt Pläne, dies in Zukunft zu beheben.

## FAQs {#faq}

**Warum unterscheiden sich meine Lead-Zählungen zwischen meinem CRM-System und [!DNL Marketo Measure Discover]?**

Da diese Integration es uns ermöglicht, Touchpoints für Leads zu erstellen, die wir direkt aus Marketo importiert haben, kann es Leads geben, die nicht mit dem CRM synchronisiert wurden. Daher könnte die Anzahl innerhalb von Discover höher sein als im CRM, da Touchpoints nur für die CRM-Leads gepusht werden.

**Wie werden meine Daten dadurch ersetzt?**

Durch diese Integration werden die Datensätze tatsächlich in Ihrer aktuellen [!DNL Marketo Measure] -Instanz, sodass nichts ersetzt wird. Was wir von Ihren aktuellen CRM-Leads erwarten würden, ist, dass wir beim Herunterladen der zweijährigen Marketo Leads diesen Lead-Datensatz einfach aktualisieren würden, um zu zeigen, dass es auch eine Übereinstimmung mit einem Marketo Lead gab. Das alles geschieht im Backend und die Touchpoints werden voraussichtlich unverändert bleiben. Wir würden auch erwarten, dass wir mehr Touchpoints aufgrund der förderfähigen Marketo Leads sehen. Wenn wir Websitzungen finden können, die mit diesen Marketo-Benutzern übereinstimmen, werden die Touchpoints in [!DNL Marketo Measure].

**Kann ich nur meine Mitarbeiter von Marketo herunterladen und die CRM-Verbindung abbrechen?**

Zu diesem Zeitpunkt nein. Wir werden diese Option in der Zukunft haben, aber wir müssen andere Phasen dieser Marketo-Integration aufbauen, damit wir die Programme, Möglichkeiten und Angebote von Marketo mit [!DNL Marketo Measure].

**Importieren Sie ALLE meiner Marketo-Leute?**

Im Moment importieren wir frühestens ab dem 1.1.2018 Daten, sodass wir mindestens 2 Jahre lang Daten haben. Das ist dasselbe Verhalten, das wir auch bei CRM-Downloads durchsetzen. Sobald die Marketo-Verbindung hergestellt ist, implementieren wir ein verbessertes Verhalten zum Herunterladen eines rollierenden 2-Jahres-Fensters.

Wir filtern auch nicht nach Personentypen, sodass alle Personen innerhalb des zweijährigen Fensters importiert werden und Touchpoints erhalten.

**Was ist SOLR und warum muss ich es aktivieren lassen, damit es diese Funktion nutzen kann?**

Die Aktivierung von SOLR für Ihre Marketo-Instanz ist ein trivialer Schritt, der in Marketo Hardware-Speicherplatz eröffnet, sodass Ihr Abonnement die [!DNL Marketo Measure] Integration. Ohne Aktivierung von SOLR haben wir keinen Zugriff auf bestimmte Anrufe, die es uns sonst ermöglichen würden, die entsprechenden Personen von Ihrer Marketo-Instanz herunterzuladen.
