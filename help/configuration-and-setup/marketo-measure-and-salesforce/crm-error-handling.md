---
description: Erfahren Sie, wie Sie Fehler in CRM-Exporten handhaben.
title: Fehlerbehandlung für CRM-Exporte
feature: Salesforce
source-git-commit: 8fa33a363b9e853dd074848032e1810b72fe169c
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Fehlerbehandlung für CRM-Exporte

Die Einstellung &quot;Pause bei Exportfehlern&quot;befindet sich unter **Mein Konto** > **Einstellungen** > **CRM** > **Allgemein**. Diese Funktion ist nur sichtbar, wenn die Funktion &quot;In CRM exportieren&quot;aktiviert ist. Damit können Sie steuern, ob CRM-Exportvorgänge angehalten werden sollen, wenn ein Fehler auf Datensatzebene auftritt.

Wenn diese Funktion aktiviert ist, wird der Exportauftrag nicht mehr ausgeführt und befindet sich weiterhin im Datensatz, in dem der Fehler aufgetreten ist, bis das Problem behoben ist. Diese Fehler sind in der Regel auf fehlende Berechtigungen, falsch angewendete benutzerdefinierte Validierungsregeln oder Probleme in Workflows/Triggern zurückzuführen. Der Auftrag wird weiterhin wie geplant ausgeführt und versucht automatisch erneut, den fehlgeschlagenen Datensatz zu exportieren, bis er erfolgreich war.

Wenn Sie diese Funktion deaktivieren, wird ein Warnhinweis-Popup angezeigt, in dem Sie darüber informiert werden, dass dies zu Dateninkonsistenzen führen kann. Es liegt in Ihrer Verantwortung, alle Probleme anzugehen, die sich aus diesen Inkonsistenzen ergeben können.

In beiden Fällen werden alle aufgetretenen Fehler auf Datensatzebene, unabhängig davon, ob die Funktion ein- oder ausgeschaltet ist, in der Tabelle `ExportErrors` protokolliert und der Auftrag `CRMExport_ExportError` versucht automatisch, diese Datensätze täglich erneut zu exportieren. Dadurch entfällt die Notwendigkeit einer Support-Anfrage zum Initiieren eines erneuten Exports, da dies automatisch ohne Eingriff von Entwicklern erfolgt.

Warum ist das Verhalten zum Anhalten von Aufträgen angesichts der Funktion `ExportErrors` erforderlich? Indem Sie die regulären CRM-Exportvorgänge an einem bestimmten Datensatz stoppen, wird die Fehlerbehebung deutlich vereinfacht. Dadurch können Sie Aufträge lokal ausführen und die Erstellung einer potenziell großen Anzahl von ExportErrors verhindern, die beim erneuten Export abgerufen und verarbeitet werden müssen.

Diese Funktion kann je nach bevorzugtem Verhalten aktiviert oder deaktiviert werden. Wenn Sie beispielsweise auf einen besonders herausfordernden Fehlercode stoßen und vorziehen, &quot;unvollständige&quot;Daten vorübergehend zu akzeptieren, können Sie die Funktion deaktivieren. Sobald das Problem behoben ist, können Sie die Funktion wieder aktivieren, um sicherzustellen, dass künftige Exporte vollständig und korrekt sind.
