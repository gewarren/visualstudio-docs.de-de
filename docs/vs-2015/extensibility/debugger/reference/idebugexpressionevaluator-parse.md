---
title: IDebugExpressionEvaluator::Parse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugExpressionEvaluator::Parse
helpviewer_keywords:
- IDebugExpressionEvaluator::Parse method
ms.assetid: e6e31b3a-63a7-4293-bcda-267eb78dffb6
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4d772ce5eda094b80a520d8fba4bd41f0b90d17
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51804520"
---
# <a name="idebugexpressionevaluatorparse"></a>IDebugExpressionEvaluator::Parse
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Diese Methode konvertiert eine Ausdruckszeichenfolge in einen analysierten Ausdruck.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT Parse(   
   LPCOLESTR                upstrExpression,  
   PARSEFLAGS               dwFlags,  
   UINT                     nRadix,  
   BSTR*                    pbstrError,  
   UINT*                    pichError,  
   IDebugParsedExpression** ppParsedExpression  
);  
```  
  
```csharp  
int Parse(  
   string                     upstrExpression,   
   enum_PARSEFLAGS            dwFlags,   
   uint                       nRadix,   
   out string                 pbstrError,   
   out uint                   pichError,   
   out IDebugParsedExpression ppParsedExpression  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `upstrExpression`  
 [in] Die Ausdruckszeichenfolge analysiert werden.  
  
 `dwFlags`  
 [in] Eine Auflistung von [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) Konstanten, die bestimmen, wie der Ausdruck ist, die analysiert werden.  
  
 `nRadix`  
 [in] Die Basis, die verwendet werden, um alle numerischen Informationen interpretieren.  
  
 `pbstrError`  
 [out] Gibt den Fehler als Klartext zurück.  
  
 `pichError`  
 [out] Gibt die Zeichenposition des Starts des Fehlers in der Ausdruckszeichenfolge zurück.  
  
 `ppParsedExpression`  
 [out] Gibt den analysierten Ausdruck in einem [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode erzeugt einen analysierten Ausdruck, der nicht auf einen tatsächlichen Wert. Ein analysierten Ausdruck kann ausgewertet werden, d. h. in einen Wert konvertiert.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)   
 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)

