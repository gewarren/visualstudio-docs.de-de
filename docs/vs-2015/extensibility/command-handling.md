---
title: Befehlsbehandlung | Microsoft-Dokumentation
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
- editors [Visual Studio SDK], legacy - command handling
ms.assetid: 78f67d92-77f7-45cb-ad75-6e3346379cc3
caps.latest.revision: 21
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d26350e9b0465b3a175cb135509f85cf69da21f0
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51778812"
---
# <a name="command-handling"></a>Behandlung von Befehlen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Als Editor verwenden, kann neue Befehle definieren. Befehle werden in der Regel in einem Menü, das auf einer Symbolleiste oder in einem Kontextmenü angezeigt.  
  
 Weitere Informationen zu definieren, Befehle und Menüs, finden Sie unter [Befehle, Menüs und Symbolleisten](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Ein Sprachdienst kann steuern, welche Kontextmenüs im Editor angezeigt werden, durch das Abfangen der <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> Enumeration. Alternativ können Sie im Kontextmenü auf einer pro-Marker-Basis steuern. Weitere Informationen finden Sie unter [wichtige Befehle für Sprachdienstfilter](../extensibility/internals/important-commands-for-language-service-filters.md).  
  
## <a name="adding-commands-to-the-editor-context-menu"></a>Hinzufügen von Befehlen zu Editor-Kontextmenüs  
 Um einen Befehl im Kontextmenü hinzugefügt haben, müssen Sie zunächst eine Gruppe von Menübefehlen, die einer bestimmten Gruppe definieren. Das folgende Beispiel stammt aus der VSCT-Datei, die als Teil der exemplarischen Vorgehensweise generiert [Exemplarische Vorgehensweise: Hinzufügen von Features zu einem benutzerdefinierten Editor](../extensibility/walkthrough-adding-features-to-a-custom-editor.md):  
  
 \<Menü-Guid = "GuidCustomEditorCmdSet" Id = "IDMX_RTF" Priorität = "0 x 0000" Type = "Kontext" >  
  
 \<Guid des übergeordneten = "GuidCustomEditorCmdSet" Id = "0" / >  
  
 \<Zeichenfolgen >  
  
 \<ButtonText > CustomEditor Kontextmenü\</ButtonText >  
  
 \<CommandName > CustomEditorContextMenu\</CommandName >  
  
 \</ Zeichenfolgen >  
  
 \</ Menü ">  
  
 \</-Menüs >  
  
 Der obige Text Fügt einen Befehl im Kontextmenü, mit dem Text **CustomEditor Kontextmenü**. Die Menü-GUID ist, dass für den Befehlssatz, mit diesem Editor erstellt wird, und der Typ ist "Kontext".  
  
 Sie können auch die vordefinierten Befehle verwenden, die nicht in der VSCT-Datei definiert werden müssen. Z. B. Wenn Sie die EditorPane.cs-Datei, die von der Visual Studio-Paket-Vorlage generiert untersuchen, finden Sie, die eine Reihe von vordefinierten Befehlen, wie z. B. <xref:Microsoft.VisualStudio.VSConstants.VSStd97CmdID> von definierten <xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>, in den Befehlshandler, z. B. die OnSelectAll-Methode behandelt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Befehle, Menüs und Symbolleisten](../extensibility/internals/commands-menus-and-toolbars.md)

