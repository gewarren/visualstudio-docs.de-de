---
title: Extrahieren Sie die Methode - Umgestaltung (c#) | Microsoft Docs
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: d79d55ae-f6bb-4902-8db2-e7fe01bdb0bf
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.extractmethod
dev_langs: csharp
ms.openlocfilehash: 3890d427ed2888647675a241f4e62a5635d7308c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="extract-a-method-in-c"></a>Extrahieren Sie eine Methode in c# #
**Was:** können Sie ein Fragment des Codes in einem eigenen umzuwandeln.

**Wann:** haben Sie ein Fragment von vorhandenem Code, in einer Methode, die von einer anderen Methode aufgerufen werden muss.  

**Grund:** Sie konnte Kopieren/Einfügen dieses Codes jedoch, die zu Duplizierung führen würde.  Eine bessere Lösung ist dieses Fragment in einem eigenen umgestaltet werden, die kostenlos durch keine andere Methode aufgerufen werden kann.

**Vorgehensweise:**

1. Markieren Sie den Code, die extrahiert werden:

   ![Hervorgehobene code](media/extractmethod_highlight.png)

1. Als Nächstes führen Sie eine der folgenden:
   * **Tastatur**
     * Drücken Sie **STRG + R**, klicken Sie dann **STRG + M**.  (Beachten Sie, dass Ihre Tastenkombination je nach dem gewählten Profil möglicherweise abweicht.)
     * Drücken Sie **STRG +.** Trigger die **Schnellaktionen und Refactorings** Menü **Methode extrahieren** im Popupmenü Fenster Vorschau.
   * **Maus**
     * Wählen Sie **Bearbeiten > Umgestalten > Methode extrahieren**.
     * Mit der rechten Maustaste in des Codes, und wählen Sie **Umgestalten > extrahieren > Methode extrahieren**.
     * Mit der rechten Maustaste in des Codes, wählen Sie die **Schnellaktionen und Refactorings** Menü **Methode extrahieren** im Popupmenü Fenster Vorschau.

   Die Methode wird sofort erstellt werden.  Von hier aus können Sie nun die Methode umbenennen, einfach durch den neuen Namen eingeben.

   > [!TIP]
   > Sie können auch aktualisieren, Kommentare und andere Zeichenfolgen mit diesen neuen Namen sowie [Vorschau der Änderungen](../../ide/preview-changes.md) vor dem Speichern, verwenden die Kontrollkästchen in der **umbenennen** Feld der oben angezeigt wird rechts von der IDE.

   ![Benennen Sie die Methode](media/extractmethod_rename.png)

1. Wenn Sie mit der Änderung zufrieden sind, klicken Sie auf die **übernehmen** Schaltfläche oder drücken Sie die **EINGABETASTE** und die Änderungen werden ein Commit ausgeführt werden.

## <a name="see-also"></a>Siehe auch  
[Refactoring (C#)](../refactoring-csharp.md)  
[Vorschau der Änderungen](../../ide/preview-changes.md)