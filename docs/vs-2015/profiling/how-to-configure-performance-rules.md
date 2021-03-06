---
title: 'Vorgehensweise: Konfigurieren von Leistungsregeln | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.ruleseditor
ms.assetid: a148b468-b849-4858-880a-808a6b47e596
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b4750dcd245094d0ea116097c7e58b87065aa91
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51765106"
---
# <a name="how-to-configure-performance-rules"></a>Vorgehensweise: Konfigurieren der Leistungsregeln der Profilerstellungstools
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die Leistungswarnungen der Profilerstellungstools von Visual Studio deuten auf Probleme in einer mit einem Profil versehenen Anwendung hin, die die Programmausführung verlangsamen können. Warnungen können auch anzeigen, dass Sie möglicherweise die Auflistungsmethoden ändern müssen, um nützlichere Daten zu erfassen. Leistungswarnungen werden automatisch in einer Profilerstellungssitzung generiert und im Fenster **Fehlerliste** angezeigt, wenn eine Datei mit Profilerstellungsdaten in [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] geöffnet wird. Bestimmte Warnungen gelten unter Umständen nicht für die Szenarios, für die Sie sich interessieren, und einige Warnungen sind möglicherweise ungenau. Sie können Leistungswarnungen konfigurieren, um bestimmte Warnungen anzuzeigen oder auszublenden.  
  
### <a name="to-configure-profiler-performance-warnings"></a>So konfigurieren Sie Leistungswarnungen des Profilers  
  
1.  Klicken Sie im Menü **Extras** auf **Optionen**.  
  
2.  Erweitern Sie **Leistungstools**, und klicken Sie dann auf **Regeln**.  
  
3.  Aktivieren oder deaktivieren Sie das Kontrollkästchen neben der Warn-**ID** und dem Namen, um eine Warnung zu aktivieren oder zu deaktivieren.  
  
4.  Klicken Sie zum Angeben der Warnstufe einer Regel neben der Regel auf die Zelle **Aktion** und anschließend auf die Warnstufe.  
  
    -   **Deaktiviert**: Deaktiviert die Regel (entspricht dem Deaktivieren des Kontrollkästchens neben der Regel-ID).  
  
    -   **Warnung**: Zeigt die Regel als Warnung an.  
  
    -   **Fehler**: Hält die Profilerstellung an und zeigt die Regel als Fehler an.  
  
    -   **Informationen**: Zeigt die Regel lediglich als Information an.



