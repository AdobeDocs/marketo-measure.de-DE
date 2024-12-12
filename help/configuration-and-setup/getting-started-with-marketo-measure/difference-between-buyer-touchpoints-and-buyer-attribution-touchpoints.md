---
unique-page-id: 18874646
description: Unterschiede zwischen Buyer Touchpoints und Buyer Attribution Touchpoints – [!DNL Marketo Measure]
title: Unterschiede zwischen Buyer Touchpoints und Buyer Attribution Touchpoints
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
feature: Touchpoints
source-git-commit: bdc32fdfe24d57fd7770654f1238896c7b59acf6
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 100%

---

# Unterschiede zwischen Buyer Touchpoints und Buyer Attribution Touchpoints {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

Erfahren Sie, was einen Buyer Touchpoint (BT) und einen Buyer Attribution Touchpoint (BAT) definiert, welche Unterschiede zwischen den beiden bestehen, und finden Sie Antworten auf häufig gestellte Fragen.

Der Hauptunterschied zwischen Buyer Touchpoints und Buyer Attribution Touchpoints besteht in ihrer Beziehung zu [!DNL Salesforce]-Objekten. BTs beziehen sich auf die Lead-, Kontakt- und Fallobjekte, jedoch nicht auf das Opportunity-Objekt. Das bedeutet, dass mit Buyer Touchpoints nie ein Umsatz verbunden ist.

Während das Objekt „Buyer Attribution Touchpoint“ mit den Kontakt-, Konten- und Opportunity-Objekten verbunden ist, jedoch nicht mit dem Lead-Objekt, sind die Buyer Attribution Touchpoints nicht an Leads gebunden. Im BAT-Objekt werden die Umsätze angezeigt, die mit bestimmten Marketing-Interaktionen verknüpft sind.

Unterschied zwischen BT und BAT:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>Buyer Touchpoint (BT)</td> 
   <td>Buyer Attribution Touchpoint (BAT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>Bezieht sich auf das Lead-, Kontakt- und Fallobjekt</li> 
     <li>Bezieht sich nicht auf das Opportunity-Objekt</li> 
     <li>Umsatz ist nicht mit einem Buyer Touchpoint verknüpft</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>Bezieht sich auf das Kontakt-, Konto- und Opportunity-Objekt</li> 
     <li>Bezieht sich nicht auf das Lead-Objekt</li> 
     <li>Da ein Buyer Attribution Touchpoint mit einer Opportunity verknüpft ist, ist allen BAT-Merkblättern Umsatz zugeordnet</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## FAQs {#faq}

**Wann wird ein Buyer Touchpoint zu einem Buyer Attribution Touchpoint ?**

Ein BT wird zu einem BAT, sobald dieser BT mit einem Kontakt verknüpft ist, der eine damit verbundene Opportunity hat. Eine wichtige Erkenntnis ist, dass eine bestimmte Marketing-Interaktion gleichzeitig ein BT und ein BAT sein kann.

**Kann ein Buyer Touchpoint eine Touchpoint-Position der Opportunity Creation (OC) haben?**

Ein Buyer Touchpoint hat als Touchpoint-Position entweder Erstkontakt (FT), Lead-Erstellung (LC) oder Formularübermittlung (Zwischen-Touchpoints). Da BTs nicht mit Opportunitys verknüpft sind, kann ein BT nicht über die Touchpoint-Position „Opportunity Creation“ oder „Closed“ verfügen.

**Wie werden Buyer-Touchpoint-Daten genutzt?**

In der Regel nutzen Kundinnen und Kunden Buyer-Touchpoint-Daten, um die „Spitze des Trichters“ und die „Mitte des Trichters“ zu verstehen. Das bedeutet, dass [!DNL Marketo Measure]-Benutzende wissen, wer Formulare sendet, wer ihre Website ansieht, welche Blog-Beiträge gut funktionieren, welche AdWords-Anzeigen zu Konversionen führen usw. Die Buyer Touchpoint-Daten eignen sich hervorragend zum Verständnis der Interaktion Ihrer Leads und Kontakte.

**Wie sieht ein Buyer Touchpoint in Salesforce aus?**

Hier ist ein Screenshot eines BT in [!DNL Salesforce]:

![](assets/buyer-touchpoints-and-buyer-attribution-touchpoints-1.png){width="600" zoomable="yes"}

**Wie sieht ein Buyer Attribution Touchpoint in Salesforce aus?**

Hier ist ein Screenshot eines BAT in [!DNL Salesforce]:

![](assets/buyer-touchpoints-and-buyer-attribution-touchpoints-2.png){width="600" zoomable="yes"}
