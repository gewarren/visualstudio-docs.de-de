---
title: IDebugErrorEvent2::GetErrorMessage | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords:
- IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7e844c37ba7e9b396c0a0216b624b446916ff639
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53913340"
---
# <a name="idebugerrorevent2geterrormessage"></a>IDebugErrorEvent2::GetErrorMessage
Gibt zurück, anhand derer der Erstellung der eine lesbare Fehlermeldung aus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetErrorMessage(  
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrErrorFormat,  
   HRESULT*     hrErrorReason,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetErrorMessage(  
   out enum_MESSAGETYPE   pMessageType,  
   out string             pbstrErrorFormat,  
   out int                phrErrorReason,  
   out uint               pdwType,  
   out string             pbstrHelpFileName,  
   out uint               pdwHelpId  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pMessageType`  
 [out] Gibt einen Wert aus der [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) Enumeration, die den Typ der Nachricht beschreibt.  
  
 `pbstrErrorFormat`  
 [out] Das Format der die endgültige Nachricht an den Benutzer (Details finden Sie unter "Hinweise").  
  
 `hrErrorReason`  
 [out] Der Fehlercode der Nachricht geht.  
  
 `pdwType`  
 [out] Schweregrad des Fehlers (verwenden Sie für Konstanten MB_XXX `MessageBox`, z. B. `MB_EXCLAMATION` oder `MB_WARNING`).  
  
 `pbstrHelpFileName`  
 [out] Der Pfad zu einer Hilfedatei (festgelegt auf einen null-Wert, wenn keine Hilfedatei vorhanden ist).  
  
 `pdwHelpId`  
 [out] Die ID des Hilfethemas zum Anzeigen der (auf 0, wenn kein Hilfethema festgelegt).  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Fehlermeldung, die ungefähr folgendermaßen formatiert werden sollen `"What I was doing.  %1"`. Die `"%1"` würde dann vom Aufrufer mit der Fehlermeldung, abgeleitet aus dem Fehlercode ersetzt (der im zurückgegeben `hrErrorReason`). Die `pMessageType` -Parameter weist den Aufrufer wie die letzte Fehlermeldung angezeigt werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)