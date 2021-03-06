---
title: GetFrameworkPath-Aufgabe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkPath task [MSBuild]
- MSBuild, GetFrameworkPath task
ms.assetid: 5b7bcdd7-d4a0-442d-af29-8aadb3b10598
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dcad656c058fffaf3f075b195cb1f105079a8e5d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49248598"
---
# <a name="getframeworkpath-task"></a>GetFrameworkPath-Aufgabe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Ruft den Pfad zur [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]-Assembly ab  
  
## <a name="task-parameters"></a>Aufgabenparameter  
 In der folgenden Tabelle werden die Parameter der `GetFrameworkPath`-Aufgabe beschrieben.  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`FrameworkVersion11Path`|Optionaler `String`-Ausgabeparameter.<br /><br /> Enthält den Pfad zu den Assemblys der Framework-Version 1.1, sofern vorhanden. Andernfalls wird `null` zurückgegeben.|  
|`FrameworkVersion20Path`|Optionaler `String`-Ausgabeparameter.<br /><br /> Enthält den Pfad zu den Assemblys der Framework-Version 2.0, sofern vorhanden. Andernfalls wird `null` zurückgegeben.|  
|`FrameworkVersion30Path`|Optionaler `String`-Ausgabeparameter.<br /><br /> Enthält den Pfad zu den Assemblys der Framework-Version 3.0, sofern vorhanden. Andernfalls wird `null` zurückgegeben.|  
|`FrameworkVersion35Path`|Optionaler `String`-Ausgabeparameter.<br /><br /> Enthält den Pfad zu den Assemblys der Framework-Version 3.5, sofern vorhanden. Andernfalls wird `null` zurückgegeben.|  
|`FrameworkVersion40Path`|Optionaler `String`-Ausgabeparameter.<br /><br /> Enthält den Pfad zu den Assemblys der Framework-Version 4.0, sofern vorhanden. Andernfalls wird `null` zurückgegeben.|  
|`Path`|Optionaler `String`-Ausgabeparameter.<br /><br /> Enthält den Pfad zu den neuesten Frameworkassemblys, sofern diese verfügbar sind. Andernfalls wird `null` zurückgegeben.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn mehrere Versionen von [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] installiert sind, gibt diese Aufgabe die Version zurück, in der [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] ausgeführt werden soll.  
  
 Zusätzlich zu den oben aufgeführten Parametern erbt diese Aufgabe Parameter von der <xref:Microsoft.Build.Tasks.TaskExtension>-Klasse, die selbst von der <xref:Microsoft.Build.Utilities.Task>-Klasse erbt. Eine Liste mit diesen zusätzlichen Parametern und ihren Beschreibungen finden Sie unter [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird mit der Aufgabe `GetFrameworkPath` der Pfad zu [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] in der `FrameworkPath`-Eigenschaft gespeichert.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="FrameworkPath" />  
        </GetFrameworkPath>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Tasks (Aufgaben)](../msbuild/msbuild-tasks.md)   
 [Aufgabenreferenz](../msbuild/msbuild-task-reference.md)



