---
unique-page-id: 37356132
description: "[!DNL Marketo Measure] Umsatz-Workflows für Dynamics - [!DNL Marketo Measure] - Produktdokumentation"
title: "[!DNL Marketo Measure] Umsatz-Workflows für Dynamics"
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 0%

---

# [!DNL Marketo Measure] Umsatz-Workflows für Dynamics {#marketo-measure-revenue-workflows-for-dynamics}

## Teil 1: Geschätzter Umsatz vs. tatsächlicher Umsatz {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] verweist standardmäßig auf ein standardmäßiges Umsatzfeld (tatsächlicher Umsatz), Dynamics verfügt jedoch über zwei standardmäßige Umsatzfelder: &quot;Tatsächlicher Umsatz&quot;und &quot;Geschätzter Umsatz&quot;. Damit Pipeline-Umsätze im Discover Dashboard verfügbar sind, sind ein benutzerdefiniertes Feld und ein Workflow erforderlich, um den korrekten Betrag entweder aus dem Feld Geschätzter Umsatz oder dem Feld Tatsächlicher Umsatz zu erfassen, je nachdem, ob die Gelegenheit offen oder geschlossen ist (Won).

Schritt 1: Erstellen eines benutzerdefinierten Opportunity-Felds in Dynamics

>[!NOTE]
>
>Alle Umsatzfelder von Dynamics verfügen über ein Basisfeld und ein reguläres Feld. Ignorieren Sie das Basisfeld.

Schritt 2: Erstellen Sie einen Workflow, der sowohl das in Schritt 1 erstellte benutzerdefinierte Feld für den Opportunitätsbetrag als auch die [!DNL Marketo Measure] Feld &quot;Opportunity Amount&quot;.

>[!NOTE]
>
>Wir können nicht auf die [!DNL Marketo Measure] Feld &quot;Opportunity Amount&quot;(bizible2_bizible_Opportunity_amount) in Discover mit Dynamics-Konten. Dynamics-Kunden müssen ein benutzerdefiniertes Feld für den Opportunitätsbetrag für [!DNL Marketo Measure] , um auf in Discover zu verweisen. Nach Abschluss muss der Kunde einen Workflow erstellen, der aktualisiert **both** die [!DNL Marketo Measure] Opportunity Amount (bizible2_bizible_Opportunity_amount) **und** das Feld für die benutzerspezifische Opportunitätszahl. Die [!DNL Marketo Measure] Das Feld &quot;Opportunity Amount&quot;wird mit dem Paket geliefert, es muss jedoch ein benutzerdefiniertes Feld erstellt werden.

Betrag-Workflow-Anweisungen:

**WORKFLOW Nr. 1**: Gelegenheit - Aktualisieren [!DNL Marketo Measure] Feld für Opportunity-Betrag und benutzerdefiniertes Feld = geschätzter Umsatz

Dieser Workflow läuft bei jeder Änderung des geschätzten Umsatzes auf offenen Stellen und aktualisiert die [!DNL Marketo Measure] Feld &quot;Opportunity Amount&quot;und Ihr benutzerdefiniertes Feld, um dem Feld &quot;Estimated Revenue&quot;zu entsprechen. Der Workflow sollte auf &quot;Echtzeit&quot;eingestellt sein, kann aber auch &quot;On-Demand&quot;ausgeführt werden, um offene Chancen zu aktualisieren.

Geben Sie Ihre [!DNL Marketo Measure] Kontaktpunkt mit dem Namen des Felds für die benutzerdefinierte Opportunity. Sie werden die [!DNL Marketo Measure] App-Opportunity-Einstellungen , um den Namen des Felds für das benutzerdefinierte Opportunity-Angebot einzuschließen. Dies gibt Discover an, welches Feld für die Berichterstellung verwendet werden soll.

**WORKFLOW Nr. 2**: Gelegenheit - Aktualisieren [!DNL Marketo Measure] Feld für Opportunity-Betrag und benutzerdefiniertes Feld = tatsächlicher Umsatz

Dieser Workflow wird in Echtzeit ausgeführt. Sie wird ausgelöst, wenn ein Benutzer eine Gelegenheit schließt, und aktualisiert die [!DNL Marketo Measure] Feld &quot;Opportunity Amount&quot;und Ihr benutzerdefiniertes Feld mit dem tatsächlichen Umsatz, der dem Formular Opportunity Close hinzugefügt wurde, bevor die Opportunity als geschlossen abgeschaltet wird.

## Teil 2: Geschätztes Abschlussdatum im Vergleich zum tatsächlichen Abschlussdatum {#part-estimated-close-date-vs-actual-close-date}

