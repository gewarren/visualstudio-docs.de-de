---
title: 'Idiasymbol:: Get_addressoffset | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_addressOffset method
ms.assetid: c15639b0-7f37-46c7-891b-40273b7f6319
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5dba9f8b40bd3246dd07ec2fae76ad6aa8b9c604
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49917805"
---
# <a name="idiasymbolgetaddressoffset"></a>IDiaSymbol::get_addressOffset
Ruft den Zeitzonenoffset-Teil eines Speicherorts für die Adresse ab. Verwenden, wenn die [LocationType-Enumeration](../../debugger/debug-interface-access/locationtype.md) nastaven NA hodnotu `LocIsStatic`.  
  
## <a name="syntax"></a>Syntax  
  
```C++  
HRESULT get_addressOffset (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRetVal`  
 [out] Gibt den Zeitzonenoffset-Teil eines Speicherorts für die Adresse zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, wird `S_OK`ist, andernfalls gibt `S_FALSE` oder ein Fehlercode.  
  
> [!NOTE]
>  Der Rückgabewert `S_FALSE` bedeutet, dass die Eigenschaft nicht für das Symbol verfügbar ist.  
  
## <a name="remarks"></a>Hinweise  
 Bei statischen Elementen befindet sich in einer externen DLL kann von dieser Methode zurückgegebene Offset 0 sein, wie diese Methode beruht auf die virtuelle Adresse des Elements. Virtuelle Adressen gültig sind nur dann, wenn die [idiasession:: Put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md) -Methode in der die [IDiaSession](../../debugger/debug-interface-access/idiasession.md) Schnittstelle mit einem ungleich NULL-Parameter angeben der Adresse Laden der DLL aufgerufen wurde.  
  
 Um den Teil "Abschnitt" eine Adresse zu erhalten, rufen die [idiasymbol:: Get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
  
|Anforderung|Beschreibung|  
|-----------------|-----------------|  
|Header:|dia2.h|  
|Version:|DIA-SDK V7. 0|  
  
## <a name="see-also"></a>Siehe auch  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType-Enumeration](../../debugger/debug-interface-access/locationtype.md)   
 [Idiasymbol:: Get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)   
 [Idiasession:: Put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)