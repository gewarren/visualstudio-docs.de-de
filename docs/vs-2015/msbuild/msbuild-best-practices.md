---
title: Best Practices für MSBuild | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 94941cacdfea79c2d846b9936b8532f155d6cebb
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49218387"
---
# <a name="msbuild-best-practices"></a>Best Practices für MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Es werden die folgenden bewährten Methoden zum Schreiben von MSBuild-Skripts empfohlen:  
  
-   Standardwerte für Eigenschaften werden am besten mit dem `Condition`-Attribut verarbeitet und nicht durch Deklarieren einer Eigenschaft, deren Standardwert in der Befehlszeile überschrieben werden kann. Verwenden Sie beispielsweise  
  
     `<MyProperty Condition="$(MyProperty)" == ''>`  
  
     `MyDefaultValue`  
  
     `</MyProperty>`  
  
-   Vermeiden Sie beim Auswählen von Elementen den Einsatz von Platzhaltern. Geben Sie stattdessen Dateien explizit an. Dies erleichtert das Auffinden von Fehlern, die beim Hinzufügen oder Löschen von Dateien auftreten können.  
  
## <a name="see-also"></a>Siehe auch  
 [MSBuild Advanced Concepts (Weiterführende MSBuild-Konzepte)](../msbuild/msbuild-advanced-concepts.md)



