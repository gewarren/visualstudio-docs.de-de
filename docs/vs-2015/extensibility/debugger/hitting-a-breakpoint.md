---
title: Erreichen eines Haltepunkts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1b2eef9b068a64f62a955cb21feb8ff445ca0fe9
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51720772"
---
# <a name="hitting-a-breakpoint"></a>Erreichen eines Haltepunkts
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Im folgenden wird den Prozess, wenn die Debug-Engine (DE) einen Haltepunkt erreicht, bei der Ausführung oder schrittweise beschrieben:  
  
## <a name="troubleshooting-a-hit-breakpoint"></a>Problembehandlung für einen Haltepunkt drücken  
  
1.  Der DE sendet eine [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) Schnittstelle als eine **EVENT_SYNC_STOP**.  
  
2.  Ruft die Sitzungs-Debug-Manager (SDM) [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) um den Haltepunkt zu erhalten, das ermittelt wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufen von Debuggerereignissen](../../extensibility/debugger/calling-debugger-events.md)

