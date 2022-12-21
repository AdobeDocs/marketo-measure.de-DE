---
unique-page-id: 18874596
description: Benutzerdefinierte Online-Kanal-Einrichtung - [!DNL Marketo Measure] - Produktdokumentation
title: Benutzerdefinierte Online-Kanal-Einrichtung
exl-id: 170ac564-6cdd-4036-abf0-b9b230bed4f7
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '1236'
ht-degree: 0%

---

# Benutzerdefinierte Online-Kanal-Einrichtung {#online-custom-channel-setup}

Um eine genaue Berichterstellung zu erhalten, müssen Marketing-Kanäle eingerichtet werden, die der UTM-Strategie Ihres Unternehmens entsprechen. In diesem Handbuch erfahren Sie, wie Sie Ihre benutzerspezifischen Kanalregeln am besten konfigurieren.

## Vorbereitung {#before-you-begin}

Bevor Sie mit der Erstellung Ihrer Kanalregeln für [!DNL Marketo Measure]Nehmen Sie sich Zeit, um über die Organisation Ihrer Marketing-Kampagnen nachzudenken und zu erfahren, wie sie in die [!DNL Marketo Measure] Framework. Sie sollten festlegen, welche Kanäle, Unterkanäle, Kampagnen und verweisenden Websites Sie verfolgen möchten.

Folgendes sollte beachtet werden:

* Ihr Unternehmen kann maximal 40 benutzerdefinierte Marketing-Kanäle erstellen. Dies umfasst sowohl Offline- als auch Online-Kanäle.
* Ihr Unternehmen kann bis zu 200 Unterkanäle erstellen.
* Für jede Sammlung bzw. jeden Behälter von Daten ist eine eigene Regel erforderlich (Zeile im Arbeitsblatt), die angibt, wie die Daten organisiert werden. Seien Sie so spezifisch wie möglich.
* [!DNL Marketo Measure] -Logik priorisiert Daten in absteigender Reihenfolge, beginnend mit der obersten Zeile des Arbeitsblatts und nach unten. Er liest jeden Behälter oder jede Zelle nacheinander, um nach der ersten Anpassung zu suchen. Die Daten werden dann nach den Werten in diesen Behältern sortiert. Mehr dazu unten.
* Sortieren Sie Ihr Blatt nicht in alphabetischer Reihenfolge, da dies die Logikregeln stört.
* Nach dem Hochladen der Datei können Sie keine der Regeln für sieben Tage ändern. [!DNL Marketo Measure] nutzt diese Zeit zur Verarbeitung und Aktualisierung der Touchpoints.

## [!DNL Marketo Measure] Logik und Prioritäten {#marketo-measure-logic-and-priorities}

Der erste Schritt besteht darin, die benutzerdefinierte Kanal-Tabelle aus dem [!DNL Marketo Measure] App. Navigieren Sie zu **Einstellungen** unter **Mein Konto** Registerkarte und wählen Sie **Online**. Sie können entweder **Originalvorlage herunterladen** oder **Aktuelle Regeln herunterladen**.

![](assets/1.png)

Die Tabelle enthält sieben Spalten:

![](assets/2.png)

* **Kanal:** Fügen Sie hier die verschiedenen Marketingkanäle hinzu
* **Subchannel:** die entsprechenden Unterkanäle hier hinzufügen
* **Kampagne:** Fügen Sie hier Kampagnennamen hinzu, unabhängig davon, ob der Wert aus UTMs oder Salesforce-Kampagnen für die Variable [!DNL Marketo Measure] Aktivitätsfunktion
* **Mittel:** Die mittlere Spalte stellt den Wert des Parameters utm_medium dar.
* **Quelle:** Die Quellspalte stellt den Wert des Parameters utm_source dar.
* **Landingpage:** Landingpage hier hinzufügen
* **Verweisende Website:** die URLs von Websites, die auf Traffic auf Ihren Seiten verweisen oder integriert sind [!DNL Marketo Measure] Logik (durch Klammern angegeben)

