---
title: Profilerstellung für ASP.NET-Webanwendungen über die Befehlszeile | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling ASP.NET applications
- profling tools,ASP.NET applications
ms.assetid: 897c00d5-5767-433b-a960-4a29c6023ede
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 03cb8a6b28ed5f5fece49644d9b1df2608f3e36d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49895664"
---
# <a name="command-line-profiling-of-aspnet-web-applications"></a>Profilerstellung für ASP.NET-Webanwendungen über die Befehlszeile
In diesem Abschnitt werden die Vorgehensweisen und Optionen zum Erfassen von Leistungsdaten für [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]-Webanwendungen mit den [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-Profilerstellungstools über die Befehlszeile beschrieben.  
  
> [!NOTE]
>  Verbesserte Sicherheitsfunktionen in Windows 8 und Windows Server 2012 erforderten tiefgreifende Änderungen bei der Datenerfassung des Visual Studio-Profilers auf diesen Plattformen. Außerdem benötigen UWP-Apps neue Erfassungsmethoden. Weitere Informationen finden Sie unter [Leistungstools für Windows 8- und Windows Server 2012-Anwendungen](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Allgemeine Aufgaben
  
| Aufgabe | Verwandter Inhalt |
| - | - |
| **Einfaches Erfassen grundlegender ASP.NET-Profilerstellungsdaten:** Verwenden Sie das Tool **VSPerfASPNETCmd**, um Sampling-, Instrumentations-, .NET-Arbeitsspeicher-, Konflikt- oder Ebeneninteraktionsdaten ohne die Konfigurationsanforderungen und die Neustarts von Internetinformationsdienste (IIS) zu sammeln, die bei **VSPerfCmd** erforderlich sind. Mit **VSPerfASPNETCmd** können keine zusätzlichen Daten erfasst werden, und auch die Datensammlung lässt sich nicht beeinflussen. **Hinweis:** **VSPerfASPNETCmd** ist das bevorzugte Tool, wenn mit dem eigenständigen Profiler ein Profil für ASP.NET-Websites erstellt wird. | -   [Schnelle Website-Profilerstellung mit VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md) |
| **Sammeln von Anwendungsstatistikdaten:** Sammeln Sie Leistungsstatistikdaten mit der Samplingmethode. Samplingdaten sind beim Analysieren von CPU-Auslastungsproblemen sowie zum Verständnis der allgemeinen Leistungsmerkmale einer Anwendung hilfreich. | -   [Sammeln von Anwendungsstatistiken durch Sampling](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md) |
| **Sammeln ausführlicher Zeitsteuerungsdaten:** Sammeln Sie ausführliche Zeitsteuerungsinformationen mit der Instrumentationsmethode. Instrumentationsdaten sind beim Analysieren von EA-Problemen und für die detaillierte Analyse von Anwendungsszenarios hilfreich. | -   [Sammeln ausführlicher Zeitsteuerungsdaten mithilfe der Instrumentierung](../profiling/collecting-detailed-timing-data-aspnet-profiler-instrumentation-method.md) |
| **Sammeln von .NET-Arbeitsspeicherdaten:** Sammeln Sie mit Sampling oder Instrumentation Daten zur .NET-Speicherbelegung, die Auskunft über die Größe und Anzahl zugeordneter Objekte geben. Sie können auch Objektlebensdauerdaten sammeln, die die Größe und Anzahl von Objekten angeben, die in jeder Garbage Collection-Generation freigegeben werden. | -   [Sammeln von Arbeitsspeicherdaten](../profiling/collecting-memory-data-from-an-aspnet-web-application.md) |
| **Sammeln von Parallelitätsdaten:** Verwenden Sie die Parallelitätsmethode, um Daten zu Ressourcenkonflikten zu sammeln. **Hinweis:** Das Sammeln von Threadaktivitäts- und Visualisierungsdaten wird für Webanwendungen nicht unterstützt. | -   [Sammeln von Parallelitätsdaten](../profiling/collecting-concurrency-data-for-an-aspnet-web-application.md) |
| **Hinzufügen von Ebeneninteraktionsdaten:** Sie können Leistungsdaten zu synchronen [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)]-Aufrufen der [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]-Webanwendung an eine Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]-Datenbank hinzufügen. | -   [Erfassen von Ebeneninteraktionsdaten](../profiling/adding-tier-interaction-data-from-the-command-line.md) |
  
## <a name="related-tasks"></a>Verwandte Aufgaben

  
|Aufgabe|Verwandter Inhalt|  
|----------|---------------------|  
|**Profilerstellung für eigenständige (Client-)Anwendungen**|-   [Profilerstellung für eigenständige Anwendungen](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**Profilerstellung für Dienste**|-   [Profilerstellung für Dienste](../profiling/command-line-profiling-of-services.md)|