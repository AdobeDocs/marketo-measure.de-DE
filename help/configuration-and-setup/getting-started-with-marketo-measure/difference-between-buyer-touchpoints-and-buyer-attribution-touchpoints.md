---
unique-page-id: 18874646
description: Unterschiede zwischen Touchpoints der Käuferzuordnung und Touchpoints der Käuferzuordnung - [!DNL Marketo Measure] - Produktdokumentation
title: Unterschiede zwischen Touchpoints der Käuferzuordnung und Touchpoints der Käuferzuordnung
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# Unterschiede zwischen Touchpoints der Käuferzuordnung und Touchpoints der Käuferzuordnung {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

Erfahren Sie, was einen Käufer-Touchpoint (BT) und einen Buyer Attribution Touchpoint (BAT) definiert, welche Unterschiede zwischen den beiden bestehen, und beantworten Sie häufig gestellte Fragen.

Der Hauptunterschied zwischen Käufer-Touchpoints und Käufer-Attribution-Touchpoints besteht in ihrer Beziehung zu [!DNL Salesforce] Objekte. BTs beziehen sich auf die Lead-, Kontakt- und Fallobjekte, jedoch nicht auf das Opportunity-Objekt. Das bedeutet, dass mit den Touchpoints des Käufers niemals Umsatz verbunden ist.

Während das Touchpoint-Objekt &quot;Käuferzuordnung&quot;mit den Kontaktobjekten, Konten und Opportunity-Objekten, jedoch nicht mit dem Lead-Objekt verknüpft ist. Das bedeutet, dass es niemals Touchpoints der Buyer Attribution geben wird, die mit Leads verknüpft sind. Im BAT-Objekt werden die Umsätze angezeigt, die mit bestimmten Marketing-Interaktionen verknüpft sind.

Unterschied zwischen BT und BVT:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>Käufer-Touchpoint (BT)</td> 
   <td>Touchpoint der Käuferzuordnung (BVT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>Bezieht sich auf die Objekte "Lead", "Kontakt"und "Groß-/Kleinschreibung"</li> 
     <li>Bezieht sich nicht auf das Opportunity-Objekt</li> 
     <li>Umsatz ist nicht mit einem Käufer-Touchpoint verknüpft</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>Bezieht sich auf die Objekte "Kontakt", "Konto"und "Chancen"</li> 
     <li>Bezieht sich nicht auf das Lead-Objekt</li> 
     <li>Da ein Touchpoint der Käuferzuordnung mit einer Chance verknüpft ist, sind allen BVT-Merkblättern Umsatz zugeordnet</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## FAQs {#faq}

**Wann wird ein Touchpoint des Käufers zu einem Touchpoint der Käuferzuordnung?**

Ein BT wird zu einem BAT, sobald dieser BT mit einem Kontakt verknüpft ist, der eine damit verbundene Chance hat. Eine sehr wichtige Erkenntnis ist, dass eine bestimmte Marketing-Interaktion ein BT und ein BAT sein kann.

**Kann ein Käufer-Touchpoint eine Touchpoint-Position der Opportunity Creation (OC) haben?**

Ein Käufer-Touchpoint hat nur die Touchpoint-Position entweder Erstkontakt (FT), Lead-Erstellung (LC) oder Formularübermittlung (Zwischen-Touchpoints). Da BTs nicht mit Chancen verbunden sind, ist es für einen BT nicht möglich, eine Touchpoint-Position der Opportunity Creation oder Closed zu haben.

**Wie werden Touchpoint-Daten des Käufers genutzt?**

In der Regel nutzen Kunden Touchpoint-Daten von Käufern, um die &quot;Spitze des Trichters&quot;und &quot;Mitte des Trichters&quot;zu verstehen. Bedeutung [!DNL Marketo Measure] Benutzer wissen, wer Formulare sendet, wer seine Website ansieht, welche Blog-Beiträge gut funktionieren, welche AdWords-Anzeigen zu Konversionen führen usw. Die Touchpoint-Daten des Käufers eignen sich hervorragend zum Verständnis der Interaktion Ihrer Leads und Kontakte.

**Wie sieht ein Käufer-Touchpoint in Salesforce aus?**

Hier ist ein Screenshot eines BT in [!DNL Salesforce]:

![](assets/1.png)

**Wie sieht ein Touchpoint der Käuferzuordnung in Salesforce aus?**

Hier ist ein Screenshot eines BAT in [!DNL Salesforce]:

![](assets/2.png)
