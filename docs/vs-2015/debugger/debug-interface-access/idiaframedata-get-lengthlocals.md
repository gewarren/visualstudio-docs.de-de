---
title: 'Idiaframedata:: Get_lengthlocals | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_lengthLocals method
ms.assetid: 51fe15c3-4cd6-4a06-8a41-a56502209762
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 66d70767c21f253064011752f965973efa885ab2
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51746776"
---
# <a name="idiaframedatagetlengthlocals"></a>IDiaFrameData::get_lengthLocals
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ruft die Anzahl der Bytes der lokalen Variablen, die auf dem Stapel abgelegt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT get_lengthLocals (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRetVal`  
 [out] Gibt die Anzahl der Bytes der lokalen Variablen zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`. Gibt `S_FALSE` Wenn diese Eigenschaft nicht unterstützt wird. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Der von dieser Methode zurückgegebene Wert wird normalerweise verwendet, bei der Interpretation einer Programm-Zeichenfolge (finden Sie unter den [idiaframedata:: Get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md) -Methode für die Definition einer Programm-Zeichenfolge).  
  
## <a name="see-also"></a>Siehe auch  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)



