---
title: "Überprüfen Sie Ihre app mit verlaufsbezogenes debugging | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 629b5d93-39b2-430a-b8ba-d2a47fdf2584
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 10d9e23912da2ee5d0af1b6d2f846fa1de2f94fe
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="inspect-your-app-with-intellitrace-historical-debugging-in-visual-studio"></a>Überprüfen Sie Ihre app mit IntelliTrace historical Debuggen in Visual Studio
Sie können [verlaufsbezogenes debugging](../debugger/historical-debugging.md) rückwärts und Vorwärts durch die Ausführung der Anwendung und ihren Status überprüfen.  
  
Sie können IntelliTrace in Visual Studio Enterprise Edition jedoch nicht in der Professional oder Community Edition verwenden.  
  
## <a name="navigate-your-code-with-historical-debugging"></a>Navigieren Sie Ihren Code mit verlaufsbezogenem debugging  
 Beginnen wir mit einem einfachen Programm, das einen Fehler aufweist. Fügen Sie in einer C#-Konsolenanwendung folgenden Code hinzu:  
  
```CSharp  
static void Main(string[] args)  
{  
    int testInt = 0;  
    int resultInt = AddAll(testInt);  
    Console.WriteLine(resultInt);  
}  
private static int AddAll(int j)  
{  
    for (int i = 0; i < 20; i++)  
    {  
        j = AddInt(j);  
    }  
    return j;  
}  
  
private static int AddInt(int add)  
{  
    if (add == 10)  
    {  
        return add += 25;  
    }  
    return ++add;  
}  
```  
  
 Wir gehen davon aus, die der erwartete Wert des `resultInt` nach dem Aufruf `AddAll()` ist 20 (das Ergebnis des inkrementieren `testInt` 20-Mal). (Wir außerdem davon aus, dass Sie nicht, dass den Fehler in sehen `AddInt()`). Aber das Ergebnis ist jedoch tatsächlich 44 beträgt. Wie finden wir den Fehler, ohne `AddAll()` schrittweise 10 Mal durchzugehen? Wir können die verlaufsbezogenes debugging verwenden, um den Fehler schneller und leichter zu finden. Gehen Sie dabei folgendermaßen vor:  
  
1.  In **Extras > Optionen > IntelliTrace > Allgemein**, stellen Sie sicher, dass IntelliTrace aktiviert ist, und wählen Sie **IntelliTrace-Ereignisse und Aufrufinformationen**. Wenn Sie diese Option nicht auswählen, wird Ihnen der Navigationsbundsteg nicht angezeigt (sie Erläuterung weitere unten).  
  
2.  Legen Sie einen Haltepunkt in der Zeile `Console.WriteLine(resultInt);` fest.  
  
3.  Beginnen Sie mit dem Debuggen. Der Code wird bis zum Haltepunkt ausgeführt. In der **"lokal"** Fenster sehen, dass der Wert des `resultInt` 44 ist.  
  
4.  Öffnen der **Diagnosetools** Fenster (**Debuggen > Diagnosetools anzeigen**). Das Code-Fenster sieht wie folgt aus:  
  
     ![Codefenster am Haltepunkt](../debugger/media/historicaldebuggingbreakpoint.png "HistoricalDebuggingBreakpoint")  
  
5.  Neben dem linken Rand sollte ein doppelter Pfeil angezeigt werden, genau über dem Haltepunkt. Dieser Bereich wird als Navigationsbundsteg bezeichnet und dient zum verlaufsbezogenen Debuggen. Klicken Sie auf den Pfeil.  
  
     Im Codefenster sollte Ihnen die vorangegangene Codezeile (`int resultInt = AddIterative(testInt);`) rosa gefärbt angezeigt werden. Über dem Fenster sollte eine Meldung angezeigt, die Sie sich nun im verlaufsbezogenes debugging befinden.  
  
     Das Codefenster sieht nun folgendermaßen aus:  
  
     ![Codefenster im verlaufsbezogenen Debugmodus](../debugger/media/historicaldebuggingback.png "HistoricalDebuggingBack")  
  
6.  Nachdem Sie in Schritt können die `AddAll()` Methode (**F11**, oder die **Einzelschritt** Schaltfläche auf dem Navigationsbundsteg. Schritt vorwärts (**F10**, oder **zum nächsten Aufruf wechseln** auf dem Navigationsbundsteg. Die rosa Linie befindet sich jetzt in der `j = AddInt(j);`-Zeile. **F10** in diesem Fall nicht in die nächste Zeile des Codes schrittweise. Stattdessen fährt es mit dem nächsten Funktionsaufruf fort. Das verlaufsbezogene Debugging navigiert von Aufruf zu Aufruf, und überspringt Codezeilen, die nicht in einem Funktionsaufruf enthalten sind.  
  
7.  Nun in die `AddInt()`-Methode einsteigen. Der Fehler in diesem Code sollte Ihnen sofort angezeigt werden.  

## <a name="next-steps"></a>Nächste Schritte

Dieses Verfahren oberflächlich nur der Verwendungsmöglichkeiten verlaufsbezogenen Debugging.

- Zum Anzeigen von Momentaufnahmen während des Debuggens finden Sie unter [Anzeigen von Momentaufnahmen mithilfe von IntelliTrace Schritt hinten](../debugger/how-to-use-intellitrace-step-back.md).
- Weitere Informationen zu den unterschiedlichen Einstellungen und die Auswirkungen der verschiedenen Schaltflächen auf dem Navigationsbundsteg finden Sie unter [IntelliTrace-Features](../debugger/intellitrace-features.md).