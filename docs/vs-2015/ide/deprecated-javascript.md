---
title: '&lt;als veraltet markiert&gt; (JavaScript) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf33d371-59da-4310-95ee-d7524fd9d58c
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4c643afe786366c7c470e74d02a5145a600a6b87
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269279"
---
# <a name="ltdeprecatedgt-javascript"></a>&lt;als veraltet markiert&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Gibt eine veraltete Funktion oder Methode an.  
  
## <a name="syntax"></a>Syntax  
  
```  
<deprecated  
    type="deprecate|remove"  
    locid="descriptionID">description  
</deprecated>  
```  
  
#### <a name="parameters"></a>Parameter  
 `type`  
 Dies ist optional. Gibt an, ob die Funktion oder Methode in einem zukünftigen Release entfernt wird oder ob die Funktion oder Methode bereits entfernt wurde und ihre Verwendung möglicherweise zu einem Fehler führen wird. Legen Sie es auf `deprecate` fest, um anzugeben, dass die Funktion oder Methode in einem zukünftigen Release entfernt wird. Legen Sie es auf `remove` fest, um anzugeben, dass die Funktion oder Methode bereits entfernt wurde.  
  
 `locid`  
 Dies ist optional. Der Bezeichner für Lokalisierungsinformationen über die Funktion oder Methode. Der Bezeichner ist entweder eine Member-ID, oder er entspricht dem `name`-Attributwert in einem Meldungsbündel, das von OpenAjax-Metadaten definiert wird. Der Bezeichnertyp hängt von dem angegebenen Format in die [ \<Loc >](../ide/loc-javascript.md) Element.  
  
 `description`  
 Dies ist optional. Eine Beschreibung der Funktion oder Methode, die veraltet ist.  
  
## <a name="remarks"></a>Hinweise  
 Die Elemente, die verwendet werden, um Funktionen, wie unter anderem `<deprecated>`, mit Anmerkungen zu versehen und müssen vor allen Anweisungen in den Funktionstext eingefügt werden. Wenn Sie eine Funktion als veraltet markieren, es wird empfohlen, die Sie ersetzen die [ \<summary >](../ide/summary-javascript.md) -Element mit der `<deprecated>` Element.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Verwendung des `<deprecated>`-Elements veranschaulicht.  
  
```javascript  
function areaFunction(radiusParam) {  
    /// <deprecated type="deprecate" >Determines the area of a circle when supplied a radius parameter.</deprecated>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentationskommentare](../ide/xml-documentation-comments-javascript.md)



