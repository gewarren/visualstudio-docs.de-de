---
title: IEnumDebugObjects::Skip | Microsoft-Dokumentation
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
- IEnumDebugObjects::Skip
helpviewer_keywords:
- IEnumDebugObjects::Skip method
ms.assetid: 957cead8-0a9c-4403-b190-b9fbadc49d42
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 870671a914a77b0c7c70ebf93b258c37b5531ead
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51736460"
---
# <a name="ienumdebugobjectsskip"></a>IEnumDebugObjects::Skip
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Diese Methode überspringt die angegebene Anzahl von Elementen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT Skip(  
   [in] ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   [In] uint celt  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der zu überspringenden Elemente.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`. Gibt `S_FALSE` Wenn `celt` größer als die Anzahl der verbleibenden Elemente ist; andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `celt` gibt einen Wert größer als die Anzahl der verbleibenden Elemente am Ende die Enumeration festgelegt ist und `S_FALSE` zurückgegeben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)

