---
title: GetWinFXPath-Aufgabe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- getting the directory of the current .NET Framework runtime [WPF MSBuild]
- GetWinFXPath task [WPF MSBuild], parameters
- GetWinFXPath task [WPF MSBuild]
- obtaining the path to the current .NET Framework runtime [WPF MSBuild]
ms.assetid: b1dfb467-f3d3-47f3-83ef-af7b0e33a772
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ace14a3238142be4d703b4d2e0fa457288b00458
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49852829"
---
# <a name="getwinfxpath-task"></a>GetWinFXPath-Aufgabe
Der <xref:Microsoft.Build.Tasks.Windows.GetWinFXPath>-Task gibt das Verzeichnis der aktuellen [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)]-Runtime zurück.  
  
## <a name="task-parameters"></a>Aufgabenparameter  
  
| Parameter | Beschreibung  |
|-------------------| - |
| `WinFXPath` | Optionaler **String**-Ausgabeparameter.<br /><br /> Gibt den tatsächlichen Pfad zur [!INCLUDE[TLA2#tla_winfx](../msbuild/includes/tla2sharptla_winfx_md.md)]-Runtime an. |
| `WinFXNativePath` | Erforderlicher **String**-Parameter.<br /><br /> Gibt den Pfad zur nativen [!INCLUDE[TLA2#tla_titlewinfx](../msbuild/includes/tla2sharptla_titlewinfx_md.md)]-Runtime an. |
| `WinFXWowPath` | Erforderlicher **String**-Parameter.<br /><br /> Gibt den Pfad zu den [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)]-Assemblys im 32-Bit-**Windows on Windows**-Modul auf 64-Bit-Systemen an. |
  
## <a name="remarks"></a>Hinweise  
 Wenn der <xref:Microsoft.Build.Tasks.Windows.GetWinFXPath>-Task auf einem 64-Bit-Prozessor ausgeführt wird, wird der **WinFXPath**-Parametersatz auf den Pfad festgelegt, der im **WinFXWowPath**-Parameter gespeichert ist. Andernfalls wird der **WinFXPath**-Parameter auf den Pfad festgelegt, der im **WinFXNativePath**-Parameter gespeichert ist.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die **GetWinFXPath**-Aufgabe verwenden, um den nativen Pfad zur [!INCLUDE[TLA2#tla_titlewinfx](../msbuild/includes/tla2sharptla_titlewinfx_md.md)]-Runtime zu ermitteln.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.GetWinFXPath"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="GetWinFXPathTask">  
    <GetWinFXPath  
      WinFXNativePath="c:\WinFXNative"   
      WinFXWowPath="c:\WinFXWowNative" />  
  </Target>  
  <Import Project="$(MSBuildBinPath)\Microsoft.WinFX.targets" />  
</Project>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [WPF-MSBuild-Referenz](../msbuild/wpf-msbuild-reference.md)   
 [Referenz zu MSBuild-Tasks](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild-Referenz](../msbuild/msbuild-reference.md)   
 [Referenz zu MSBuild-Tasks](../msbuild/msbuild-task-reference.md)   
 [Erstellen einer WPF-Anwendung (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)