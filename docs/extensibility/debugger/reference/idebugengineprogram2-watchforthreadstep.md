---
title: IDebugEngineProgram2::WatchForThreadStep | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2::WatchForThreadStep
helpviewer_keywords:
- IDebugEngineProgram2::WatchForThreadStep
ms.assetid: b70922a3-1313-409a-b3b7-50c7cd13e394
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 865cc4ad42bc030592e8b06c7ebcf3147cc8c93d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53925770"
---
# <a name="idebugengineprogram2watchforthreadstep"></a>IDebugEngineProgram2::WatchForThreadStep
Wird überwacht, ob für die Ausführung (oder beendet wird, für die Ausführung überwachen) an den angegebenen Thread ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT WatchForThreadStep(   
   IDebugProgram2* pOriginatingProgram,  
   DWORD           dwTid,  
   BOOL            fWatch,  
   DWORD           dwFrame  
);  
```  
  
```csharp  
int WatchForThreadStep(   
   IDebugProgram2 pOriginatingProgram,  
   uint           dwTid,  
   int            fWatch,  
   uint           dwFrame  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pOriginatingProgram`  
 [in] Ein [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) Objekt, das die Anwendung abgestuft wird darstellt.  
  
 `dwTid`  
 [in] Gibt den Bezeichner des Threads zu überwachen.  
  
 `fWatch`  
 [in] Ungleich 0 (`TRUE`) bedeutet, dass starten, Überwachen der Ausführung des Threads identifizierte `dwTid`ist, andernfalls 0 (null) (`FALSE`) bedeutet, dass beenden, Überwachen der Ausführung auf `dwTid`.  
  
 `dwFrame`  
 [in] Gibt einen FrameIndex, der steuert, den Typ an. In diesem Wert ist 0 (null), der Typ ist "step into" und das Programm beendet werden soll, wenn der Thread identifizierte `dwTid` ausgeführt wird. Wenn `dwFrame` ungleich NULL ist, wird der Typ ist "step over" und das Programm beendet werden soll, nur, wenn der Thread durch identifiziert `dwTid` läuft in einem Rahmen, dessen Index gleich oder höher auf dem Stapel als ist `dwFrame`.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Sitzungs-Manager (SDM) ein Programm, das identifizierte Schritte der `pOriginatingProgram` Parameter, benachrichtigt er alle anderen angefügten Programme durch Aufrufen dieser Methode.  
  
 Diese Methode ist nur auf demselben Thread schrittweise anwendbar.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)