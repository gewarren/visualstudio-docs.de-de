---
title: IDebugBoundBreakpoint2::Enable | Microsoft-Dokumentation
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
- IDebugBoundBreakpoint2::Enable
helpviewer_keywords:
- Enable method
- IDebugBoundBreakpoint2::Enable method
ms.assetid: 1b4e3f73-c94d-4aa3-9aa8-0d8cb8a6c5ca
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d2a8fa16f340fb2ce916e56b8b353b3f9bfac2a2
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51801289"
---
# <a name="idebugboundbreakpoint2enable"></a>IDebugBoundBreakpoint2::Enable
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Aktiviert oder deaktiviert den Haltepunkt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT Enable(   
   BOOL fEnable  
);  
```  
  
```csharp  
int Enable(   
   int fEnable  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fEnable`  
 [in] Ungleich 0 festgelegt (`TRUE`) zum Aktivieren oder auf Null (`FALSE`) auf den Haltepunkt zu deaktivieren.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben. Gibt `E_BP_DELETED` , wenn der Zustand des Objekts gebundene Haltepunkt, um festgelegt ist `BPS_DELETED` (Teil der [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) Enumeration).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die Implementierung dieser Methode für eine einfache `CBoundBreakpoint` -Objekt, das macht die [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md) Schnittstelle.  
  
```  
HRESULT CBoundBreakpoint::Enable(BOOL fEnable)    
{    
   HRESULT hr;    
  
   // Verify that the bound breakpoint has not been deleted. If deleted,   
   // then return hr = E_BP_DELETED.    
   if (m_state != BPS_DELETED)    
   {    
      // Check the state of the bound breakpoint. If the breakpoint is  
      // supposed to be, but has not already been, enabled, then have the  
      // interpreter set the breakpoint.    
      if (fEnable && m_state != BPS_ENABLED)    
      {    
         hr = m_pInterp->SetBreakpoint(m_sbstrDoc, this);    
         if (hr == S_OK)    
         {    
            // Change the state of the breakpoint to BPS_ENABLED.    
            m_state = BPS_ENABLED;    
         }    
      }    
      // Check the state of the bound breakpoint. If the breakpoint is   
      // supposed to be, but has not already been, disabled, then have the   
      // interpreter remove the breakpoint.    
      else if (!fEnable && m_state != BPS_DISABLED)    
      {    
         hr = m_pInterp->RemoveBreakpoint(m_sbstrDoc, this);    
         if (hr == S_OK)    
         {    
            // Change the state of the breakpoint to BPS_DISABLED.    
            m_state = BPS_DISABLED;    
         }    
      }    
      else    
      {    
         hr = S_FALSE;    
      }    
   }    
   else    
   {    
      hr = E_BP_DELETED;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)

