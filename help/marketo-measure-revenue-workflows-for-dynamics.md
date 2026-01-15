---
description: Workflows zur Abstimmung der Dynamics-Umsatz- und Abschlussdatumsfelder für Marketo Measure-Berichte
title: '[!DNL Marketo Measure] Umsatz-Workflows für Dynamics'
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 0%

---

# [!DNL Marketo Measure] Umsatz-Workflows für Dynamics {#marketo-measure-revenue-workflows-for-dynamics}

## Teil 1: Geschätzte Einnahmen vs. tatsächliche Einnahmen {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] verweist standardmäßig auf ein Standardeinnahmenfeld (tatsächlicher Umsatz), Dynamics verfügt jedoch über zwei Standardeinnahmenfelder: „Tatsächlicher Umsatz“ und „Geschätzter Umsatz“. Damit Pipeline-Umsatz im Discover-Dashboard verfügbar sind, sind ein benutzerdefiniertes Feld und ein Workflow erforderlich, um den richtigen Betrag entweder aus dem Feld Geschätzter Umsatz oder dem Feld Tatsächlicher Umsatz zu erfassen, je nachdem, ob die Opportunity offen oder geschlossen (gewonnen) ist.

Schritt 1: Benutzerdefiniertes Feld für den Opportunity-Betrag in Dynamics erstellen

>[!NOTE]
>
>Alle Dynamics-Umsatzfelder verfügen über ein Basisfeld und ein reguläres Feld. Ignorieren Sie das Basisfeld.

Schritt 2: Erstellen Sie einen Workflow, der sowohl das in Schritt 1 erstellte Feld für den benutzerdefinierten Opportunity-Betrag als auch das Feld für den [!DNL Marketo Measure] Opportunity-Betrag aktualisiert.

>[!NOTE]
>
>Wir können nicht auf das Feld „Opportunity-Betrag [!DNL Marketo Measure]&quot; (bizible2_bizible_unity_amount) in Discover mit Dynamics-Konten verweisen. Dynamics-Kunden müssen ein benutzerdefiniertes Feld für den Opportunity-Betrag erstellen, damit [!DNL Marketo Measure] in Discover auf verweisen kann. Nach Abschluss muss der Kunde einen Workflow erstellen, der **sowohl** Feld [!DNL Marketo Measure] Opportunity-Betrag (Bizible2_Bizible_Opportunity-Betrag) **als auch** Feld Benutzerdefinierter Opportunity-Betrag) aktualisiert. Das Feld Opportunity-Betrag [!DNL Marketo Measure] wird mit dem Paket geliefert, es muss jedoch ein benutzerdefiniertes Feld erstellt werden.

Workflow-Anweisungen für Betrag:

**WORKFLOW #1**: Opportunity - Feld „Betrag [!DNL Marketo Measure] Opportunity“ und benutzerdefiniertes Feld aktualisieren = Geschätzter Umsatz

Dieser Workflow wird für offene Opportunities jedes Mal ausgeführt, wenn sich der geschätzte Umsatz ändert, und aktualisiert das Feld Opportunity-Betrag und Ihr benutzerdefiniertes Feld [!DNL Marketo Measure] so, dass sie dem Feld Geschätzter Umsatz entsprechen. Der Workflow sollte auf „Echtzeit“ eingestellt sein, kann aber auch „on demand“ ausgeführt werden, um offene Opportunities zu aktualisieren.

Geben Sie Ihren [!DNL Marketo Measure] Kontaktpunkt mit dem Namen des benutzerdefinierten Betragsfelds für die Opportunity an. Sie aktualisieren die Opportunity-Einstellungen der [!DNL Marketo Measure]-App, um den Namen des benutzerdefinierten Betragsfelds für die Opportunity aufzunehmen. Dadurch wird festgelegt, welches Feld im Reporting verwendet werden soll.

**WORKFLOW #2**: Opportunity - Feld „Betrag [!DNL Marketo Measure] Opportunity“ und benutzerdefiniertes Feld aktualisieren = Tatsächlicher Umsatz

Dieser Workflow wird gestartet, wenn ein Benutzer eine Opportunity schließt und das Feld Opportunity-Betrag [!DNL Marketo Measure] und Ihr benutzerdefiniertes Feld mit dem tatsächlichen Umsatz aktualisiert, der dem Formular Opportunity-Abschluss hinzugefügt wurde, bevor die Opportunity als geschlossen gesperrt wird.

## Teil 2: Geschätztes Abschlussdatum im Vergleich zum tatsächlichen Abschlussdatum {#part-estimated-close-date-vs-actual-close-date}

