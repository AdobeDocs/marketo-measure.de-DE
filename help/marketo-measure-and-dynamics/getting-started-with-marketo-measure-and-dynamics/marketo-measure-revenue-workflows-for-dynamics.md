---
unique-page-id: 37356132
description: '[!DNL Marketo Measure] Umsatz-Workflows für Dynamics - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Umsatz-Workflows für Dynamics'
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---

# [!DNL Marketo Measure] Umsatz-Workflows für Dynamics {#marketo-measure-revenue-workflows-for-dynamics}

## Teil 1: Geschätzter Umsatz vs. tatsächlicher Umsatz {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] verweist standardmäßig auf ein Standard-Umsatzfeld (tatsächlicher Umsatz), Dynamics verfügt jedoch über zwei standardmäßige Umsatzfelder: &quot;Tatsächlicher Umsatz&quot;und &quot;Geschätzter Umsatz&quot;. Damit Pipeline-Umsätze im Discover Dashboard verfügbar sind, sind ein benutzerdefiniertes Feld und ein Workflow erforderlich, um den korrekten Betrag entweder aus dem Feld Geschätzter Umsatz oder dem Feld Tatsächlicher Umsatz zu erfassen, je nachdem, ob die Gelegenheit offen oder geschlossen ist (Won).

Schritt 1: Erstellen eines benutzerdefinierten Opportunity-Felds in Dynamics

>[!NOTE]
>
>Alle Umsatzfelder von Dynamics verfügen über ein Basisfeld und ein reguläres Feld. Ignorieren Sie das Basisfeld.

Schritt 2: Erstellen Sie einen Workflow, der sowohl das in Schritt 1 erstellte benutzerdefinierte Feld für den Opportunity-Betrag als auch das Feld [!DNL Marketo Measure] Opportunity Amount aktualisiert.

>[!NOTE]
>
>Wir können nicht auf das Feld [!DNL Marketo Measure] Opportunity Amount (bizible2_bizible_Opportunity_amount) in Discover mit Dynamics-Konten verweisen. Dynamics-Kunden müssen ein benutzerdefiniertes Feld für den Opportunitätsbetrag erstellen, damit [!DNL Marketo Measure] in Discover auf verweisen kann. Nach Abschluss muss der Kunde einen Workflow erstellen, der **sowohl** als auch [!DNL Marketo Measure] den Betrag der Opportunity (bizible2_bizible_Opportunity_amount) **und** das Feld für den benutzerdefinierten Opportunity-Betrag aktualisiert. Das Feld [!DNL Marketo Measure] Opportunity Amount wird mit dem Paket geliefert, es muss jedoch ein benutzerdefiniertes Feld erstellt werden.

Betrag-Workflow-Anweisungen:

**WORKFLOW #1**: Gelegenheit - Update [!DNL Marketo Measure] Opportunity Amount Field &amp; Custom Field = Estimated Revenue

Dieser Workflow läuft bei jeder Änderung des geschätzten Umsatzes auf offene Chancen und aktualisiert das Feld [!DNL Marketo Measure] Opportunity Amount und Ihr benutzerdefiniertes Feld so, dass es dem Feld Geschätzter Umsatz entspricht. Der Workflow sollte auf &quot;Echtzeit&quot;eingestellt sein, kann aber auch &quot;On-Demand&quot;ausgeführt werden, um offene Chancen zu aktualisieren.

Geben Sie Ihrem [!DNL Marketo Measure]-Kontaktpunkt den Namen des Felds für den benutzerspezifischen Opportunitätsbetrag an. Sie aktualisieren die [!DNL Marketo Measure] App-Opportunity-Einstellungen, um den Namen des Felds für das benutzerdefinierte Opportunity-Angebot einzuschließen. Dadurch wird Discover informiert, welches Feld für die Berichterstellung verwendet werden soll.

**WORKFLOW #2**: Gelegenheit - Aktualisierung von [!DNL Marketo Measure] Feld für die Opportunity und benutzerdefiniertes Feld = tatsächlicher Umsatz

Dieser Workflow wird initiiert, wenn ein Benutzer eine Gelegenheit schließt und das Feld [!DNL Marketo Measure] Opportunity Amount (Opportunity Amount) sowie Ihr benutzerdefiniertes Feld aktualisiert, wobei der tatsächliche Umsatz dem Formular Opportunity Close hinzugefügt wird, bevor die Opportunity als geschlossen abgeschaltet wird.

## Teil 2: Geschätztes Abschlussdatum im Vergleich zum tatsächlichen Abschlussdatum {#part-estimated-close-date-vs-actual-close-date}

Standardmäßig sind die Pipeline-Umsatzdaten nicht im Dashboard verfügbar, da Dynamics standardmäßig über zwei Felder für das Schließdatum des Lagers verfügt: Geschätztes Schließdatum und tatsächliches Schließdatum. [!DNL Marketo Measure] kann nur auf ein Schließen-Datumsfeld im Dashboard verweisen und es verweist auf das tatsächliche Schließen-Datum.

