---
title: IDebugExpressionEvaluator2::GetService | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugExpressionEvaluator2::GetService
- GetService
ms.assetid: f8988a9e-9d18-42af-84a7-55f41e9adf63
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a8a2eed46be960fbc4efa46075591d6a610acd1e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53922337"
---
# <a name="idebugexpressionevaluator2getservice"></a>IDebugExpressionEvaluator2::GetService
Ruft ein Dienstobjekt unter Berücksichtigung den eindeutigen Bezeichner ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetService (  
   GUID        uid,  
   IUnknown ** ppService  
);  
```  
  
```csharp  
int GetService (  
   Guid       uid,  
   out object ppService  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `uid`  
 [in] Eindeutiger Bezeichner des abzurufenden Dienstes.  
  
 `ppService`  
 [out] Gibt ein Objekt, das den Dienst darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Dies kann von einem Drittanbieter-ausdrucksauswertung zum Abrufen von Diensten aus einem anderen ausdrucksauswertung genutzt werden. Beispielsweise kann diese Methode zum Abrufen der Schnittstelle für den schnellansichtsdienst aus der Standard-ausdrucksauswertung verwendet werden. Drittanbieter--ausdruckauswertung ist es unwahrscheinlich, dass diese Schnittstelle implementieren müssen.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)