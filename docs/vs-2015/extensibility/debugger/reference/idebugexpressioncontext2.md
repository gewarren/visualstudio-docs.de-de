---
title: IDebugExpressionContext2 | Microsoft-Dokumentation
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
- IDebugExpressionContext2
helpviewer_keywords:
- IDebugExpressionContext2 interface
ms.assetid: 577fdaae-4b2d-4112-9839-ab899535fa6f
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c6cfa4daf038eef4d96f71ab650b621afad5c07
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51739017"
---
# <a name="idebugexpressioncontext2"></a>IDebugExpressionContext2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Diese Schnittstelle stellt einen Kontext für ausdrucksauswertung dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugExpressionContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die Debug-Engine (DE) implementiert diese Schnittstelle, um einen Kontext darstellen, in dem ein Ausdruck ausgewertet werden kann.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Ein Aufruf von [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) gibt zurück, die diese Schnittstelle. Diese Schnittstelle ist zugegriffen werden kann, nur, wenn das derzeit debuggte Programm angehalten wurde und ein Stapelrahmen verfügbar ist.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IDebugExpressionContext2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugexpressioncontext2-getname.md)|Ruft den Namen des dem Auswertungskontext ab.|  
|[ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)|Analysiert einen textbasierter Ausdruck für die Evaluierung.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Evaluierungskontext kann als Bereich für die Durchführung der Auswertung des Ausdrucks betrachtet werden.  
  
 Wenn ein Programm angehalten wurde, erhält der sitzungsbasierter Debug-Manager (SDM) einen Stapelrahmen aus dem DE mit einem Aufruf von [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md). Klicken Sie dann aufruft, das SDM [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) zum Abrufen der `IDebugExpressionContext2` Schnittstelle. Darauf folgt ein Aufruf von [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) zum Erstellen einer [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) -Schnittstelle, die den analysierten Ausdruck zur Auswertung bereiter darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Wichtige Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)   
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)