Standardmäßig sind die Pipeline-Umsatzdaten nicht im Dashboard verfügbar, da Dynamics standardmäßig über zwei Felder für das Schließdatum des Lagers verfügt: Geschätztes Schließdatum und tatsächliches Schließdatum. [!DNL Marketo Measure] kann nur auf ein Schließdatumsfeld im Dashboard verweisen. Wir verweisen derzeit auf das tatsächliche Schließdatum.

Wenn im Feld &quot;Tatsächliches Datum für Schließen&quot;keine Daten zu den Öffnungsmöglichkeiten vorhanden sind, werden im Dashboard keine Daten zu den Öffnungsmöglichkeiten angezeigt. Allerdings ist ein Workflow erforderlich, der auf der Opportunitätsphase basiert, um beide Datumsfelder zu unterstützen.

1. Erstellen Sie ein benutzerdefiniertes Feld für das Schließen des Datums für das Opportunity-Objekt (d. h. [!DNL Marketo Measure] Benutzerdefiniertes Datum für Schließen).
1. Erstellen Sie einen Workflow, um die [!DNL Marketo Measure] Benutzerdefiniertes Schließen-Datum mit dem Datum des Geschätzten Schließen-Datums oder des tatsächlichen Schließen-Datums, je nachdem, ob die Gelegenheit geöffnet oder geschlossen ist (der Workflow sollte für die Ausführung in Echtzeit gespeichert werden, muss jedoch mindestens einmal ausgeführt werden, um alle aktuellen offenen Optionen zu aktualisieren.)
1. Testen Sie den Workflow und überprüfen Sie, ob er funktioniert.
1. Kunde, der den API-Namen für das benutzerspezifische Datum für Schließen angibt [!DNL Marketo Measure].
1. [!DNL Marketo Measure] , um die [!DNL Marketo Measure] App-Einstellungen, um auf die [!DNL Marketo Measure] Benutzerdefiniertes Datum für Schließen im Dashboard.

   Nach Abschluss der oben genannten Schritte müssen wir Workflows ausführen, um sowohl die benutzerspezifische [!DNL Marketo Measure] Feld &quot;Opt-in-Betrag&quot;und [!DNL Marketo Measure] Benutzerdefiniertes Feld für das Schließen des Datums zu Ihren historischen Möglichkeiten, um die richtigen Daten widerzuspiegeln. Dadurch ändern sich wahrscheinlich die geänderten Ein-/Von-Felder, sodass Sie mit Ihrem Team prüfen möchten, ob dies Probleme verursacht.

So aktualisieren Sie die geschlossenen Möglichkeiten ...

1. Isolieren von Möglichkeiten, die seit der [!DNL Marketo Measure] Starten Sie das Datum, bis der Workflow aktiv ist. Dies ist die Gruppe historischer Möglichkeiten, die Sie über den Workflow aktualisieren müssen.
1. Exportieren Sie alle Datensätze nach Excel.
1. Öffnen Sie die Excel-Datei und aktivieren Sie den Inhalt.
1. Kopieren Sie die tatsächlichen Daten des Schließen-Datums in [!DNL Marketo Measure] Benutzerdefiniertes Schließdatum.
1. Tatsächliche Umsatzdaten kopieren nach [!DNL Marketo Measure] Benutzerdefinierter Opportunity-Betrag **und** [!DNL Marketo Measure] Opportunity Amount (es gibt zwei Felder.)
1. Speichern Sie die Datei.
1. Importieren Sie die Datei. Dynamics erkennt dies als Datei mit vorhandenen Datensätzen, die aktualisiert werden sollen.
1. Prüfen Sie, ob die Importdatei fehlgeschlagen ist.

>[!NOTE]
>
>Die in diesem Dokument beschriebenen Workflows sind nur eine Möglichkeit, die Felder zu aktualisieren, sodass [!DNL Marketo Measure] kann die korrekten Daten in Discover anzeigen. Wenn Sie eine andere Möglichkeit haben, die gleiche Aufgabe zu erledigen, können Sie sich dafür entscheiden. Grundsätzlich benötigen wir eine Art Workflow(e), der Folgendes ermöglicht:
>
> * Wenn Opp = Öffnen, aktualisieren Sie das benutzerdefinierte Feld für das Schließen des Datums, das benutzerdefinierte Feld für den Opt-in-Betrag und [!DNL Marketo Measure] opp amount -Feld auf Geschätztes Abschlussdatum bzw. geschätzten Umsatz.
> * Wenn &quot;Opp = Closed Won&quot;ist, aktualisieren Sie das benutzerdefinierte Feld für das Schließen des Datums, das benutzerdefinierte Feld für den Opt-Wert und [!DNL Marketo Measure] opp amount -Feld auf den Wert &quot;Tatsächliches Schließdatum&quot;bzw. &quot;Tatsächlicher Umsatz&quot;.
