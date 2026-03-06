---
description: Was ist Adobe Marketo Measure
title: Was ist Adobe Marketo Measure?
hide: true
hidefromtoc: true
source-git-commit: 7c3f586e308ba885d10f3f9b8925af93277ad2e0
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 0%

---

# Was ist Adobe Marketo Measure? {#what-is-adobe-marketo-measure}

Adobe Marketo Measure (früher bekannt als Bizible) ist eine führende Multi-Touch-Attributionsplattform.

Es konsolidiert Daten aus unterschiedlichen Datenquellen (CRM, Marketing-Automatisierung, Website usw.). Mit diesen Daten an einem Ort wird eine Zeitreihe von Ereignissen (die oben genannten Touchpoints) für jede Person erstellt, die durch ihre eindeutige E-Mail-Adresse identifiziert wird.

Diese Touchpoints sind dann entweder über Account-basierte oder Opportunity-Kontakt-Rollenbasierte Methoden mit Opportunities verknüpft, sodass wir die Attribution von Opportunitys wieder den verschiedenen Touchpoints zuordnen können, die in der Journey jeder Opportunity eine Rolle gespielt haben.

Unter Verwendung verschiedener regelbasierter und positionsbasierter Attributionsmodelle (auf die wir später viel genauer eingehen werden) wird jedem Touchpoint, der mit einer Opportunity in Verbindung steht, eine Gewichtung zugewiesen, die dann jedem Touchpoint einen Dollarwert zuweist.

Da jeder Touchpoint nach Kanal, Unterkanal, Kampagne und anderen definierten Segmenten klassifiziert wird, können Sie dann herausfinden, welche Marketing-Aktivitäten am stärksten mit Opportunitys und Gewinnen korreliert sind.

Reden wir mehr darüber, wie es das macht!
Funktionsweise von Marketo Measure
Marketo Measure lässt sich mit vielen Tools in Ihrem Technologie-Stack integrieren. Es lässt sich auch direkt in die unten aufgeführten Werbeplattformen integrieren.

●    Google Ads
●    Bing Ads
●    Facebook/Meta
●    LinkedIn

Diese Integrationen helfen dabei, den Paid-Media-Kampagnen-Traffic von diesen Plattformen aus auf die exakte Anzeigenkampagne aufzulösen, wenn das automatische Tagging aktiviert ist.

Diese Integrationen nehmen auch automatisch alle Anzeigenkampagnen und -ausgaben von diesen Plattformen direkt in die Marketo Measure-Plattform auf.

Hinweis: Diese Integrationen können keine Touchpoints innerhalb der Paid Media Walled Gardens einbringen, mit Ausnahme der LinkedIn-Lead-Gen-Formular-Integration. Das bedeutet, dass Sie keine Touchpoints für Dinge wie Kommentare, Freigaben und Likes erhalten… oder für andere Interaktionen, die ausschließlich innerhalb dieser Plattformen stattfinden.
Marketo Measure verfügt auch über ein JavaScript, das auf Ihrer Website platziert wird und Touchpoints aus Web-Interaktionen erstellt. Diese Touchpoints werden dann basierend auf Regeln, die UTM-Parameter, Kampagneninformationen, Landingpages und/oder verweisende URLs verwenden, in Kanäle und Unterkanäle kategorisiert. Weitere Informationen zu dieser Funktion finden Sie später.

Es kann auch in Ihr CRM integriert werden, um Opportunities, Konten, Kontakte, Leads, Opportunity-Kontaktrollen, Kampagnen, Kampagnenmitglieder und Aktivitäten (Aufgaben und Ereignisse) einzubringen. Durch diese Integration können Sie Regeln einrichten, mit denen Touchpoints aus der Kampagnenmitgliedschaft sowie aus für eine Person protokollierten Aktivitäten (Telefonanrufe, E-Mails, Meetings usw.) erstellt werden. Weitere Informationen zu diesen Einstellungen finden Sie später wieder.

Marketo Measure kann auch direkt in Marketo Engage integriert werden. Bei dieser Integration können Sie Regeln erstellen, die Touchpoints aus der Programmmitgliedschaft sowie dem Marketo-Aktivitätsprotokoll erstellen. Wir werden auch näher auf diese Funktion eingehen.

Mit all diesen Daten erschaffen Sie jetzt Touchpoints aus einer Fülle verschiedener Datenquellen. Und diesen Touchpoints wird dann ein Kanal und, in einigen Fällen, ein Unterkanal zugewiesen. Dadurch werden die Touchpoints nach dem Herkunftsort kategorisiert.

Touchpoints wird auch eine Position zugewiesen. Diese Position basiert darauf, wo sich der Touchpoint im Kaufprozess und beim Journey befindet. Es gibt vier Standardpositionen und Sie haben die Möglichkeit, benutzerdefinierte Positionen zu erstellen. Die Standardpositionen sind wie folgt…

●    First Touch (FT) - Der allererste Touchpoint (kann anonym sein)
●    Lead Creation (LC) : Der erste Touchpoint, an dem wir eine E-Mail-Adresse erfassen
●    Opportunity Creation (OC) - Der letzte Kontakt vor der Erstellung einer Opportunity
●    Geschlossen : Der letzte Kontakt vor dem Abschluss (geschlossen, gewonnen oder verloren) einer Opportunity.

Die Positionen bestimmen dann die Gewichtung, basierend auf den verschiedenen Attributionsmodellen.

Der Wert der Opportunities wird dann auf alle Touchpoints aufgeteilt, die sie beeinflusst haben, wie Tortenstücke, um jedem Touchpoint einen Wert zu geben.

Wenn beispielsweise ein Touchpoint eine Gewichtung von 30 % hat und mit einer Opportunity mit einem Wert von 10.000 $ in Verbindung steht, wird dieser Touchpoint mit 3.000 $ bewertet.
