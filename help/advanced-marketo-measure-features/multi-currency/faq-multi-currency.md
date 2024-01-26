---
unique-page-id: 27656745
description: Häufig gestellte Fragen (mehrere Währungen) - [!DNL Marketo Measure] - Produktdokumentation
title: Häufig gestellte Fragen (mehrere Währungen)
exl-id: 1d0936fb-4e66-4877-98d2-32c678a7ef3e
feature: Multi-Currency
source-git-commit: b7aea1e0789b2f4f3fd4b250c0f66595618317bb
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Häufig gestellte Fragen (mehrere Währungen) {#faq-multi-currency}

**Woher weiß ich, welches Feature-Bit aktiviert werden soll?**

Beachten Sie, dass es für diese Funktion zwei verschiedene Feature Bit gibt. Beide befinden sich im Tab Allgemein des CRM-Abschnitts unter Einstellungen: Mehrere Währungen und Erweiterte Währungen. Mehrere Währungen sollten aktiviert werden, wenn der Kunde mehr als eine Währung verwendet, während die zusätzliche Funktion und die erweiterten Währungen aktiviert werden können, wenn der Kunde [!DNL Salesforce]Funktion &quot;Erweiterte Währungsverwaltung&quot;, bei der der Benutzer einen zeitbasierten Bereich für Konversionsraten festlegen kann.

Leider wissen wir nicht, wann ein Kunde zwischen &quot;Einfach&quot;und &quot;Erweitert&quot;wechselt, wenn Advanced bereits aktiviert ist. Aus diesem Grund muss der Kunde die Einstellung Erweiterte Währungen manuell an seine CRM-Einstellung anpassen. Dies sollte für den Kunden sichtbar sein, wenn die Konversionen falsch sind. Das bedeutet, dass wir nicht wussten, welcher Konversionsgrad angewendet werden sollte.

**Warum gibt mir mein Werbekonto eine Warnmeldung aus?**

Neben Ihrem Anzeigenkonto wird eine Warnmeldung angezeigt, bei der Währungen von einer nicht unterstützten Währung eingehen können. In diesem Fall enthalten Ihre Dashboards Kacheln mit der Meldung &quot;Gemischte Währungen&quot;. Wir empfehlen Ihnen, mit Ihrem CRM-Administrator zusammenzuarbeiten, um sicherzustellen, dass diese unbekannte Währung eine Konversion in Ihrem CRM-System enthält.

**Was bedeutet &quot;Gemischte Währungen&quot;auf meiner Dashboard-Kachel?**

Wenn Sie eine Kachel mit der Meldung &quot;Gemischte Währungen&quot;am unteren Rand haben, bedeutet das, dass wir einige Kosten importiert haben, die einer Währung zugeordnet sind, die wir nicht erkennen. Da alle Konversionen aus dem CRM-System mit einer tatsächlichen Konversionsrate stammen müssen, bedeutet dies, dass Ihrem CRM diese Währung fehlt. Wir empfehlen Ihnen, mit Ihrem CRM-Administrator zusammenzuarbeiten, um sicherzustellen, dass diese unbekannte Währung eine Konversion in Ihrem CRM-System enthält.

**Wie kann ich eine neue Währung oder einen neuen Umrechnungskurs hinzufügen?**

Die Deklarierung einer neuen Währung oder Umrechnungskurse kann nur in [!DNL Salesforce] oder [!DNL Dynamics] sodass es für diese Werte nur eine einzige Quelle der Wahrheit gibt. Sobald eine neue Währung oder ein neuer Umrechnungskurs erkannt wurde, [!DNL Marketo Measure] werden das herunterladen und Ihnen zur Verfügung stellen. Wir bieten keinen Bereich, in dem diese Preise angegeben werden können.

**Die Währung wird nicht im richtigen Format angezeigt. Wie kann ich das ändern?**

Wir wissen, dass einige Länder eine andere Art haben, Beträge zu formatieren (z. B. 1.234.00, 1.234, 1.234). Aber wir führen ein weiteres Maß an Komplexität ein, wenn wir nicht nur die Währung eines Benutzers bestimmen müssen, sondern auch dessen Herkunftsland, da unterschiedliche Länder und Währungen unterschiedlich gehandhabt werden können. Das von uns gewählte konsistente Format ist 1.234.00. Dies kann nicht geändert werden.

**Warum können Sie das Währungssymbol für meine ausgewählte Währung nicht anzeigen?**

[!DNL Salesforce] und [!DNL Dynamics] die Beträge mit dem dreistelligen Konversionscode anzeigen. Aus Gründen der Konsistenz werden unsere konvertierten Beträge auch mit dem 3-Buchstaben-Konversionscode und nicht mit dem Symbol angezeigt.

**Was wird mein Kunde sehen, wenn mehrere Währungen nicht aktiviert sind?**

Wenn der Kunde nicht über die Funktion für mehrere Währungen verfügt, wird standardmäßig sein Währungsgebietsschema aus dem CRM ausgewählt und alle ISO-Codes geändert, die seine Ausgaben und Umsätze in der Unternehmenskurve anzeigen. Wenn dies nicht korrekt ist und der Kunde eine gemischte Verwendung der Währung hat, besteht die Lösung darin, ein Upgrade durchzuführen, um die Funktion mit mehreren Währungen zu erhalten.

**Wie wirkt sich diese Funktion auf Touchpoint-basierte Berichte im CRM aus?**

Für [!DNL Dynamics] und [!DNL Salesforce] Kunden, die nur die grundlegende (nicht erweiterte) Währungsverwaltung verwenden, sollten die Umsätze von Touchpoints korrekt konvertiert werden, sodass CRM-Berichte erwartungsgemäß funktionieren.

Leider gibt es einige Nuancen, wie dies für Benutzer von [!DNL Salesforce] Fortgeschrittenes Währungsmanagement aufgrund einer seit langem bestehenden Beschränkung von [!DNL Salesforce]. Die kurze Antwort auf &quot;Was tun wir in diesem Fall&quot; ist, dass wir Umsätze mithilfe der Pauschalsätze umrechnen, die im Tab &quot;Währungen verwalten&quot; (d. h. nicht erweiterter Standard) definiert sind. Mit anderen Worten, wir ignorieren die veralteten Wechselkurse ganz und gar, obwohl der Kunde die alten Wechselkurse definiert hat.

Für den interessierten Leser hier ist der Grund, warum es so funktioniert. Unsere Touchpoints verwenden Formelfelder zur Berechnung des Umsatzes (abgeleitet aus dem zugehörigen Opportunity-Betrag). [!DNL Salesforce] unterstützt nativ die Währungsumrechnung für diese Formelberechnungen, jedoch nur für ihren grundlegenden Charakter der Währungsunterstützung. Es ist unmöglich für uns, ein Formelfeld zu definieren, das auf die alten Wechselkurse verweist. [!DNL Salesforce] unterstützt diese Funktion einfach nicht, sodass wir keine Möglichkeit haben, in unseren Umsatzberechnungen auf die veralteten Zinssätze zu verweisen, obwohl diese veralteten Sätze in [!DNL Salesforce] (Es klingt verrückt, aber so funktioniert es.)

**Wenn mein Kunde einen Workflow zum Ausfüllen eines konvertierten Felds verwendet hat, wie sollte er dieses Feld dann verwenden?**

Da unser Angebot nun die Konversionen für den Kunden verarbeitet, empfehlen wir, die Workflows und das benutzerdefinierte Feld zu entfernen und den Rohdatenwert zu importieren.

>[!MORELIKETHIS]
>
>[Fehlerbenachrichtigungen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
