---
title: ExtendedDebugPropertyInfo-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ExtendedDebugPropertyInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- ExtendedDebugPropertyInfo structure
ms.assetid: f2cf6477-454b-4d13-95da-ae4c90daa175
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 62b9f3b5877f7919a57e9747355276e438240796
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49888904"
---
# <a name="extendeddebugpropertyinfo-structure"></a>ExtendedDebugPropertyInfo-Struktur
Erweitert die `DebugPropertyInfo` Struktur mit zusätzliche Member für die erweiterte Eigenschaft charakterisieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct ExtendedDebugPropertyInfo{  
   DBGPROP_INFO_FLAGS  dwValidFields;  
   LPOLESTR  bstrName;  
   LPOLESTR  bstrType;  
   LPOLESTR  bstrValue;  
   LPOLESTR  bstrFullName;  
   DBGPROP_ATTRIB_FLAGS  dwAttrib;  
   IDebugProperty*  pDebugProp;  
   DWORD  nDISPID;  
   DWORD  nType;  
   VARIANT  varValue;  
   ILockBytes*  plbValue;  
   IDebugExtendedProperty*  pDebugExtProp;  
};  
```  
  
## <a name="members"></a>Member  
 `dwValidFields`  
 Ein Aufzählungsdatentyp verwendet, um anzugeben, welche Felder initialisiert werden.  
  
 `bstrName`  
 Der Eigenschaftenname in einem Kontext.  
  
 `bstrType`  
 Der Typ der formatierten Zeichenfolge.  
  
 `bstrValue`  
 Der Eigenschaftswert als formatierte Zeichenfolge.  
  
 `bstrFullName`  
 Der vollständige Name der Eigenschaft.  
  
 `dwAttrib`  
 Eine Enumeration, die angibt, die Flags für die Attribute der Debug-Eigenschaft.  
  
 `pDebugProp`  
 `IDebugProperty` Objekt, das diesem `ExtendedDebugPropertyInfo`.  
  
 `nDISPID`  
 Die Dispatch-Id ein.  
  
 `nType`  
 Der Typ des erweiterten Eigenschaft.  
  
 `varValue`  
 Die erweiterte Eigenschaft-Wert, wenn es in Variante eingepasst werden kann.  
  
 `plbValue`  
 Die tatsächlichen Datenbytes des Eigenschaftswerts.  
  
 `pDebugExtProp`  
 `IDebugExtendedProperty` Objekt, das diesem `ExtendedDebugPropertyInfo`.  
  
## <a name="see-also"></a>Siehe auch  
 [DebugPropertyInfo-Struktur](../../winscript/reference/debugpropertyinfo-structure.md)   
 [IDebugProperty-Schnittstelle](../../winscript/reference/idebugproperty-interface.md)   
 [IDebugExtendedProperty-Schnittstelle](../../winscript/reference/idebugextendedproperty-interface.md)   
 [DBGPROP_ATTRIB_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)