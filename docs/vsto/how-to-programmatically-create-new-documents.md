---
title: 'Vorgehensweise: Programmgesteuertes Erstellen neuer Dokumente'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- templates [Office development in Visual Studio], custom document
- Word [Office development in Visual Studio], creating documents
- documents [Office development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3b5b7766e58cf420d171c1390546957eba1817c1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53918809"
---
# <a name="how-to-programmatically-create-new-documents"></a>Vorgehensweise: Programmgesteuertes Erstellen neuer Dokumente
  Wenn Sie ein Dokument programmgesteuert erstellen, ist das neue Dokument ein systemeigenes <xref:Microsoft.Office.Interop.Word.Document>-Objekt. Dieses Objekt verfügt nicht über die zusätzlichen Ereignisse und Datenbindungsfunktionen eines <xref:Microsoft.Office.Tools.Word.Document>-Hostelements. Weitere Informationen finden Sie unter [programmgesteuerte Einschränkungen von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Wenn Sie ein Projekt auf Dokumentebene entwickeln, können Sie Ihrem Projekt nicht programmgesteuert <xref:Microsoft.Office.Tools.Word.Document>-Hostelemente hinzufügen. In einem VSTO-Add-In-Projekt können Sie beliebige <xref:Microsoft.Office.Interop.Word.Document>-Objekte zur Laufzeit in <xref:Microsoft.Office.Tools.Word.Document>-Hostelements konvertieren. Weitere Informationen finden Sie unter [Erweitern von Word-Dokumenten und Excel-Arbeitsmappen in VSTO-Add-ins zur Laufzeit](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="to-create-a-new-document-based-on-the-normal-template"></a>So erstellen Sie ein neues Dokument basierend auf der Vorlage "NORMAL.DOT"  
  
-   Verwenden Sie die Methode <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> der Auflistung <xref:Microsoft.Office.Interop.Word.Documents> zum Erstellen eines neuen Dokuments auf der Grundlage der Vorlage "NORMAL.DOT". Wenn Sie dieses Codebeispiel verwenden möchten, führen Sie es aus der Klasse `ThisDocument` oder `ThisAddIn` in Ihrem Projekt aus.  
  
     [!code-vb[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#1)]
     [!code-csharp[Trin_VstcoreWordAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#1)]  
  
## <a name="use-custom-templates"></a>Verwenden von benutzerdefinierten Vorlagen  
 Die <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> Methode verfügt über einen optionalen *Vorlage* Argument zum Erstellen eines neuen Dokuments auf Grundlage einer anderen Vorlage als die Vorlage "Normal.dot". Sie müssen den Dateinamen und den vollqualifizierten Pfad der Vorlage angeben.  
  
### <a name="to-create-a-new-document-based-on-a-custom-template"></a>So erstellen Sie ein neues Dokument basierend auf einer benutzerdefinierten Vorlage  
  
-   Rufen Sie die Methode <xref:Microsoft.Office.Interop.Word.Documents.Add%2A> der Auflistung <xref:Microsoft.Office.Interop.Word.Documents> auf, und geben Sie den Pfad zur Vorlage an. Wenn Sie dieses Codebeispiel verwenden möchten, führen Sie es aus der Klasse `ThisDocument` oder `ThisAddIn` in Ihrem Projekt aus.  
  
     [!code-vb[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#2)]
     [!code-csharp[Trin_VstcoreWordAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Programmgesteuertes Öffnen vorhandener Dokumente](../vsto/how-to-programmatically-open-existing-documents.md)   
 [Hostelemente und Host-Steuerelementen (Übersicht)](../vsto/host-items-and-host-controls-overview.md)   
 [Einschränkungen für programmgesteuerte Aufgaben von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Optionaler Parameter in Office-Projektmappen](../vsto/optional-parameters-in-office-solutions.md)  
