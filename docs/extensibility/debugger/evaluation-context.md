---
title: Evaluierungskontext | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, context
ms.assetid: 008a20c7-1b27-4013-bf96-d6a3f510da02
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 58c1ac8a6b9819aee18f8be58bb392b04c22f922
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53840615"
---
# <a name="evaluation-context"></a>Evaluierungskontext
> [!IMPORTANT]
>  In Visual Studio 2015 ist diese Art der Implementierung von ausdrucksauswertungen veraltet. Informationen zum Implementieren von CLR-ausdrucksauswertungen finden Sie unter [CLR ausdrucksauswertungen](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) und [Auswertung (Beispiel) verwaltete Ausdruck](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Wenn die Debug-Engine (DE) die ausdrucksauswertung (EE), drei Argumente, die aufgerufen werden übergeben [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) den Kontext für Suchen und Auswerten von Symbolen, zu bestimmen, wie in der folgenden Tabelle gezeigt.  
  
## <a name="arguments"></a>Argumente  
  
|Argument|Beschreibung|  
|--------------|-----------------|  
|`pSymbolProvider`|Ein [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) Schnittstelle, die der Symbol-Handler (SH) gibt, verwendet werden soll, um das Symbol zu identifizieren.|  
|`pAddress`|Ein [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) Schnittstelle, die dem aktuellen Zeitpunkt der Ausführung angibt. Diese Schnittstelle sucht die Methode, die den ausgeführten Code enthält.|  
|`pBinder`|Ein [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) -Schnittstelle, die den Wert und Typ eines Symbols mit dem angegebenen Namen gefunden.|  
  
 `IDebugParsedExpression::EvaluateSync` Gibt eine [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) Schnittstelle, die den sich ergebenden Wert und seinen Typ darstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Wichtige Schnittstellen für die ausdrucksauswertung](../../extensibility/debugger/key-expression-evaluator-interfaces.md)   
 [Anzeigen von lokalen Variablen](../../extensibility/debugger/displaying-locals.md)   
 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)