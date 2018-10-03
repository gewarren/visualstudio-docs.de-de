---
title: XML-Dokumenteigenschaften, Eigenschaftenfenster | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dbb34d9-02ea-4201-b445-c98a0eb0d6db
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7145c81a87235d37a0e4825509e7f8fb94ab0f7c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47524239"
---
# <a name="xml-document-properties-properties-window"></a>XML-Dokumenteigenschaften, Eigenschaftenfenster
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [XML-Dokumenteigenschaften, Eigenschaftenfenster](https://docs.microsoft.com/visualstudio/xml-tools/xml-document-properties-properties-window).  
  
  
Die **Eigenschaften** Eigenschaftenfenster liefert grundlegende Informationen über das Dokument, das in der XML-Editor aktiv ist. Die verfügbaren Eigenschaften sind vom Typ des gerade aktiven XML-Dokuments abhängig.  
  
> [!NOTE]
>  Alle XML-Dokumenteigenschaften werden in der Projektmappe gespeichert. Dadurch müssen Sie diese Werte nicht erneut eingeben, wenn Sie die Projektmappe das nächste Mal öffnen.  
  
 **Codierung**  
 Die Zeichencodierung für die Datei. Wenn diese Eigenschaft geändert wird, wird auch das Codierungsattribut für die XML-Deklaration geändert und umgekehrt. Die neue Codierung wird beim Speichern der Datei zum Codieren der Datei verwendet.  
  
 **Eingabe**  
 Das dem XSLT-Stylesheet zugeordnete Eingabedokument. Hiermit wird durch die **ShowXSLT Ausgabe** Befehl. Ein Dokument mit der Schaltfläche ausgewählt werden kann (**...** ) Schaltfläche.  
  
 Diese Eigenschaft ist nur sichtbar, wenn derzeit eine XSLT-Datei im Editor-Fenster aktiv ist.  
  
 **Ausgabe**  
 Die bei der Transformation eines XML-Dokuments generierte Datei.  
  
 Wenn keine Datei angegeben wurde, wird aufgrund des `method`-Attributs für das `xsl:output`-Element, das die Dateierweiterung festlegt, ein Standarddateiname generiert. Die Standarddatei befindet sich im temporären Verzeichnis des aktuellen Benutzers.  
  
 **Schemas**  
 Die für die Validierung verwendeten Schemata. Die Schaltfläche öffnet die **XSD-Schemas** das Dialogfeld zum Auswählen der zu verwendenden Schemas verwendet werden kann.  
  
 Sie können den Pfad zu den Schemata auch eingeben. Wenn mehrere Schemata angegeben sind, muss jeder Schemapfad in doppelte Anführungszeichen eingeschlossen werden.  
  
 **Stylesheet**  
 Die XSLT-Datei, die verwendet wird, um das Dokument zu transformieren. wenn die **XSLT-Ausgabe anzeigen** -Befehl wird verwendet. Wenn dieses Feld leer, wenn ist die **XSLT-Ausgabe anzeigen** -Befehl wird verwendet, verwendet der Editor des Werts der `xml-stylesheet` -verarbeitungsanweisung des Dokuments, oder es fordert Sie zur Eingabe des Dateinamens.  
  
 Beim Bearbeiten einer XSLT-Datei kann diese Eigenschaft verwendet werden, um anzugeben, dass ein anderes Stylesheet sollte verwendet werden, wenn die **XSLT-Ausgabe anzeigen** oder **XSLT Debuggen** Befehl aktiviert ist. Dies kann z. B. beim Bearbeiten eines Stylesheets der Fall sein, das in einem übergeordneten Stylesheet enthalten ist.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Editor](../xml-tools/xml-editor.md)   
 [Komponenten des XML-Editors](../xml-tools/xml-editor-components.md)


