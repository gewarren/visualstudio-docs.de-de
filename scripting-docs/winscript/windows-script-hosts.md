---
title: Windows Script Hosts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Script Host, implementing hosts
ms.assetid: 9d5f6471-b318-40f3-be01-d9cd0b1cdd47
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 486c41c54e7935bcda27ad6bea18b3180aa0371e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49882356"
---
# <a name="windows-script-hosts"></a>Windows Script Hosts
Wenn Sie einen Microsoft Windows-Skripthost implementieren, können Sie problemlos davon ausgehen, dass eine Skript-Engine nur die [IActiveScriptSite](../winscript/reference/iactivescriptsite.md)-Schnittstelle im Kontext des Basisthreads aufruft, solange der Host Folgendes macht:  
  
- einen Basisthread auswählt (für gewöhnlich den Thread, der die Nachrichtenschleife enthält)  
  
- Die Skript-Engine im Basisthread instanziiert  
  
- Skript-Engine-Methoden nur aus dem Basisthread aufruft, es sei denn, es wurde etwas anderes erlaubt, wie z.B. bei [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) und [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md).  
  
- das Verteilungsobjekt der Skript-Engine nur vom Basisthread aus aufruft  
  
- sicherstellt, dass die Nachrichtenschleife im Basisthread ausgeführt wird, wenn ein Fensterhandle bereitgestellt wird  
  
- sicherstellt, dass Objekte im Objektmodell des Hosts nur Ereignisse des Basisthreads als Datenquelle verwenden  
  
  Diese Regeln werden automatisch von allen Host mit einem Thread befolgt. Das oben beschriebene eingeschränkte Modell ist absichtlich weit gefasst, damit der Host ein hängendes Skript abbrechen kann, indem er [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) aus einem anderen Thread aufruft (durch einen STRG + UNTRBR-Handler o.ä. initiiert), oder damit er ein Skript in einem neuen Thread mit [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md) duplizieren kann.  
  
## <a name="remarks"></a>Hinweise  
 Keine dieser Einschränkungen gilt für einen Host, der eine [IActiveScriptSite](../winscript/reference/iactivescriptsite.md)-Freethreadschnittstelle und ein Freethread-Objektmodell implementiert. Ein derartiger Host kann die [IActiveScript](../winscript/reference/iactivescript.md)-Schnittstelle aus jedem Thread verwenden und das ohne Einschränkungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Skriptschnittstellen](../winscript/windows-script-interfaces.md)