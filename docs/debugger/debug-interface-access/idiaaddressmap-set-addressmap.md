---
title: 'Idiaaddressmap:: Set_addressmap | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_addressMap method
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d097ccbe5c893c603aaa2a018f8fcd422f15ac2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49834521"
---
# <a name="idiaaddressmapsetaddressmap"></a>IDiaAddressMap::set_addressMap
Stellt eine Adresszuordnung zum Unterstützen von Bild Layout Übersetzungen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```C++  
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