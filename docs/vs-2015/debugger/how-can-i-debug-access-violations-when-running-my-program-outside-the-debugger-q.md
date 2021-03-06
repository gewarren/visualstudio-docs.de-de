---
title: Wie können Zugriffsverletzungen, die beim Ausführen des Programms außerhalb des Debuggers auftreten, gedebuggt werden? | Microsoft-Dokumentation
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
- vs.debug.access
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5e0ed8025986c92cd4c809ea8b04f0109fb010c5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51816275"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Wie können Zugriffsverletzungen, die beim Ausführen des Programms außerhalb des Debuggers auftreten, gedebuggt werden?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Problembeschreibung  
 Das Programm läuft in der Visual Studio-Umgebung einwandfrei. Wird es jedoch eigenständig unter dem Windows-Betriebssystem ausgeführt, generiert es eine Zugriffsverletzung. Wie kann dieses Problem behoben werden?  
  
## <a name="solution"></a>Lösung  
 Legen Sie die [Just-in-Time-Debuggen](../debugger/just-in-time-debugging-in-visual-studio.md) aus, und Ihr Programm im eigenständigen Modus ausgeführt, bis die zugriffsverletzung auftritt. Klicken Sie auf die **Zugriffsverletzung** Dialogfeld klicken Sie auf **Abbrechen** den Debugger starten.  
  
 Weitere Informationen finden Sie im Knowledge Base-Artikel Q133174, "How to Locate Where a General Protection (GP) Fault Occurs" (nur auf Englisch verfügbar). Sie finden Knowledge Base-Artikel auf der MSDN Library-CD oder durch Suchen [ http://support.microsoft.com/ ](http://support.microsoft.com/).  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von nativem Code häufig gestellte Fragen](../debugger/debugging-native-code-faqs.md)   
 [Debuggen von nativem Code](../debugger/debugging-native-code.md)



