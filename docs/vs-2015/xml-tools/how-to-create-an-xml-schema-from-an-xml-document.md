---
title: 'Vorgehensweise: erstellen ein XML-Schemas aus einem XML-Dokument | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 84e09b4f7dcdcb21c2928ba0d80fb6ae27e90dc7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49889567"
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>Gewusst wie: Erstellen eines XML-Schemas aus einem XML-Dokument
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Der XML-Editor ermöglicht Ihnen, ein XSD-Schema (XML Schema Definition Language) aus einem XML-Dokument zu erstellen. Das XML-Instanzdokument bestimmt wie folgt, auf welche Weise das Schema generiert wird:  
  
- Wenn dem XML-Dokument kein Schema oder keine DTD (Document Type Definition) zugeordnet ist, wird mithilfe der Daten im XML-Dokument ein neues XML-Schema abgeleitet.  
  
- Wenn das XML-Dokument eine zugeordnete DTD enthält, werden die externe DTD und die interne Teilmenge in ein entsprechendes XML-Schema konvertiert.  
  
- Wenn das XML-Dokument ein XDR-Inlineschema (XML-Data Reduced) enthält, wird das XDR-Schema in ein entsprechendes XML-Schema konvertiert.  
  
  Mit den erstellten Schemata wird anschließend IntelliSense für das XML-Dokument bereitgestellt.  
  
  Weitere Informationen zum schemarückschlussmodul finden Sie unter [Herleiten eines XML-Schemas](http://msdn.microsoft.com/library/b18e7ffd-3c04-482d-9934-ba2f6a59b2c9).  
  
### <a name="to-create-an-xml-schema"></a>So erstellen Sie ein XML-Schema  
  
1.  Laden Sie ein XML-Instanzdokument im XML-Editor.  
  
2.  Klicken Sie auf die **Create Schema** Schaltfläche der **Symbolleiste**.  
  
     Ein XML-Schemadokument wird für jeden im XML-Instanzdokument gefundenen Namespace erstellt und geöffnet. Jedes Schema wird als sonstige temporäre Datei geöffnet.  
  
     Die Schemata können auf Datenträger gespeichert, dem Projekt hinzugefügt oder verworfen werden.  
  
    > [!NOTE]
    >  Die **Create Schema** Befehl ist auch verfügbar im Kontextmenü des XML-Editor und wählen Sie unter den **XML** Menü.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Editor](../xml-tools/xml-editor.md)



