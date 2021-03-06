---
title: IEnumDebugErrorBreakpoints2 | Microsoft-Dokumentation
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
- IEnumDebugErrorBreakpoints2
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2
ms.assetid: ffdad73d-969a-45ef-9ad1-7f5d3b814018
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 96291b76cd6b155552ee220e028a31a189c8faba
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51744630"
---
# <a name="ienumdebugerrorbreakpoints2"></a>IEnumDebugErrorBreakpoints2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Diese Schnittstelle listet Fehler Haltepunkte ein ausstehender Haltepunkt zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
IEnumDebugErrorBreakpoints2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die Debug-Engine (DE) implementiert diese Schnittstelle als Teil der Unterstützung für Haltepunkte an.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Visual Studio-Aufrufe [CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md) , rufen Sie diese Schnittstelle stellt eine Liste von Haltepunkten an, die nicht gebunden werden kann, oder [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) beim Abrufen der diese Schnittstelle, die eine Liste der Haltepunkte darstellt. wurden nicht gebunden.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IEnumDebugErrorBreakpoints2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Nächste](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-next.md)|Ruft eine angegebene Anzahl von Fehler Breakpoints in einer Enumerationsfolge ab.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-skip.md)|Überspringt eine angegebene Anzahl der Fehler von Breakpoints in einer Enumerationsfolge.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-reset.md)|Setzt eine Enumerationsfolge auf den Anfang zurück.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-clone.md)|Erstellt einen Enumerator, der den gleichen Enumerationszustand wie der aktuelle Enumerator enthält.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-getcount.md)|Ruft die Anzahl der Fehler, Haltepunkte in einen Enumerator ab.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle enthält eine Liste der [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) Schnittstellen, die beschreibt, von denen jede einen Haltepunkt nicht gebunden werden kann und warum es konnte nicht gebunden werden. Visual Studio verwendet die `IEnumDebugErrorBreakpoint2` Schnittstelle zum Aktualisieren die Haltepunkte in der IDE angezeigt.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Wichtige Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)   
 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)   
 [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)

