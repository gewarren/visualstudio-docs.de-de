---
title: Neues in MSBuild 12.0 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9976a6ad-c052-4017-b848-35b5ae4a2f66
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f10fa5496795947c041482d5ae5dc7b6112da67
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49247395"
---
# <a name="what39s-new-in-msbuild-120"></a>Neues in MSBuild 12.0
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

MSBuild wird jetzt als Teil von Visual Studio nicht als Teil von .NET Framework installiert. Die aktuelle MSBuild-Versionsnummer ist 12.0. Wenn Sie MSBuild separat installieren möchten, laden Sie das Installationspaket von der [MSBuild-Downloadsite](http://go.microsoft.com/fwlink/?LinkId=309745) herunter.  
  
## <a name="changed-path"></a>Geänderter Pfad  
 MSBuild wird jetzt direkt unter *%ProgramFiles%* installiert, zum Beispiel unter C:\Programme\MSBuild\\.  
  
## <a name="changed-properties"></a>Geänderte Eigenschaften  
 Die folgenden MSBuild-Eigenschaften ändern sich aufgrund der neuen Versionsnummer:  
  
-   Die `MSBuildToolsVersion` für diese Version der Tools ist 12.0.  
  
-   Der `MSBuildToolsPath` ist jetzt %ProgramFiles%\MSBuild\12.0\bin auf 32-Bit-Betriebssystemen oder %ProgramFiles%\MSBuild\12.0\bin\amd64 auf 64-Bit-Betriebssystemen.  
  
-   Die `ToolsVersion`-Werte sind in HKLM\SOFTWARE\Microsoft\MSBuild\ToolsVersions\12.0 für 32-Bit-Betriebssysteme und in HKLM\SOFTWARE\Wow6432Node\Microsoft\MSBuild\ToolsVersions\12.0 für 64-Bit-Betriebssysteme enthalten.  
  
-   Die Eigenschaften `SDK35ToolsPath` und `SDK40ToolsPath` verweisen auf das .NET Framework SDK, das mit dieser Version von Visual Studio geliefert wird (beispielsweise 8.1A für die 4.X-Tools).  
  
## <a name="new-properties"></a>Neue Eigenschaften  
  
-   `MSBuildFrameworkToolsPath` ist eine neue Eigenschaft mit dem Wert %windir%\Microsoft.NET\Framework\v4.0.30319 auf 32-Bit-Betriebssystemen oder %windir%\Microsoft.NET\Framework64\v4.0.30319 auf 64-Bit-Betriebssystemen. Dies ist ein Ersatz für `MSBuildToolsPath`, das verwendet werden kann, um auf die .NET Framework-Tools und -Hilfsprogramme zu verweisen.  
  
-   `MSBuildToolsPath` und `MSBuildFrameworkToolsPath` haben 32-Bit-Äquivalente (`MSBuildToolsPath32` und `MSBuildFrameworkToolsPath32`), die immer auf den 32-Bit-Speicherort verweisen, unabhängig davon, ob die 32-Bit- oder 64-Bit-Version von MSBuild verwendet wird.

## <a name="see-also"></a>Siehe auch
[MSBuild](msbuild.md)


