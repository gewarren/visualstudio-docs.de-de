---
title: IDebugDisassemblyStream2::GetCodeLocationId | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
helpviewer_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
ms.assetid: 567adfb8-2f54-499a-a027-e4ecb82277ef
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 52423c671bb27de0c5b03a302dc757cad7a3aaa1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53891517"
---
# <a name="idebugdisassemblystream2getcodelocationid"></a>IDebugDisassemblyStream2::GetCodeLocationId
Gibt einen Code-Speicherort-Bezeichner für einen bestimmten Code-Kontext zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCodeLocationId(   
   IDebugCodeContext2* pCodeContext,  
   UINT64*             puCodeLocationId  
);  
```  
  
```csharp  
int GetCodeLocationId(   
   IDebugCodeContext2 pCodeContext,  
   out ulong          puCodeLocationId  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pCodeContext`  
 [in] Ein [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) Objekt, das auf einen Bezeichner konvertiert werden.  
  
 `puCodeLocationId`  
 [out] Gibt den Code-Ort-Bezeichner. Siehe Hinweise.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben. Gibt `E_CODE_CONTEXT_OUT_OF_SCOPE` , wenn der Codekontext gültig ist, aber außerhalb des Bereichs.  
  
## <a name="remarks"></a>Hinweise  
 Der Standortbezeichner Code bezieht sich auf die Debug-Engine (DE) unterstützt die Disassembly. Diese Standortbezeichner wird intern vom die DE verwendet, um Positionen im Code zu verfolgen und ist in der Regel eine Adresse oder einen Offset irgendeiner Art. Die einzige Voraussetzung ist, sofern der Codekontext von einem Speicherort, die kleiner als der Codekontext von einem anderen Speicherort ist dann der entsprechende Code geographical Location Identifier des ersten Codekontext auch der Bezeichner des zweiten Code Kontexts Speicherort muss niedriger als sein.  
  
 Rufen Sie zum Abrufen der Codekontext geographical Location Identifier ein Code die [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md) Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Idebugdocumentcontext2 angegeben](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)