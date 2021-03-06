---
title: Befehl „Module auflisten“ | Microsoft-Dokumentation
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
- debug.listmodules
helpviewer_keywords:
- Debug.ListModules command
- ListModules command
- list modules command
ms.assetid: 3cb73774-6ac0-43b2-b781-75ed47175bfd
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 97a269fd5ed0e30e648e2dade210ab0238c8d759
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49246692"
---
# <a name="list-modules-command"></a>Befehl "Module auflisten"
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Listet die Module für den aktuellen Prozess auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
Debug.ListModules [/Address:yes|no] [/Name:yes|no] [/Order:yes|no]  
[/Path:yes|no] [/Process:yes|no] [/SymbolFile:yes|no]  
[/SymbolStatus:yes|no] [/Timestamp:yes|no] [/Version:yes|no]  
```  
  
#### <a name="parameters"></a>Parameter  
 /Address:`yes|no`  
 Dies ist optional. Gibt an, ob die Speicheradressen der Module angezeigt werden sollen. Der Standardwert ist `yes`sein.  
  
 /Name:`yes|no`  
 Dies ist optional. Gibt an, ob die Namen der Module angezeigt werden sollen. Der Standardwert ist `yes`sein.  
  
 /Order:`yes|no`  
 Dies ist optional. Gibt an, ob die Reihenfolge der Module angezeigt werden soll. Der Standardwert ist `no`sein.  
  
 /Path:`yes|no`  
 Dies ist optional. Gibt an, ob die Pfade zu den Modulen angezeigt werden sollen. Der Standardwert ist `yes`sein.  
  
 /Process:`yes|no`  
 Dies ist optional. Gibt an, ob die Prozesse der Module angezeigt werden sollen. Der Standardwert ist `no`sein.  
  
 /SymbolFile:`yes|no`  
 Dies ist optional. Gibt an, ob die Symboldateien der Module angezeigt werden sollen. Der Standardwert ist `no`sein.  
  
 /SymbolStatus:`yes|no`  
 Dies ist optional. Gibt an, ob die Symbolstatus der Module angezeigt werden sollen. Der Standardwert ist `yes`sein.  
  
 /Timestamp:`yes|no`  
 Dies ist optional. Gibt an, ob der Zeitstempel der Module angezeigt werden soll. Der Standardwert ist `no`sein.  
  
 /Version:`yes|no`  
 Dies ist optional. Gibt an, ob die Versionen der Module angezeigt werden sollen. Der Standardwert ist `no`sein.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden die Modulnamen, -adressen und -zeitstempel für den aktuellen Prozess aufgeführt.  
  
```  
Debug.ListModules /Address:yes /Name:yes /Order:no /Path:no /Process:no /SymbolFile:no /SymbolStatus:no /Timestamp:yes /Version:no  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Studio-Befehle](../../ide/reference/visual-studio-commands.md)   
 [Befehlsfenster](../../ide/reference/command-window.md)   
 [Gewusst wie: Verwenden des Modulfensters](../../debugger/how-to-use-the-modules-window.md)