Wenn im Feld &quot;Tatsächliches Datum für Schließen&quot;keine Daten zu den Öffnungsmöglichkeiten vorhanden sind, enthält das Dashboard keine Daten zu den Öffnungsmöglichkeiten. Allerdings ist ein Workflow erforderlich, der auf der Opportunitätsphase basiert, um beide Datumsfelder zu unterstützen.

1. Erstellen Sie ein benutzerdefiniertes Datumsfeld für Schließen am Opportunity-Objekt ([!DNL Marketo Measure] Benutzerdefiniertes Schließdatum).
1. Erstellen Sie einen Workflow, um das Feld &quot;[!DNL Marketo Measure] Benutzerdefiniertes Schließdatum&quot;mit dem Datum aus dem geschätzten Schließdatum oder dem tatsächlichen Abschlussdatum zu aktualisieren, je nachdem, ob die Gelegenheit geöffnet oder geschlossen ist (der Workflow sollte zur Ausführung in Echtzeit gespeichert werden, muss jedoch mindestens einmal ausgeführt werden, um alle aktuellen geöffneten OPS zu aktualisieren).
1. Testen Sie den Workflow und überprüfen Sie, ob er funktioniert.
1. Der Kunde muss den API-Namen für das benutzerspezifische Close-Datum [!DNL Marketo Measure] angeben.
1. [!DNL Marketo Measure] , um die Einstellungen der [!DNL Marketo Measure] App so zu aktualisieren, dass sie auf das Feld [!DNL Marketo Measure] Benutzerdefiniertes Schließdatum im Dashboard verweisen.

   Führen Sie nach Abschluss der oben genannten Schritte die Workflows aus, um sowohl das Feld &quot;Benutzerdefinierter Opp-Betrag&quot;(0) als auch das Feld &quot;[!DNL Marketo Measure] Benutzerdefiniertes Close-Datum&quot;zu aktualisieren und die korrekten Daten widerzuspiegeln. [!DNL Marketo Measure] Dadurch ändern sich wahrscheinlich die geänderten Ein-/Von-Felder. Stellen Sie daher sicher, dass Ihr Team weiß, ob dies Probleme verursacht.

So aktualisieren Sie die geschlossenen Möglichkeiten ...

1. Isolieren Sie die Möglichkeiten, die seit dem Startdatum von [!DNL Marketo Measure] geschlossen wurden, bis der Workflow aktiv ist. Dies ist die Gruppe historischer Möglichkeiten, die Sie über den Workflow aktualisieren müssen.
1. Exportieren Sie alle Datensätze nach Excel.
1. Öffnen Sie die Excel-Datei und aktivieren Sie den Inhalt.
1. Kopieren Sie die tatsächlichen Daten des Schließen-Datums in das benutzerdefinierte Datum für die Schließen-Schließung ( [!DNL Marketo Measure] Custom Close Date).
1. Kopieren Sie die tatsächlichen Umsatzdaten in den Wert [!DNL Marketo Measure] Benutzerdefinierte Opportunity Amount **und den Wert** [!DNL Marketo Measure] Opportunity Amount (es gibt zwei Felder).
1. Speichern Sie die Datei.
1. Importieren Sie die Datei. Dynamics erkennt dies als Datei mit vorhandenen Datensätzen, die aktualisiert werden sollen.
1. Prüfen Sie, ob die Importdatei fehlgeschlagen ist.

>[!NOTE]
>
>Die in diesem Dokument beschriebenen Workflows sind nur eine Möglichkeit, die Felder zu aktualisieren, damit [!DNL Marketo Measure] die richtigen Daten in Discover anzeigen kann. Wenn Sie eine andere Möglichkeit haben, die gleiche Aufgabe zu erledigen, können Sie sich dafür entscheiden. Grundsätzlich benötigen wir einen Workflow, der Folgendes ermöglicht:
>
> * Wenn Opp = Öffnen, aktualisieren Sie das benutzerdefinierte Feld für das Schließen des Datums, das benutzerdefinierte Feld für den Opt-in-Betrag und das Feld für den Opt-in-Betrag, sodass es den geschätzten Close-Datum bzw. den geschätzten Umsatz entspricht.[!DNL Marketo Measure]
> * Wenn &quot;Opp = Geschlossener Monat&quot;ist, aktualisieren Sie das benutzerdefinierte Feld für das Datum des Schließen, das benutzerdefinierte Feld für den Opt-in-Betrag und das Feld für den Opt-in-Betrag auf &quot;Tatsächliches Datum schließen&quot;bzw. &quot;Tatsächlicher Umsatz&quot;.[!DNL Marketo Measure]
