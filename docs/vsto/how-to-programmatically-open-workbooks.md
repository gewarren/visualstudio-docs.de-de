---
title: 'Vorgehensweise: Programmgesteuertes Öffnen von Arbeitsmappen'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening
- Excel [Office development in Visual Studio], opening workbooks
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ab91a1e9a89edee013b559f1653c1607e7b8c884
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53860948"
---
# <a name="how-to-programmatically-open-workbooks"></a>Vorgehensweise: Programmgesteuertes Öffnen von Arbeitsmappen
  Die <xref:Microsoft.Office.Interop.Excel.Workbooks> Sammlung in Microsoft Office Excel ermöglicht es mit allen geöffneten Arbeitsmappen funktionieren, und Öffnen von Arbeitsmappen.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="to-open-an-existing-workbook"></a>Um einer vorhandenen Arbeitsmappe zu öffnen.  
  
1.  Verwenden der <xref:Microsoft.Office.Interop.Excel.Workbooks.Open%2A> Methode der <xref:Microsoft.Office.Interop.Excel.Workbooks> Auflistung, die den Pfad zur Arbeitsmappe übergeben.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#2)]  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
 Für dieses Codebeispiel benötigen Sie Folgendes:  
  
-   Eine Arbeitsmappe mit dem Namen `YourWorkbook.xls` muss vorhanden sein, in ein Verzeichnis namens `Test` auf Laufwerk C.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Arbeitsmappen](../vsto/working-with-workbooks.md)   
 [Vorgehensweise: Programmgesteuertes Öffnen von Textdateien als Arbeitsmappen](../vsto/how-to-programmatically-open-text-files-as-workbooks.md)   
 [Vorgehensweise: Programmgesteuertes Erstellen neuer Arbeitsmappen](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [Vorgehensweise: Programmgesteuertes Speichern von Arbeitsmappen](../vsto/how-to-programmatically-save-workbooks.md)   
 [Vorgehensweise: Programmgesteuertes Schließen von Arbeitsmappen](../vsto/how-to-programmatically-close-workbooks.md)   
 [Einschränkungen für programmgesteuerte Aufgaben von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Optionaler Parameter in Office-Projektmappen](../vsto/optional-parameters-in-office-solutions.md)   
 [Hostelemente und Host-Steuerelementen (Übersicht)](../vsto/host-items-and-host-controls-overview.md)  