In der achten Spalte wird angegeben, welche Regeln nicht aus der Tabelle mit &quot;Nicht entfernen&quot;gelöscht werden können. Am oberen Rand des Arbeitsblatts befinden sich standardmäßige Kanalregeln, die [!DNL Marketo Measure] empfiehlt, diese Kanäle nicht zu ändern oder zu entfernen, selbst wenn Sie diese Kanäle nicht verwenden. [!DNL Marketo Measure] verfügt über tiefe Integrationen mit diesen Plattformen, sodass sie standardmäßig eingeschlossen sind.

Die Zeilen stellen Regeln und die Reihenfolge dar, in der [!DNL Marketo Measure] priorisiert die Daten. Die erste Zeile hat Vorrang vor der zweiten Zeile, die zweite Zeile hat Priorität vor der dritten Zeile usw. Bei der Bestimmung, in welchen Marketing-Kanälen und Unterkanälen Touchpoints zusammengefasst werden sollen, [!DNL Marketo Measure] liest von oben nach unten, von links nach rechts, bis eine Zeile gefunden wird, die den Kriterien des Touchpoints entspricht. (IE, wenn ein Touchpoint einen utm_source=Facebook hat, wird der Touchpoint aufgrund von Regel 15 im Screenshot im Kanal Social.Facebook zusammengefasst.)

![](assets/3.png)

[!DNL Marketo Measure] enthält 12 Standardkanäle für Ihre Verwendung. Diese Kanäle korrelieren mit Plattformen, mit denen [!DNL Marketo Measure] vollständig integriert ist. Unabhängig davon, ob Sie sie verwenden oder nicht, entfernen Sie sie bitte nicht. Wenn Sie eine dieser Plattformen verwenden, z. B. Bing Ads, aber lieber eine andere Benennungsregel für den Kanal oder den Unterkanal verwenden, können Sie den Namen aktualisieren. Ein Beispiel wird in der Abbildung unten gezeigt.

![](assets/4.png)

Auch die Struktur der Regeln ist wichtig. Die Regeln können wie wiederholte Informationen und fehlende Daten aussehen, aber diese Struktur ist beabsichtigt. Für eine genaue Sortierung der Daten ist es erforderlich, jede einzelne Quelle separat dem entsprechenden Kanal zuzuordnen - selbst Quellen, die Unterkanäle und Kanäle gemeinsam nutzen. Je detaillierter und detaillierter die Regeln sind, desto aufschlussreicher werden die Ergebnisse sein. Grundsätzlich empfiehlt es sich, für jede einzelne Marketing-Maßnahme, die Sie verfolgen möchten, eine detaillierte Regel zu erstellen.

Betrachten Sie die folgende Situation: Sie haben andere Anzeigen, die Sie aus irgendeinem Grund nicht verfolgen möchten, oder Sie erhalten Besuche auf Ihrer Website von einem bekannten Kanal, aber keine bekannte Quelle. Diese Situation kann zu Datenverlusten führen, wenn [!DNL Marketo Measure] kann die geeignete Regel zum Sortieren der Daten nicht finden. Um dies zu verhindern, [!DNL Marketo Measure] empfiehlt Ihnen, Ihre Regel über mehrere Zeilen aufzuheben.

Jeder Parameter oder jede Komponente der Regel wird dem Kanal separat zugeordnet. Wenn beispielsweise [!DNL Marketo Measure] has [!DNL Facebook] zu sortierende Daten; sucht nach Regeln, die sich auf [!DNL Facebook]. Es scannt von oben nach unten. Im unten abgebildeten Beispiel [!DNL Marketo Measure] würde verstehen, dass für die erste [!DNL Facebook] -Unterkanal ist nur der Quellparameter, mit dem Daten in den Behälter dieser Regel abgelegt werden.

![](assets/5.png)

Die nächste Regel fragt nur nach dem Parameter medium ab, sodass alle Daten mit diesem Parameter in diesen Kanal zusammengefasst werden. Schließlich [!DNL Facebook], werden alle Daten, die von der Facebook-URL stammen, in den letzten Facebook-Behälter aufgenommen.

