---
title: IDebugProgram2::GetProcess | Microsoft-Dokumentation
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
- IDebugProgram2::GetProcess
helpviewer_keywords:
- IDebugProgram2::GetProcess
ms.assetid: 1d602485-ebaf-451c-9165-f2e226f20a90
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a0748ee6d0ccf14f0fd142c5d64aaa00ea278dec
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51724278"
---
# <a name="idebugprogram2getprocess"></a>IDebugProgram2::GetProcess
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Rufen Sie den Prozess, den dieses Programm ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetProcess(  
   IDebugProcess2** ppProcess  
);  
```  
  
```csharp  
int GetProcess(  
   out IDebugProcess2 ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppProcess`  
 [out] Gibt die [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) -Schnittstelle, die den Prozess darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Wenn es sich bei eine Debug-Engine (DE) implementiert die [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md) -Schnittstelle, die DE Implementierung dieser Methode sollte immer zurückgeben `E_NOTIMPL` da eine bereitgestellten Kompatibilitätsrichtlinie nicht bestimmen kann, welcher Prozess, in und aus diesem Grund ausgeführt wird kann nicht eine Implementierung dieser Methode zu erfüllen.  
  
 Implementieren der `IDebugEngineLaunch2` Schnittstelle bedeutet, dass die DE wissen, wie Sie zum Erstellen eines Prozesses; muss daher die DE Implementierung des der [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) Schnittstelle ist, können Sie wissen, welcher Prozess in läuft.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)

