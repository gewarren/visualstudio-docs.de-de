---
title: 'Vorgehensweise: Aktivieren und Deaktivieren von bearbeiten und fortfahren | Microsoft-Dokumentation'
ms.custom: seodec18
ms.date: 10/04/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: 0b5fbc7ee0f2d85c72ccda75bc2e8531419d52e3
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2018
ms.locfileid: "53051386"
---
# <a name="how-to-enable-and-disable-edit-and-continue-c-vb-c"></a>Vorgehensweise: Aktivieren und Deaktivieren von bearbeiten und Fortfahren (C#, VB, C++)

Sie können das Aktivieren oder deaktivieren **bearbeiten und Fortfahren** in Visual Studio **Optionen** Dialogfeld zur Entwurfszeit. Die Funktion **Bearbeiten und Fortfahren** funktioniert nur in Debugversionen. Weitere Informationen hierzu finden Sie unter [Bearbeiten und Fortfahren](../debugger/edit-and-continue.md). 
  
Bei systemeigenem C++ **bearbeiten und Fortfahren** erfordert die Verwendung der `/INCREMENTAL` Option. Weitere Informationen zu den Funktionen in C++ finden Sie in diesem [Blogbeitrag](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/) und [bearbeiten und Fortfahren (Visual C++)](../debugger/edit-and-continue-visual-cpp.md).
  
**So aktivieren oder deaktivieren, bearbeiten und Fortfahren:**  
  
1.  Wenn Sie in einer Debugsitzung sind, beenden Sie das Debuggen (**Debuggen** > **Debuggen beenden** oder **UMSCHALT**+**F5**) .

1.  In **Tools** > **Optionen** > (oder **Debuggen** > **Optionen**) > **Debuggen**  >  **Allgemeine**Option **bearbeiten und Fortfahren** im rechten Bereich.  
  
    > [!NOTE]
    >  Wenn IntelliTrace aktiviert ist und Sie IntelliTrace-Ereignisse und Aufrufinformationen erfassen, wird „Bearbeiten und Fortfahren“ deaktiviert. Weitere Informationen finden Sie unter [IntelliTrace](../debugger/intellitrace.md).
    
1.  Für C++-Code stellen Sie sicher, dass **systemeigene bearbeiten und Fortfahren aktivieren** ausgewählt ist, und legen Sie die zusätzlichen Optionen:
    - **Änderungen beim Fortfahren anwenden (nur nativ)**  
      
      Wenn ausgewählt, wird in Visual Studio automatisch kompiliert und codeänderungen angewendet werden, wenn Sie fortfahren, Debuggen von Zustand "unterbrochen". Andernfalls können Sie mithilfe von Änderungen zu übernehmen **Debuggen** > **Codeänderungen übernehmen**.  
      
    - **Warnung bei veraltetem Code (nur nativ)**  
      
      Wenn Sie ausgewählt haben, erhalten Warnungen über veralteten Code. 
  
1.  Klicken Sie auf **OK**.    
