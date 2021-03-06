---
title: ThreadOn und ThreadOff | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cd5a695-0a14-484a-8952-ed47e13d8e92
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4e908da955258bfef5d66187bc974b6e051a48ad
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51789167"
---
# <a name="threadon-and-threadoff"></a>ThreadOn und ThreadOff
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die VSPerfCmd.exe-Unterbefehle **ThreadOff** und **ThreadOn** sind nur in Befehlszeilensitzungen zur Profilerstellung verfügbar, in denen die Instrumentierungmethode verwendet wird. **ThreadOff** und **ThreadOn** halten die Profilerstellung für den angegebenen Thread an oder setzen diese fort. **ThreadOff** hält die Profilerstellung für den Thread an, und **ThreadOn** setzt diese fort.  
  
 In den meisten Fällen geben Sie **ThreadOn** oder **ThreadOff** als einzige Option in einer VSPerfCmd.exe-Befehlszeile an. Sie können aber auch mit den Unterbefehlen **GlobalOn**, **GlobalOff**, **ProcessOn** und **ProcessOff** kombiniert werden.  
  
 Die Unterbefehle **ThreadOn** und **ThreadOff** interagieren mit den Unterbefehlen **GlobalOn** und **GlobalOff**, die die Datensammlung für alle Prozesse in einer Befehlszeilen-Profilerstellungssitzung steuern. Sie interagieren außerdem mit den Unterbefehlen **ProcessOn** und **ProcessOff**, die die Datensammlung für einen angegebenen Thread steuern.  
  
 Die Unterbefehle **ThreadOff** und **ThreadOn** haben außerdem Auswirkungen auf die Start/Stop-Zähler von Threads, die von den Profiler-API-Funktionen bearbeitet wird.  
  
- **ThreadOff** legt die globale Start/Stop-Zähler der Threads sofort auf 0 (null) fest und hält die Profilerstellung daher an.  
  
- **ThreadOn** legt die globale Start/Stop-Zähler sofort auf 1 fest und setzt die Profilerstellung daher fort.  
  
  Weitere Informationen finden Sie unter [APIs für Profilerstellungstools](../profiling/profiling-tools-apis.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
VSPerfCmd.exe /{ThreadOff|ThreadOn}:TID [Options]  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `TID`  
 Der ganzzahlige Bezeichner des Threads zum Starten oder Beenden.  
  
## <a name="valid-options"></a>Gültige Optionen  
 **ThreadOn** und **ThreadOff** können in Befehlszeilen angegeben werden, die auch die folgenden Unterbefehle enthalten.  
  
 **Start:** `Method`  
 Initialisiert die Profilerstellungssitzung in der Befehlszeile und legt die angegebene Profilerstellungsmethode fest  
  
 **GlobalOff**|**GlobalOn**  
 Beendet oder startet die Profilerstellung für alle Prozesse in einer Befehlszeilen-Profilerstellungssitzung  
  
 {**ProcessOff**|**ProcessOn**}**:**`TID`  
 Beendet oder startet die Profilerstellung für den angegebenen Prozess  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der Unterbefehl **ThreadOff** verwendet, um das Erfassen der Profilerstellungsdaten anzuhalten, damit nur Daten zum Starten von Anwendungen erfasst werden.  
  
```  
; Initialize the profiler.  
VSPerfCmd.exe /Start:Trace /Output:Instrument.vsp   
; Start the instrumented application.  
; Stop profiling the thread after startup.  
VSPerfCmd.exe /ThreadOff:12345  
; Shut down the target application.  
; Close the profiler.  
VSPerfCmd /Shutdown  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilerstellung für eigenständige Anwendungen](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilerstellung für ASP.NET-Webanwendungen](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Erstellen von Dienstprofilen](../profiling/command-line-profiling-of-services.md)



