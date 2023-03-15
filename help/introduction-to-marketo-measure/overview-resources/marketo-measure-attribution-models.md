---
unique-page-id: 18874568
description: Marketo Measure-Attributionsmodelle - Marketo Measure - Produktdokumentation
title: Marketo Measure-Attributionsmodelle
exl-id: d8f76f29-e7c9-4b2d-b599-e80fd93c4687
source-git-commit: 0aa263053aa8dd804b03a67ab446dc0cda3850c5
workflow-type: ht
source-wordcount: '734'
ht-degree: 100%

---

# Marketo Measure-Attributionsmodelle {#marketo-measure-attribution-models}

Marketo Measure bietet sechs Arten von Attributionsmodellen:

* First Touch
* Leaderstellung
* U-förmig
* W-förmig
* Vollständiger Pfad
* Benutzerdefiniertes Modell

Diese Modelle sind unterschiedlich komplex. First Touch und Lead Creation sind unsere einfachen Single Touch Modelle. Die restlichen vier sind unsere komplexeren Multitouch-Modelle. Die Struktur der Attributionsmodelle von Marketo Measure spiegelt die vier wichtigsten Touchpoints wider, die auf der Journey des Kunden auftreten:

* First Touch (FT)
* Lead Creation (LC)
* Opportunity Creation (OC)
* Closed-Won-Deal (CW)

![](assets/1-1.png)

In den **Single-Touch-Modellen** werden die Attributionsgutschriften nur einem Meilenstein-Touchpoint zugeordnet, weswegen der Name &quot;Single Touch&quot; lautet.
In den **Multi-Touch-Modellen** wird der Großteil der Attributionsgutschriften zwei oder mehr Meilenstein-Touchpoints zugewiesen. Das verbleibenden Guthaben wird Touchpoints zugeordnet, die zwischen den Meilensteinkontaktpunkten auftreten.

In den nächsten Abschnitten werden die einzelnen Attributionsmodelle und die Zuweisung von Attributionsgutschriften behandelt.

## Single-Touch-Modelle {#single-touch-models}

**Erstkontakt-Modell**

Das Erstkontakt-Modell konzentriert sich nur auf die allererste Interaktion, die ein Lead mit Ihrem Unternehmen hat. Dieses Modell ordnet 100 % der Attributionsgutschriften dem ersten Mal zu, dass der Lead von Ihrem Unternehmen in Kenntnis gesetzt wurde – der Erstkontakt (First Touch, FT).

Nehmen wir an, Kate besucht www.adobe.com zum ersten Mal über eine Adwords-Anzeige und sieht sich ein Whitepaper an. Der Adwords-Kanal würde 100 % des Attributionsguthabens von dieser Opportunity erhalten.

![](assets/2.png)

**Lead-Erstellungsmodell**

Das Lead-Erstellungsmodell ordnet dem LC-Touchpoint 100 % des Attributionsguthabens zu, wenn ein Interessent seine Kontaktinformationen angibt und zum Lead wird.

Austin besucht nach Kates erstem Besuch auf www.adobe.com über Adwords die Website über einen LinkedIn-Beitrag. Austin füllt ein Formular aus und wird zum Lead. In diesem Modell würde Linkedin 100 % des Attributionsguthabens erhalten.

![](assets/3.png)

## Multi-Touch-Modelle {#multi-touch-models}

Multi-Touch-Modelle werden für längere, kompliziertere Verkaufszyklen verwendet. Diese Modelle sind besonders nützlich, wenn mehrere Personen eines Kontos/Unternehmens an der Journey des Käufers beteiligt sind.

**U-förmiges Modell**

Das U-förmige Modell konzentriert sich sowohl auf die FT- als auch auf LC-Touchpoints. In diesem Modell erhalten FT- und LC-Touchpoint jeweils 50 % der Umsatzgutschrift.

Kates erster Besuch bei www.adobe.com über eine AdWords-Website würde 50 % des Attributionsguthabens erhalten. Die restlichen 50 % würden dem Linkedin-Beitrag zugeordnet, der Austin dazu brachte, ein Formular auszufüllen und zu einem Lead zu werden.

![](assets/4.png)

**W-förmiges Modell**

Drei der Meilenstein-Touchpoints sind im W-förmigen Modell enthalten. In diesem Modell werden den Touchpoints FT, LC und OC jeweils 30 % des Attributionskredits zugeordnet. Die verbleibenden 10 % werden proportional zu allen zwischengeschalteten Touchpoints zugeordnet, die zwischen den drei Meilenstein-Touchpoints auftreten.

Kate und Austin erwähnen Marketo Measure gegenüber ihrer Kollegin Hillary. Sie findet einen Inhalt durch eine Google-Suche und füllt ein Formular aus. Später erhält Austin eine E-Mail für eine Webinar-Registrierung und füllt das Registrierungsformular auf der Website aus. Kate unterhält sich mit einem Vertriebsmitarbeiter über das Marketo Measure-Produkt.

Hillary erhält eine E-Mail mit einem Link zur Preisseite und besucht die Seite. Anschließend wird eine Opportunity für ihr Konto erstellt. Der Webbesuch von Hillary auf der Preisseite erhält die Gutschrift für die Opportunity-Erstellung, da es sich um die Marketing-Interaktion handelte, die am nächsten am Erstellungsdatum der Opportunity gelegen hat. Jedem Meilenstein-Touchpoint werden 30 % des Attributionsguthabens zugewiesen, und den Zwischen-Touchpoints werden die verbleibenden 10 % zugeordnet.

![](assets/5.png)

**Vollständiges Pfadmodell**

Das vollständige Pfadmodell umfasst alle vier Meilenstein-Touchpoints. FT, LC, OC und CW erhalten jeweils 22,5 % der Einnahmegutschrift, und die verbleibenden 10 % werden zu gleichen Teilen auf die zwischengeschalteten Kontakte verteilt.

Nach der Schaffung dieser Opportunity entscheiden sich Kate, Austin und Hillary, Marketo Measure ihrer CMO, Elizabeth, vorzustellen. Elizabeth nimmt an einer Konferenz teil, auf der Marketo Measure eine Veranstaltung veranstaltet. Kate sieht einen LinkedIn-Beitrag zu einer Fallstudie und füllt ein Formular aus, um den Inhalt herunterzuladen. Elizabeth nimmt an einem Verkaufsessen teil, das von Marketo Measure veranstaltet wird. Nach dem Abendessen entscheidet sie sich für den Kauf von Marketo Measure und wird Kunde. In diesem Szenario würden dem Verkaufsessen 22,5 % der Einnahmegutschrift aus dem geschlossenen Geschäft zugeordnet. Die Touchpoints FT, LC und OC erhalten ebenfalls jeweils 22,5 % des Kredits. Den zwischengeschalteten Touchpoints werden ebenfalls die verbleibenden 10 % der Einnahmegutschrift zugewiesen.

![](assets/6.png)

**Benutzerdefiniertes Attributionsmodell**

Marketo Measure bietet außerdem ein benutzerdefiniertes Attribution-Modell, mit dem Benutzer auswählen können, welche Touchpoints oder benutzerdefinierten Stufen in ihr Modell aufgenommen werden sollen. Darüber hinaus können Benutzer den Prozentsatz der Attributionszuweisung steuern, der diesen Touchpoints und Stufen zugeordnet ist.
