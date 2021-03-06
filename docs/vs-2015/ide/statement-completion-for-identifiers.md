---
title: Anweisungsvervollständigung für Bezeichner | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IntelliSense [JavaScript], statement completion
- statement completion, JavaScript IntelliSense
ms.assetid: c2cd4945-c67e-471b-8057-96cfd25f7fb2
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d58c5ecc1d787195f7f5c91a07da7a4e775fc27e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49827054"
---
# <a name="statement-completion-for-identifiers"></a>Anweisungsvervollständigung für Bezeichner
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

JavaScript lässt keine explizite Typisierung für Deklarationen von Variablen zu. Daher kann nicht der IntelliSense-Vervollständigungslisten nicht immer für Objekte bereit. Dies kann in verschiedenen Situationen auftreten. Im folgenden werden einige gängige Rollen.  
  
- Ein Parameter ist deklariert, aber es nicht aufgerufen wurde an anderer Stelle im aktiven Dokument, wie im folgenden Beispiel gezeigt.  
  
  ```javascript  
  function illuminate(light) {  
           light.  // Accurate statement completion is not available   
                   // unless illuminate is called elsewhere with a   
                   // parameter that has a value. If it is called only  
                   // in a function that is a sibling to   
                   // illuminate(light) in the call hierarchy, the   
                   // IntelliSense engine also cannot determine the   
                   // parameter type.  
       }  
  
  // Sibling function. No statement completion for light   
  // object in preceding code.  
  function lightLamp() {  
      var x = illuminate(1);  
  }  
  
  // Uncomment the next line to obtain statement completion for  
  // light object in preceding code.  
  // var x = illuminate(1);  
  ```  
  
- Ein Objekt ist in einer Funktion, die als Reaktion auf ein Ereignis aufgerufen wird. Zur Entwurfszeit kann die IntelliSense-Engine den Typ der Objekte in dieser Situation nicht bestimmen.  
  
   Wenn die IntelliSense-Engine bestimmen kann, dass das Ereignis, in der Regel durch die Verwendung von aufgerufen werden muss, `addEventListener` für das Ereignis in das aktive Dokument ist, wird genauer IntelliSense-Informationen bereitgestellt.  
  
  Wenn IntelliSense ein Objekt identifizieren kann, füllt die IntelliSense-Engine die Vervollständigungsliste mit benannten Entitäten oder Bezeichner, die im aktiven Dokument vorhanden sind. Wenn die Liste dieser Bezeichner enthält, werden die informationssymbole neben dem Namen angezeigt. Außerdem zeigt eine QuickInfo für jeden Bezeichner an, dass der Ausdruck unbekannt ist. Die folgende Abbildung zeigt die Anweisung abgeschlossen-Optionen für ein Objekt des Typs `light` , können nicht identifiziert werden, da das Objekt und seine Eigenschaften nicht definiert sind. Allerdings die `intensity` Eigenschaft ist in der bezeichnerliste verfügbar, da er verwendet wurde die `illuminate` Funktion.  
  
  **Abschluss-Optionen für ein Objekt, das nicht identifiziert werden kann**  
  
  ![JavaScript IntelliSense für Bezeichner](../ide/media/js-intellisense-identifiers.png "Js_intellisense_identifiers")  
  
  Sie können die Vervollständigungsliste für ein Objekt überschreiben, indem Sie mithilfe von XML-Dokumentationskommentare oder JavaScript-IntelliSense-Erweiterungs-Features. Verwendung dieser Features können Sie Typinformationen und Bereitstellen aussagekräftigeren IntelliSense-Informationen, wenn es andernfalls nicht verfügbar wären. Weitere Informationen finden Sie unter [Erweitern von JavaScript IntelliSense](../ide/extending-javascript-intellisense.md) und [Erstellen von XML-Dokumentationskommentare](../ide/create-xml-documentation-comments-for-javascript-intellisense.md).  
  
## <a name="see-also"></a>Siehe auch  
 [JavaScript IntelliSense](../ide/javascript-intellisense.md)