Standardmäßig sind Pipeline-Umsatzdaten nicht im Dashboard verfügbar, da Dynamics standardmäßig zwei Felder für das Abschlussdatum des Lagerbestands hat: Geschätztes Abschlussdatum und Tatsächliches Abschlussdatum. [!DNL Marketo Measure] kann nur auf ein Abschlussdatumsfeld im Dashboard verweisen und es verweist auf das tatsächliche Abschlussdatum.

Wenn offene Opportunitys im Feld Tatsächliches Abschlussdatum keine Daten haben, enthält das Dashboard keine Daten zu offenen Opportunitys. Allerdings ist ein auf der Opportunity-Phase basierender Workflow erforderlich, um beide Datumsfelder zu unterstützen.

1. Benutzerdefiniertes Abschlussdatumsfeld im Opportunity-Objekt erstellen ([!DNL Marketo Measure] benutzerdefiniertes Abschlussdatum).
1. Erstellen Sie einen Workflow, um das benutzerdefinierte [!DNL Marketo Measure]-Abschlussdatumsfeld mit dem Datum entweder des geschätzten Abschlussdatums oder des tatsächlichen Abschlussdatums zu aktualisieren, je nachdem, ob die Opportunity offen oder geschlossen ist (der Workflow sollte gespeichert werden, um in Echtzeit ausgeführt zu werden, muss jedoch mindestens einmal „on demand“ ausgeführt werden, um alle aktuellen offenen Opportunities zu aktualisieren).
1. Testen Sie den Workflow und bestätigen Sie, dass er funktioniert.
1. Kunde, um den benutzerdefinierten API-Namen für das Abschlussdatum für [!DNL Marketo Measure] anzugeben.
1. [!DNL Marketo Measure] Sie die Einstellungen der [!DNL Marketo Measure] App so aktualisieren, dass sie auf das Feld Benutzerdefiniertes [!DNL Marketo Measure] Abschlussdatum im Dashboard verweisen.

   Führen Sie nach Abschluss der oben genannten Schritte die Workflows aus, um sowohl das Feld Benutzerdefinierter [!DNL Marketo Measure]-Opportunity-Betrag als auch das Feld Benutzerdefiniertes Abschlussdatum [!DNL Marketo Measure] für Ihre historischen Opportunitys zu aktualisieren, um die richtigen Daten widerzuspiegeln. Dadurch werden wahrscheinlich die Felder Geändert am/von geändert. Sie sollten daher bei Ihrem Team nachfragen, ob dies Probleme verursacht.

Um die geschlossenen Opportunities zu aktualisieren…

1. Isolieren Sie Vertriebschancen, die seit dem Startdatum Ihres [!DNL Marketo Measure] geschlossen wurden, bis der Workflow aktiv ist. Dies ist die Gruppe historischer Opportunitys, die Sie über den Workflow aktualisieren müssen.
1. Alle Datensätze nach Excel exportieren.
1. Excel-Datei öffnen, Inhalt aktivieren.
1. Kopieren Sie die Daten zum tatsächlichen Abschlussdatum in [!DNL Marketo Measure] benutzerdefiniertes Abschlussdatum.
1. Kopieren Sie die tatsächlichen Umsatzdaten in [!DNL Marketo Measure] benutzerdefinierten Opportunity-Betrag **und** [!DNL Marketo Measure] Opportunity-Betrag (es gibt zwei Felder).
1. Datei speichern.
1. Datei importieren. Dynamics erkennt dies als Datei mit vorhandenen Datensätzen, die aktualisiert werden müssen.
1. Auf Fehler bei der Importdatei prüfen.

>[!NOTE]
>
>Die in diesem Dokument beschriebenen Workflows sind nur eine Möglichkeit, die Felder zu aktualisieren, damit [!DNL Marketo Measure] die richtigen Daten in Discover anzeigen können. Wenn Sie dieselbe Aufgabe auf eine andere Art und Weise erledigen können, können Sie es tun. Im Grunde benötigen wir von ihnen eine Art Workflow, der Folgendes ermöglicht:
>
> * Wenn Opportunity = Offen ist, aktualisieren Sie das benutzerdefinierte Feld für das Abschlussdatum, das benutzerdefinierte Feld für den Opportunity-Betrag und [!DNL Marketo Measure] Feld für den Opportunity-Betrag auf das geschätzte Abschlussdatum bzw. den geschätzten Umsatz.
> * Wenn Opportunity = Gewonnen geschlossen ist, aktualisieren Sie das benutzerdefinierte Feld „Abschlussdatum“, das benutzerdefinierte Feld „Opportunity-Betrag“ und [!DNL Marketo Measure] Feld „Opportunity-Betrag“ auf das aktuelle Abschlussdatum bzw. den tatsächlichen Umsatz.
