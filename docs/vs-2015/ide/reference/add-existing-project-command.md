---
title: Befehl „Vorhandenes Projekt hinzufügen“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- file.addexistingproject
helpviewer_keywords:
- Add Existing Project command
- File.AddExistingProject
ms.assetid: 71cf3e31-c76b-405b-ad6a-1b1bc654bd40
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c881f32594ee6327dfba9792fa83bd2d092efcf9
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49267643"
---
# <a name="add-existing-project-command"></a>Befehl "Vorhandenes Projekt hinzufügen"
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Fügt der aktuellen Projektmappe ein vorhandenes Projekt hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```  
File.AddExistingProject filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Dies ist optional. Der vollständige Pfad und der Projektname des Projekts mit Erweiterung, die der Projektmappe hinzugefügt werden sollen.  
  
 Wenn das `filename`-Argument Leerzeichen enthält, muss es in Anführungszeichen stehen.  
  
 Wenn kein Dateiname angegeben ist, öffnet der Befehl das Dialogfeld „Datei“, damit der Benutzer ein Projekt auswählen kann.  
  
## <a name="remarks"></a>Hinweise  
 Bei der automatischen Vervollständigung wird während der Eingabe versucht, den richtigen Pfad und Dateinamen zu finden.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]-Projekt, TestProject1, der aktuellen Projektmappe hinzugefügt.  
  
```  
>File.AddExistingProject "c:\visual studio projects\TestProject1.vbproj"  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Studio-Befehle](../../ide/reference/visual-studio-commands.md)   
 [Befehlsfenster](../../ide/reference/command-window.md)   
 [Such-/Befehlsfeld](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



