---
title: IDebugObject2::GetBackingFieldForProperty | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugObject2::GetBackingFieldForProperty
helpviewer_keywords:
- IDebugObject2::GetBackingFieldForProperty method
ms.assetid: e72c6338-5573-4fad-8075-f3ade3435424
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4ee7d6c998cb511425fa9a9e2314eeb3a7346f22
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53954020"
---
# <a name="idebugobject2getbackingfieldforproperty"></a>IDebugObject2::GetBackingFieldForProperty
Ruft ab, das Feld oder eine Variable (sofern vorhanden), die von diesem Objekt dargestellte Eigenschaft sichern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetBackingFieldForProperty(  
   IDebugObject2** ppObject  
);  
```  
  
```csharp  
int GetBackingFieldForProperty(  
   out IDebugObject2 ppObject  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppObject`  
 [out] Ein [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) Objekt, das das dahinter liegende Feld beschreibt.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt S_OK zurück. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) Objekt stellt verwalteten Code Klasseneigenschaft, d. h. eine Methode mit einer Get bzw. set-Accessor. Diese Eigenschaften erfordern in der Regel eine Variable, die den Wert, der bearbeitet werden, durch die Eigenschaft enthalten. Diese Variable wird als das dahinter liegende Feld bezeichnet. Liegt keine dahinter liegende Feld für das Objekt, dann stellen Sie sicher auf einen Nullwert zurückgibt: Einige Aufrufer kann keine Achten Sie darauf, den Rückgabewert, aber sehen Sie sich stattdessen um festzustellen, ob ein null-Wert, in zurückgegeben wurde `ppObject`.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)