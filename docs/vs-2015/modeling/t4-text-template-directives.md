---
title: T4-Textvorlagenanweisungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, import directive
- text templates, include directive
- text templates, assembly directive
- text templates, output directive
- text templates, directives
- text templates, template directive
ms.assetid: 6898ee02-ebb2-4635-a4e9-350774c13cf2
caps.latest.revision: 83
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: e079b21c3a85f883351808b8defda6d0d68619f7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47515092"
---
# <a name="t4-text-template-directives"></a>T4-Textvorlagenanweisungen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [T4-Textvorlagenanweisungen](https://docs.microsoft.com/visualstudio/modeling/t4-text-template-directives).  
  
Durch Direktiven werden Anweisungen für die Textvorlagen-Transformations-Enginebereitgestellt.  
  
 Die Syntax von Direktiven lautet wie folgt:  
  
```  
<#@ DirectiveName [AttributeName = "AttributeValue"] ... #>  
```  
  
 Alle Attributwerte müssen in doppelte Anführungszeichen eingeschlossen werden. Wenn der Wert selbst Anführungszeichen enthält, müssen diese mit dem Escapezeichen "\" versehen werden.  
  
 Direktiven sind in der Regel die ersten Elemente in einer Vorlagendatei oder einer eingeschlossenen Datei. Platzieren Sie sie nicht in einem Codeblock `<#...#>` und nicht nach einem Klassenfunktionsblock `<#+...#>`.  
  
 [T4-Vorlagenanweisung](../modeling/t4-template-directive.md)  
 ```  
<#@ template [language="VB"] [hostspecific="true|TrueFromBase"] [debug="true"] [inherits="templateBaseClass"] [culture="code"] [compilerOptions="options"] [visibility="internal"] [linePragmas="false"] #>  
```  
  
 [T4-Parameter-Direktive](../modeling/t4-parameter-directive.md)  
 ```  
<#@ parameter type="Full.TypeName" name="ParameterName" #>  
```  
  
 [T4 Output-Direktive](../modeling/t4-output-directive.md)  
 ```  
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>  
```  
  
 [T4-Assemblydirektive](../modeling/t4-assembly-directive.md)  
 ```  
<#@ assembly name="[assembly strong name|assembly file name]" #>  
```  
  
 [T4-Import-Anweisung](../modeling/t4-import-directive.md)  
 ```  
<#@ import namespace="namespace" #>  
```  
  
 [T4-Include-Direktive](../modeling/t4-include-directive.md)  
 ```  
<#@ include file="filePath" #>  
```  
  
 [T4 CleanUpBehavior-Anweisung](../modeling/t4-cleanupbehavior-directive.md)  
 ```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 Darüber hinaus können Sie eigene Anweisungen erstellen. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten T4 Text Vorlage Richtlinie Prozessoren](../modeling/creating-custom-t4-text-template-directive-processors.md). Wenn Sie mithilfe des Visualisierungs- und Modellierungs-SDKs eine domänenspezifische Sprache (DSL) erstellen, wird ein Direktivenprozessor als Teil der DSL generiert.