Der Standardkanal &quot;Sonstige&quot;ist vorhanden, um Daten zu erfassen, die nicht den Kriterien einer Regel entsprechen. Beachten Sie, dass einige Buckets im Kanal Sonstige Sternchen (&#42;). Diese Sternchen stellen Platzhalterzeichen dar, die als Auffangbehälter dienen.

![](assets/6.png)

Aufgrund von [!DNL Marketo Measure] -Logik von oben nach unten, beachten Sie bitte, dass die Platzhalterregel mit einem Sternchen (&#42;), sollte am Ende Ihres Regelblatts platziert werden. Alle Daten, die nicht von anderen Regeln erfasst oder sortiert werden, werden automatisch zu diesem Platzhalter-Bucket hinzugefügt.

Im Folgenden finden Sie weitere Beispiele für die Logik von Platzhaltern:

* &#42;email&#42; = enthält &quot;email&quot;
* &#42;email = endet mit &quot;email&quot;
* email&#42; = [!UICONTROL beginnt mit E-Mail]

Beachten Sie außerdem, dass Sie beim Erstellen eines Unterkanals für einen Ihrer Kanäle einen Unterkanal für alle Regeln unter diesem Kanal erstellen müssen. Anders ausgedrückt: Wenn Sie einen Unterkanal erstellen, können Sie den Rest der Spalten nicht leer lassen.

## Einrichten Ihrer benutzerspezifischen Kanalregeln {#setting-up-your-custom-channels-rules}

Sobald Sie sich für die Organisation und Priorisierung Ihrer Daten entschieden haben, können Sie Ihre Regeln zur Tabelle hinzufügen. Nachfolgend finden Sie einige Best Practices:

* Halten Sie Ihre Regeln von Anfang an so einfach wie möglich. Sie können jederzeit auf den Regeln aufbauen.
* Fügen Sie den Kanalnamen keine Sonderzeichen hinzu (z. B. $%#&amp;&#42;@)
* Bearbeiten Sie nicht die mit BingAds und AdWords verknüpften Regeln. Diese Regeln sind von entscheidender Bedeutung für die Zusammenfassung der Daten, die automatisch aus dem [!DNL Marketo Measure] API-Integration mit diesen Plattformen. Eine Änderung des Subkanals und des Kanalnamens an Ihre Anforderungen ist jedoch kein Problem.
* Entfernen Sie nicht die Regeln, die einen &quot;Do Not Remove&quot;-Hinweis enthalten.
* Organische Suchregeln werden immer nach dem [!UICONTROL Gebührenpflichtige Suchregeln]
* Sie können keine Regeln basierend auf verschiedenen Subdomains erstellen.
* Wenn Sie einer Zelle im Arbeitsblatt mehr als einen Wert hinzufügen müssen, trennen Sie diese durch ein Semikolon `;` nur. Keine Kommas oder Leerzeichen.
* Sie müssen Punkt com (.com) nicht am Ende der verweisenden URL hinzufügen.
* Wenn Sie eine verweisende URL hinzufügen, dürfen Sie sie nicht wie die anderen API-bezogenen Regeln in Klammern setzen.

## Hochladen Ihrer benutzerspezifischen Kanalregeln {#uploading-your-custom-channels-rules}

Stellen Sie sicher, dass alle neuen Kanal- und Unterkanalwerte, die Sie in der CSV-Datei hinzufügen, bereits im Kanaleinstellungsbereich Ihres Bizible-Kontos hinzugefügt wurden. Überprüfen Sie, ob alle Kanal- und Subkanalnamen in der CSV mit dem Kanaleinstellungsbereich Ihrer [!DNL Marketo Measure] -Konto. Stellen Sie sicher, dass Sie nach Kommas und Leerzeichen suchen.

Wenn Sie beim Hochladen eine Fehlermeldung erhalten, beheben Sie das Problem und laden Sie es erneut hoch. Wenn keine Fehlermeldung empfangen wird, klicken Sie auf **Speichern und verarbeiten** unten auf der Seite.
