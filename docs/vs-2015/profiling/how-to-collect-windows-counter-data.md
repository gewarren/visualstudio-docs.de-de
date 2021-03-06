---
title: 'Vorgehensweise: Sammeln von Windows-Indikatordaten | Microsoft-Dokumentation'
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
- vs.performance.property.syscounter
- vs.performance.property.wincounter
helpviewer_keywords:
- windows counters
- performance tools, using windows counters
- profiling tools, using windows counters
ms.assetid: db4fbac2-bea5-4558-aa8b-160fcccf4b33
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 030a36f2f09465b29faf23b1fc05ad13f4a01326
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51770495"
---
# <a name="how-to-collect-windows-counter-data"></a>Gewusst wie: Sammeln von Windows-Indikatordaten
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows-Indikatoren sind Systemleistungsindikatoren, die während der Profilerstellung in festgelegten Intervallen gesammelt werden können In der Markierungsansicht des Berichts „Profilerstellungstools“, wird eine Zeile für jedes Sammlungsintervall als **AutoMark** bezeichnet. Die Zeile enthält Spalten, die die Leistungsindikatorwerte in diesem Intervall beschreibt. Klicken Sie zum Beschränken der Analyse auf eine Zeitraum zwischen zwei bestimmten Markierungen auf die Markierungen, anschließend auf die rechte Maustaste, und wählen Sie dann im Kontextmenü **Filtern nach** ->  **Markierungen** aus  
  
 **Anforderungen**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
> [!NOTE]
>  Verbesserte Sicherheitsfunktionen in Windows 8 und Windows Server 2012 erforderten tiefgreifende Änderungen bei der Datenerfassung des Visual Studio-Profilers auf diesen Plattformen. Außerdem benötigen Windows Store-Apps neue Erfassungsmethoden. Siehe [Profilerstellungstools für Windows 8- und Windows Server 2012-Anwendungen](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
### <a name="to-collect-windows-counter-data"></a>So sammeln Sie Windows-Indikatordaten  
  
1.  Klicken Sie im Leistungs-Explorer mit der rechten Maustaste auf die Sitzung, für die Sie Windows-Indikatoren konfigurieren möchten, und wählen Sie **Eigenschaften** aus.  
  
2.  Klicken Sie in den **Eigenschaftenseiten** auf **Windows-Indikatoren**.  
  
3.  Wählen Sie das Kontrollkästchen **Windows-Indikatoren auflisten** aus.  
  
4.  Geben Sie im Textfeld **Sammlungsintervall (ms)** ein Zeitintervall ein.  
  
5.  Wählen Sie eine Kategorie aus der Dropdownliste **Indikatorkategorie** aus.  
  
6.  Wählen Sie eine Instanz aus der Dropdownliste **Instanz** aus.  
  
7.  Wählen Sie die Indikatoren aus, die Sie bei der Profilerstellung Ihrer Anwendung verwenden möchten.  
  
8.  Klicken Sie auf **Übernehmen**.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren von Leistungssitzungen](../profiling/configuring-performance-sessions.md)   
 [Eigenschaften von Leistungssitzungen](../profiling/performance-session-properties.md)   
 [CPU- und Windows-Indikatoren](../profiling/cpu-and-windows-counters.md)



