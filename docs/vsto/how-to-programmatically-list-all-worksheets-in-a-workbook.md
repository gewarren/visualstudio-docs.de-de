---
title: 'Vorgehensweise: Programmgesteuertes Listen Sie aller Arbeitsblätter in einer Arbeitsmappe auf'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, listing worksheets
- worksheets, listing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2cab3547bb23aa563e2c6b5bfe6a82a93fd5e29e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53928723"
---
# <a name="how-to-programmatically-list-all-worksheets-in-a-workbook"></a>Vorgehensweise: Programmgesteuertes Listen Sie aller Arbeitsblätter in einer Arbeitsmappe auf
  Die <xref:Microsoft.Office.Interop.Excel.Workbook>-Klasse stellt ein <xref:Microsoft.Office.Interop.Excel.Worksheets>-Objekt bereit. Dieses Objekt enthält eine Auflistung aller <xref:Microsoft.Office.Interop.Excel.Worksheet>-Objekte in der Arbeitsmappe.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="to-list-all-existing-worksheets-in-a-workbook-in-a-document-level-customization"></a>So listen Sie alle vorhandenen Arbeitsblätter einer Arbeitsmappe in einer Anpassung auf Dokumentenebene auf.  
  
1.  Durchlaufen Sie die <xref:Microsoft.Office.Interop.Excel.Worksheets>-Auflistung, und senden Sie mit einem <xref:Microsoft.Office.Tools.Excel.NamedRange>-Steuerelement den Namen jedes Blattes an ein Zellenoffset.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#21](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomation#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#21)]  
  
## <a name="to-list-all-existing-worksheets-in-a-workbook-in-a-vsto-add-in"></a>So listen Sie alle vorhandenen Arbeitsblätter einer Arbeitsmappe in einem VSTO-Add-In auf  
  
1.  Durchlaufen Sie die <xref:Microsoft.Office.Interop.Excel.Worksheets>-Auflistung und senden Sie mit einem <xref:Microsoft.Office.Interop.Excel.Range>-Objekt den Namen jedes Blatts an ein Zellenoffset.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Arbeitsblättern](../vsto/working-with-worksheets.md)   
 [Vorgehensweise: Programmgesteuertes fügen Sie neuer Arbeitsblätter zu Arbeitsmappen hinzu](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [Vorgehensweise: Programmgesteuertes Verschieben von Arbeitsblättern in Arbeitsmappen](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Globaler Zugriff auf Objekte in Office-Projekten](../vsto/global-access-to-objects-in-office-projects.md)  
