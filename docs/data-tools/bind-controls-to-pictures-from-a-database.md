---
title: Binden von Steuerelementen an Bilder aus einer Datenbank
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- images [Visual Basic], displaying on Windows Forms
- data binding [Windows Forms], pictures
- images [Visual Basic], data binding
- pictures, data binding
- pictures, dragging from Data Sources window
- Data Sources Window, setting controls to display images
- PictureBox control [Windows Forms], data binding
- images [Visual Basic], dragging from Data Sources window
ms.assetid: 9748815e-3556-49e8-86b1-c6aa593c6163
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d93ca95a67bc3816d8d65a799282dc6c7969e093
ms.sourcegitcommit: 81e9d90843ead658bc73b30c869f25921d99e116
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2018
ms.locfileid: "52304916"
---
# <a name="bind-controls-to-pictures-from-a-database"></a>Binden von Steuerelementen an Bilder aus einer Datenbank

Sie können im Datenquellenfenster** ein Bild in einer Datenbank an ein Steuerelement in der Anwendung binden. Zum Beispiel kann ein Bild an ein <xref:System.Windows.Controls.Image>-Steuerelement in einer WPF-Anwendung oder an ein <xref:System.Windows.Forms.PictureBox>-Steuerelement in einer Windows Forms-Anwendung gebunden werden.

Bilder in einer Datenbank werden in der Regel als Bytearrays gespeichert. Für Elemente im Datenquellenfenster **, die als Bytearrays gespeichert werden, wird der Steuerelementtyp standardmäßig auf Keine** festgelegt, da Bytearrays sämtliche Objekte von einem einfachen Bytearray bis zur ausführbaren Datei einer großen Anwendung enthalten können. Um für ein Bytearrayelement im Datenquellenfenster** ein datengebundenes Steuerelement zu erstellen, das ein Bild darstellt, muss das zu erstellende Steuerelement ausgewählt werden.

In der folgenden Prozedur wird davon ausgegangen, dass das Datenquellenfenster** bereits mit einem an das Bild gebundenen Element gefüllt ist.

## <a name="to-bind-a-picture-in-a-database-to-a-control"></a>So binden Sie ein Bild in einer Datenbank an ein Steuerelement

1.  Stellen Sie sicher, dass die Entwurfsoberfläche, der Sie das Steuerelement hinzufügen möchten, im WPF-Designer oder im Windows Forms-Designer geöffnet ist.

2.  Erweitern Sie im Datenquellenfenster** die gewünschte Tabelle oder das gewünschte Objekt, sodass die Spalten bzw. Eigenschaften angezeigt werden.

   > [!TIP]
   > Wenn die **Datenquellen** Fenster nicht geöffnet ist, öffnen Sie es durch Auswählen von **Ansicht** > **Other Windows** > **Datenquellen**.

3.  Wählen Sie die Spalte oder die Eigenschaft aus, die die Bilddaten enthält, und wählen Sie eines der folgenden Steuerelemente aus der Dropdown-Steuerelementliste aus:

    - Wenn der WPF-Designer geöffnet ist, wählen Sie Bild** aus.

    - Wenn der Windows Forms-Designer geöffnet ist, wählen Sie PictureBox** aus.

    - Sie können auch ein anderes Steuerelement auswählen, das die Datenbindung unterstützt und Bilder anzeigen kann. Wenn das Steuerelement, das Sie verwenden möchten, nicht in der Liste der verfügbaren Steuerelemente enthalten ist, können Sie es der Liste hinzufügen und es anschließend auswählen. Weitere Informationen finden Sie unter [Hinzufügen benutzerdefinierter Steuerelemente zum Datenquellenfenster](../data-tools/add-custom-controls-to-the-data-sources-window.md).

## <a name="see-also"></a>Siehe auch

- [Binden von WPF-Steuerelementen an Daten in Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)