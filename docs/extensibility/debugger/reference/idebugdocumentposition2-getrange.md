---
title: IDebugDocumentPosition2::GetRange | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDocumentPosition2::GetRange
helpviewer_keywords:
- IDebugDocumentPosition2::GetRange
ms.assetid: 91a06ee7-253a-4215-be22-04bf57305aa8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 36794360c84b46b623a70526c38f388530254792
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53895635"
---
# <a name="idebugdocumentposition2getrange"></a>IDebugDocumentPosition2::GetRange
Ruft den Bereich für dieses Dokumentposition ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```csharp  
int GetRange(   
   TEXT_POSITION[] pBegPosition,  
   TEXT_POSITION[] pEndPosition  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pBegPosition`  
 [in, out] Ein [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) -Struktur, die mit die Position gefüllt wird. Legen Sie dieses Argument auf einen null-Wert, wenn diese Informationen nicht benötigt wird.  
  
 `pEndPosition`  
 [in, out] Ein [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) -Struktur, die mit der Endposition gefüllt wird. Legen Sie dieses Argument auf einen null-Wert, wenn diese Informationen nicht benötigt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 In einen Dokumentposition für einen Positionshaltepunkt angegebene Bereich wird nun für eine Anweisung zu suchen, die tatsächlich beitragen von Code von der Debug-Engine (DE) verwendet. Beachten Sie z. B. folgenden Code:  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 Zeile 5 unterstützt kein Code vorhanden, das derzeit debuggte Programm. Wenn der Debugger, der den Haltepunkt in Zeile 5 festlegt will die DE, um eine bestimmte Menge für die erste Zeile vorwärts zu suchen, die Code beteiligt sind, würde der Debugger einen Bereich angeben, der weitere Kandidat Zeilen enthält, in denen ein Haltepunkt ordnungsgemäß eingefügt werden kann. Die DE würde dann vorwärts durch diese Zeilen suchen, bis er eine Zeile gefunden, die einen Haltepunkt akzeptieren konnte.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)