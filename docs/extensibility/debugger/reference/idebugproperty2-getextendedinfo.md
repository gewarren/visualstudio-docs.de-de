---
title: IDebugProperty2::GetExtendedInfo | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::GetExtendedInfo
helpviewer_keywords:
- IDebugProperty2::GetExtendedInfo
ms.assetid: 0c9c0b2b-7540-4424-adb5-fce7aa37a026
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e0366d547dea7f181c42fd5cccbacb568418c203
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53935410"
---
# <a name="idebugproperty2getextendedinfo"></a>IDebugProperty2::GetExtendedInfo
Ruft Informationen für die Eigenschaft erweitert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExtendedInfo (   
   REFGUID* guidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
```csharp  
int GetExtendedInfo (   
   ref Guid guidExtendedInfo,  
   out object pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `guidExtendedInfo`  
 [in] GUID, der bestimmt, den Typ des erweiterten Informationen abgerufen werden sollen. Einzelheiten finden Sie unter "Hinweise".  
  
 `pExtendedInfo`  
 [out] Gibt eine `VARIANT` (C++) oder ein Objekt (C#), die zum Abrufen der Informationen der erweiterten Eigenschaft verwendet werden kann. Dieser Parameter möglicherweise zurück, z. B. eine `IUnknown` -Schnittstelle, die abgefragt werden kann ein [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) Schnittstelle. Einzelheiten finden Sie unter "Hinweise".  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`; gibt andernfalls den Fehlercode zurück. Gibt `S_GETEXTENDEDINFO_NO_EXTENDEDINFO` , wenn es keine erweiterten Informationen gibt abrufen.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode gibt es zum Abrufen von Informationen, die nicht alleine als komponententestbar ist an abgerufen wird, durch den Aufruf der [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) Methode.  
  
 Die folgenden GUIDs werden in der Regel von dieser Methode erkannt (die GUID-Werte sind für C#-Code angegeben, da der Name nicht in einer beliebigen Assembly verfügbar ist). Zusätzliche GUIDs können für die interne Verwendung erstellt werden.  
  
|name|GUID|Beschreibung|  
|----------|----------|-----------------|  
|guidDocument|{3f98de84-fee9-11d0-b47f-00a0244a1dd2}|Gibt eine `IUnknown` Schnittstelle, um das Dokument. In der Regel die [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) Schnittstelle erhalten Sie von dieser `IUnknown` Schnittstelle.|  
|guidCodeContext|{e2fc65e-56ce - 11d 1-b528-00aax004a8797}|Gibt eine `IUnknown` Schnittstelle, um den Dokumentenkontext. In der Regel die [idebugdocumentcontext2 angegeben](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) Schnittstelle erhalten Sie von dieser `IUnknown` Schnittstelle.|  
|guidCustomViewerSupported|{d9c9da31-ffbe-4eeb-9186-23121e3c088c}|Gibt eine Zeichenfolge, die mit der CLSID der ein benutzerdefinierter Viewer, die in der Regel von einer ausdrucksauswertung implementiert.|  
|guidExtendedInfoSlot|{6df235ad-82c6-4292-9c97-7389770bc42f}|Gibt eine 32-Bit-Zahl, die die gewünschten Slotnummer darstellt, wenn diese Eigenschaft auf eine lokale Adresse von verwaltetem Code darstellt.|  
|guidExtendedInfoSignature|{b5fb6d46-f805-417f-96a3-8ba737073ffd}|Gibt eine Zeichenfolge, die die Signatur der Property-Objekt zugeordneten Variablen enthält.|  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)