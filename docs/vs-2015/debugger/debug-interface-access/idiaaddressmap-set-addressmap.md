---
title: 'Idiaaddressmap:: Set_addressmap | Microsoft-Dokumentation'
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
- IDiaAddressMap::set_addressMap method
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea357cc04a2c0b1bce5882e1dd10cda8138a0b8c
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51756712"
---
# <a name="idiaaddressmapsetaddressmap"></a>IDiaAddressMap::set_addressMap
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Stellt eine Adresszuordnung zum Unterstützen von Bild Layout Übersetzungen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
HRESULT set_addressMap (   
   DWORD                     cbData,  
   struct DiaAddressMapEntry data[],  
   BOOL                      imagetoSymbols  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cbData`  
 [in] Die Anzahl der Elemente in der `data` Parameter.  
  
 `data[]`  
 [in] Ein Array von [DiaAddressMapEntry-Struktur](../../debugger/debug-interface-access/diaaddressmapentry.md) Strukturen, die die Übersetzung-Zuordnung zu definieren.  
  
 `imagetoSymbols`  
 [in] `TRUE` Wenn die `data` Parameter definiert das Layout für das neue in das ursprüngliche Layout eine Zuordnung (wie durch die Debugsymbole beschrieben). `FALSE` Wenn `data` ist eine Zuordnung für das neue Image-Layout das ursprüngliche Layout entnommen.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls ein Fehlercode zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 In der Regel ruft der DIA Adresse Übersetzung Maps über die Programmdatenbankdatei (.pdb) ab. Wenn diese Werte fehlen, sind die [idiaaddressmap:: Set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) Methode zweimal aufgerufen wird einmal mit der `imagetoSymbols` Parametersatz zu `TRUE` und einmal mit der `imagetoSymbols` Parametersatz zu `FALSE`. Adressübersetzung der Zuordnung können nicht aktiviert werden, mithilfe der [idiaaddressmap:: Put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) Methode, wenn beide Übersetzung Maps bereitgestellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [DiaAddressMapEntry-Struktur](../../debugger/debug-interface-access/diaaddressmapentry.md)   
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)



