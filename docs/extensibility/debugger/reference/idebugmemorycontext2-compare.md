---
title: IDebugMemoryContext2::Compare | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMemoryContext2::Compare
helpviewer_keywords:
- IDebugMemoryContext2::Compare method
- Compare method
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 86ba475aa9eab6b6cd878f9051e5851611955cf1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53851176"
---
# <a name="idebugmemorycontext2compare"></a>IDebugMemoryContext2::Compare
Vergleicht den Speicherkontext, der jeder Kontext, in dem angegebenen Array in die Art und Weise, angegeben durch Vergleichen-Flags, die einen Index des ersten Kontext, der mit übereinstimmt zurückgegeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Compare(   
   CONTEXT_COMPARE        compare,  
   IDebugMemoryContext2** rgpMemoryContextSet,  
   DWORD                  dwMemoryContextSetLen,  
   DWORD*                 pdwMemoryContext  
);  
```  
  
```csharp  
int Compare(  
   enum_CONTEXT_COMPARE   compare,   
   IDebugMemoryContext2[] rgpMemoryContextSet,   
   uint                   dwMemoryContextSetLen,   
   out uint               pdwMemoryContext  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `compare`  
 [in] Ein Wert aus der [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md) Enumeration, der den Typ des Vergleichs bestimmt.  
  
 `rgpMemoryContextSet`  
 [in] Ein Array von Verweisen auf die [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) Objekte mit verglichen werden soll.  
  
 `dwMemoryContextSetLen`  
 [in] Die Anzahl von Kontexten, in der `rgpMemoryContextSet` Array.  
  
 `pdwMemoryContext`  
 [out] Gibt den Index des ersten Arbeitsspeicher Kontexts, die den Vergleich zu erfüllen.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben. Gibt `E_COMPARE_CANNOT_COMPARE` , wenn die beiden Kontexte nicht verglichen werden können.  
  
## <a name="remarks"></a>Hinweise  
 Eine Debug-Engine (DE) muss nicht alle Typen der Vergleiche unterstützt, aber es muss mindestens unterstützen `CONTEXT_EQUAL`, `CONTEXT_LESS_THAN`, `CONTEXT_GREATER_THAN` und `CONTEXT_SAME_SCOPE`.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)