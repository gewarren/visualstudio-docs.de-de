---
title: Zeit für die vorzeitige Entfernung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e1ddd0f239317021d38017ec159de46ecbc2aa77
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51721396"
---
# <a name="preemption-time"></a>Zeit für die vorzeitige Entfernung
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Diese Segmente in der Zeitachse werden der Blockierungszeit zugeordnet, die als Speicherverwaltungszeit kategorisiert ist. Diese Kategorie impliziert, dass ein Thread aus einem der folgenden Gründe deaktiviert wird:  
  
- Der Planer hat ihn durch einen Thread mit höherer Priorität ersetzt  
  
- Das Ausführungsquantum des Threads ist abgelaufen, und andere Threads konnten ausgeführt werden  
  
  Gleichzeitig wurde ein Thread aufgrund einer Kernelwarteursache blockiert, die die Parallelitätsschnellansicht als vorzeitige Entfernung erfasst. Die vorzeitige Entfernung der Segmente beginnt, wenn ein Thread aus einem logischen Kern übertragen wird, und endet, wenn der Thread mit der Ausführung fortfährt.  
  
  Die QuickInfo für ein vorzeitig entferntes Segment zeigt den Namen des Prozesses oder Threads an, durch die die vorzeitige Entfernung ausgelöst wurde. Dies impliziert allerdings nicht, dass der Prozess oder der Thread, der den Vorgang übernommen hat, auch wirklich während der vorzeitigen Entfernung ausgeführt wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Threads View (Threadansicht)](../profiling/threads-view-parallel-performance.md)



