---
title: IDebugProgramPublisher2::UnpublishProgram | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramPublisher2::UnpublishProgram
helpviewer_keywords:
- IDebugProgramPublisher2::UnpublishProgram
ms.assetid: 627e7d38-b2ac-4873-9a40-37ff7f47cd1d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ee3d294fe63c1ed4e3076b0d495646552f17e199
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53884605"
---
# <a name="idebugprogrampublisher2unpublishprogram"></a>IDebugProgramPublisher2::UnpublishProgram
Wird ein Programm nicht verfügbar, die debuggt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT UnpublishProgram(  
   IUnknown* pDebuggeeInterface  
);  
```  
  
```csharp  
int UnpublishProgram(  
   object pDebuggeeInterface  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pDebuggeeInterface`  
 [in] Ein `IUnknown` Schnittstelle, um die Anwendung. Dies ist der gleiche Wert angegeben die [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md) Methode und eindeutig identifiziert die Anwendung entfernt wird (d. h., er dient als ein Cookie).  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Um ein Programm auf die Debug-Engines und sitzungsbasierter Debug-Manager verfügbar zu machen, verwenden Sie die [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md) Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md)