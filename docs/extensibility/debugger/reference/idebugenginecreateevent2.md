---
title: IDebugEngineCreateEvent2 | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEngineCreateEvent2
helpviewer_keywords:
- IDebugEngineCreateEvent2 interface
ms.assetid: 37c0a841-1c8d-4802-a990-36b54bca3ef7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: accf18a72969d160d9b4469d9f0e6f4d843a5c70
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53963161"
---
# <a name="idebugenginecreateevent2"></a>IDebugEngineCreateEvent2
Die Debug-Engine (DE) sendet diese Schnittstelle für die Sitzung Debug-Manager (SDM), wenn eine Instanz des DE erstellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugEngineCreateEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die DE implementiert diese Schnittstelle als Teil der normalen Vorgänge. Der [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) Schnittstelle muss auf dasselbe Objekt wie diese Schnittstelle implementiert werden (das SDM verwendet die `QueryInterface` Methode, um Zugriff auf die `IDebugEvent2` Schnittstelle).  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Die DE erstellt und sendet dieses Ereignisobjekt, bei der DE instanziiert wurde. Das Ereignis gesendet wird, mithilfe der [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) Callback-Funktion, die durch die SDM bereitgestellt wird, wenn diese an die zu debuggende Programm wird angefügt.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IDebugEngineCreateEvent2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetEngine](../../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)|Ruft das Objekt, das das neu erstellte Debugmodul (DE) darstellt.|  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)