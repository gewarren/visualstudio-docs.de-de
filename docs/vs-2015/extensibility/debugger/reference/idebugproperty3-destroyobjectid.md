---
title: IDebugProperty3::DestroyObjectID | Microsoft-Dokumentation
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
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 88eb8160e265c51e40b3d96be7e9c1d187e8a861
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51793190"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Zerstört die eindeutige ID dieser Eigenschaft zugeordnet, der angibt, dass der Aufrufer nicht mehr wichtig, um diese Eigenschaft über alle anderen Eigenschaften eindeutig zu identifizieren.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Debug-Engine nicht eindeutige IDs für eine Eigenschaft zu unterstützen (da es bereits diese eindeutig intern nachverfolgt), wird einfach zurückgegeben kann `E_NOTIMPL` für diese Methode.  
  
 Eindeutige IDs werden erstellt, durch einen Aufruf der [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) Methode, wenn der Aufrufer sicherstellen, dass diese Eigenschaft für alle anderen Eigenschaften eindeutig identifiziert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)

