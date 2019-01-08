---
title: Erste Schritte mit Roslyn-Analysetools | Microsoft-Dokumentation
ms.date: 04/02/2018
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 591e09596c92476b7664b541d74344099d19ecb9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53874528"
---
# <a name="get-started-with-roslyn-analyzers"></a>Erste Schritte mit Roslyn-Analysetools

Mit live-projektbasierten codeanalysemodulen in Visual Studio können die API-Autoren domänenspezifische Codeanalyse als Teil ihrer NuGet-Pakete schicken. Da diese Analysemodule durch das .NET Compiler Platform (Codename "Roslyn") unterstützt werden, können sie Warnungen in Ihrem Code führen, während der Eingabe, bevor Sie die Zeile (nicht mehr darauf warten, erstellen Sie Ihren Code, um Probleme zu ermitteln) abgeschlossen haben. Analyzer können auch auftreten, einen automatischen Codefix über die Visual Studio-Glühbirne-Eingabeaufforderung, bereinigen Sie Ihren Code sofort zu können.

## <a name="get-started"></a>Erste Schritte

[Einführung in Roslyn live Code-Analyzer und exemplarische Vorgehensweise](https://msdn.microsoft.com/magazine/dn879356.aspx)

[Fügen Sie codefehlerbehebungen Exemplarische Vorgehensweise: Bieten Sie Benutzern Korrekturen für Analyzer-Probleme](https://msdn.microsoft.com/magazine/dn904670.aspx)

[Einführung und exemplarische Vorgehensweise des Analyzers der realen Welt kommunizieren.](https://channel9.msdn.com/events/Build/2015/3-725)

[Roslyn-Analyzer realen](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) , die Sie können außerdem sehen Sie sich als ein [sprechen](https://channel9.msdn.com/events/Build/2015/3-725)

[Beispiele auf GitHub an, gruppiert drei Arten von Analysen](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[Einführung und Überblick über einige Analysen kommunizieren.](https://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="see-also"></a>Siehe auch

- [Übersicht über die Roslyn-Analyzer](../code-quality/roslyn-analyzers-overview.md)
- [Tutorial: Schreiben Sie Ihre erste Lösung für Analyzer und code](/dotnet/csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix)
- [.NET Compiler Platform-Version-Paketverweis](roslyn-version-support.md)
- [Weitere-Dokumentation auf der GitHub-OSS-Website](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [FxCop-Regeln, die mit Roslyn-Analysetools auf GitHub implementiert](http://roslynanalyzersstatus.azurewebsites.net/)
