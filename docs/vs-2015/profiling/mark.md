---
title: Mark | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d72cef3-bb09-4bbb-8864-6ea0ab623ff9
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff40ac5db35927fad0fe28fe3c86c5411b5f5255
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51769084"
---
# <a name="mark"></a>Mark
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Über die „VSPerfCmd.exe“-Option **Mark** (Markieren) werden die angegeben Informationen in die Profilerstellungs-Datendatei eingefügt. Die Option „Mark“ kann in einem separaten VSPerfReport-Bericht oder in der Mark-Berichtsansicht der Benutzeroberfläche für die Profilerstellung aufgeführt werden. **Mark** kann verwendet werden, um Start- und Endpunkte in Berichten sowie Filter für die Ansicht anzugeben.  
  
 Die Option **Mark** (Markieren) muss als einzige Option in der Befehlszeile angegeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
VSPerfCmd.exe /Mark:MarkID,[MarkName]  
```  
  
#### <a name="parameters"></a>Parameter  
 `MarkID`  
 Eine benutzerdefinierte Ganzzahl, die als Mark-ID in den Ansichten des Profilers und des Berichts aufgeführt ist. `MarkID` muss nicht eindeutig sein.  
  
 `MarkName`  
 (Optional) Eine benutzerdefinierte Zeichenfolge, die als der Markierungsname in den Ansichten des Profilers und des Berichts aufgeführt ist. Wenn `MarkName` nicht angegeben ist, ist das Feld für den Markierungsnamen in der Markierungsauflistung leer. Setzen Sie Zeichenfolgen, die Leerräume und Schrägstriche enthalten, in Anführungszeichen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird ein Mark mit der ID „123“ und dem Markierungsnamen „TestMark“ eingefügt.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
VSPerfCmd.exe /Mark:123,TestMark  
```  
  
## <a name="see-also"></a>Siehe auch  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilerstellung für eigenständige Anwendungen](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilerstellung für ASP.NET-Webanwendungen](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Erstellen von Dienstprofilen](../profiling/command-line-profiling-of-services.md)



