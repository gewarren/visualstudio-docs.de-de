---
title: IDebugProgram2::Terminate | Microsoft-Dokumentation
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
- IDebugProgram2::Terminate
helpviewer_keywords:
- IDebugProgram2::Terminate
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bb969fe4e3170da3723861f63948dced5de68d69
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51768336"
---
# <a name="idebugprogram2terminate"></a>IDebugProgram2::Terminate
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Das Programm beendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT Terminate(   
   void   
);  
```  
  
```csharp  
int Terminate();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Wenn möglich, wird das Programm beendet und aus dem Prozess entladen werden; Andernfalls führt die Debug-Engine (DE) eventuell erforderlichen Bereinigungen.  
  
 Diese Methode oder der [Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md) Methode wird von der IDE, in der Regel in der Antwort an den Benutzer, die das Anhalten des alle-Debuggen aufgerufen. Die Implementierung dieser Methode sollten im Idealfall die Anwendung innerhalb des Prozesses beendet. Wenn dies nicht möglich ist, sollte die DE verhindern, dass das Programm ausführen, bei diesem Vorgang keine weiteren (und werden eventuell erforderlichen Bereinigungen). Wenn die `IDebugProcess2::Terminate` Methode wurde von der IDE aufgerufen, wird der gesamte Prozess einige Zeit nach beendet die `IDebugProgram2::Terminate` Methode wird aufgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)

