---
title: ContentControl-Elemente
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.DropDownListContentControl
- VST.Toolbox.RichTextContentControl
- VST.Toolbox.PlainTextContentControl
- VST.Toolbox.ComboBoxContentControl
- VST.Toolbox.CCBuildingBlockGalleryContentControl
- VST.Toolbox.DatePickerContentControl
- VST.Toolbox.PictureContentControl
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document building blocks [Office development in Visual Studio]
- restricted permissions [Office development in Visual Studio]
- ComboBoxContentControl class
- PictureContentControl class
- PlainTextContentControl class
- Office documents [Office development in Visual Studio], restricted permissions
- RichTextContentControl class
- content controls [Office development in Visual Studio]
- building block gallery [Office development in Visual Studio]
- controls [Office development in Visual Studio], content controls
- GroupContentControl class
- documents [Office development in Visual Studio], restricted permissions
- DropDownListContentControl class
- DatePickerContentControl class
- data binding [Office development in Visual Studio], content controls
- content controls [Office development in Visual Studio], about content controls
- custom XML parts, content controls
- templates [Office development in Visual Studio], content controls
- BuildingBlockGalleryContentControl class
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: b1656f40cd0d75c73f9f1e4b3a74a6f2b7e7ad0e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53956543"
---
# <a name="content-controls"></a>ContentControl-Elemente
  Inhaltssteuerelemente bieten Ihnen eine Möglichkeit, Dokumente und Vorlagen zu entwerfen, die die folgenden Funktionen aufweisen:  
  
- Eine Benutzeroberfläche (UI), die über verwaltete Eingaben wie ein Formular verfügt.  
  
- Einschränkungen, die verhindern, dass Benutzer geschützte Abschnitte des Dokuments oder der Vorlage bearbeiten können. Weitere Informationen finden Sie unter [Teilen von Dokumenten mithilfe von Inhaltssteuerelementen schützen](#Protection).  
  
- Datenbindung an eine Datenquelle. Weitere Informationen finden Sie unter [Binden von Daten an Inhaltssteuerelemente](#DataBinding).  
  
  [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
  ![Link zum Video](../vsto/media/playvideo.gif "Link zum Video") eine entsprechende Videodemo finden Sie unter [Binden von Daten an Word 2007-Inhaltssteuerelemente mit Visual Studio Tools for Office System (3.0)](http://go.microsoft.com/fwlink/?LinkId=136785).  
  
## <a name="overview-of-content-controls"></a>Übersicht über Inhaltssteuerelemente  
 Inhaltssteuerelemente stellen eine Benutzeroberfläche bereit, die für Benutzereingaben und Druck optimiert ist. Wenn Sie einem Dokument ein Inhaltssteuerelement hinzufügen, wird das Steuerelement durch einen Rahmen, einen Titel und temporären Text identifiziert, der Anweisungen für den Benutzer bereitstellen kann. Der Rahmen und der Titel des Steuerelements werden nicht in gedruckten Versionen des Dokuments angezeigt.  
  
 Wenn Sie z. B. möchten, dass der Benutzer ein Datum in einem Abschnitt Ihres Dokuments eingibt, können Sie dem Dokument ein Datumsauswahl-Inhaltssteuerelement hinzufügen. Wenn Benutzer auf das Steuerelement klicken, wird die Datumsauswahl-Standardbenutzeroberfläche angezeigt. Sie können die Eigenschaften des Steuerelements auch so festlegen, dass der regionale Kalender festgelegt wird, der angezeigt wird, und Sie können das Datumsformat angeben. Nachdem der Benutzer ein Datum ausgewählt hat, wird die Benutzeroberfläche des Steuerelements ausgeblendet, und nur das Datum wird angezeigt, wenn der Benutzer das Dokument druckt.  
  
 Inhaltssteuerelemente unterstützen Sie auch bei den folgenden Aufgaben:  
  
- Verhindern, dass Benutzer Teile eines Dokuments bearbeiten oder löschen. Dies ist sinnvoll, wenn Informationen in einem Dokument oder einer Vorlage vorhanden sind, die Benutzer lesen, jedoch nicht bearbeiten können sollen, oder wenn Benutzer Steuerelemente bearbeiten, jedoch nicht löschen dürfen.  
  
- Binden von Teilen eines Dokuments oder einer Vorlage an Daten. Sie können Inhaltssteuerelementen an Datenbankfelder, verwaltete Objekte in [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)], XML-Elemente, die im Dokument gespeichert sind, und andere Datenquellen binden.  
  
  In Projekten auf Dokumentebene können Sie dem Dokument Inhaltssteuerelemente zur Entwurfszeit oder zur Laufzeit hinzufügen. In VSTO-Add-In-Projekten können Sie einem beliebigen geöffneten Dokument zur Laufzeit Inhaltssteuerelemente hinzufügen. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Inhaltssteuerelementen zu Word-Dokumenten](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
> [!NOTE]  
>  Sie können Inhaltssteuerelemente nur in Dokumenten verwenden, die im Open XML-Format gespeichert werden. Können keine ContentControl-Elemente in Dokumenten, die in das Word 97-2003-Dokument gespeichert werden (*.doc*) Format.  
  
## <a name="types-of-content-controls"></a>Typen von Inhaltssteuerelementen  
 Es gibt neun verschiedene Typen von Inhaltssteuerelementen, die Sie Dokumenten hinzufügen können. Die meisten der Inhaltssteuerelemente besitzen einen entsprechenden Typ im Namespace <xref:Microsoft.Office.Tools.Word>. Sie können auch einen generischen Namespace <xref:Microsoft.Office.Tools.Word.ContentControl> verwenden, der eines der verfügbaren Inhaltssteuerelemente darstellen kann. Eine exemplarische Vorgehensweise, die zeigt, wie die einzelnen verfügbaren Inhaltssteuerelemente verwendet werden, finden Sie unter [Exemplarische Vorgehensweise: Erstellen Sie eine Vorlage mithilfe von Inhaltssteuerelementen](../vsto/walkthrough-creating-a-template-by-using-content-controls.md).  
  
### <a name="build-block-gallery"></a>Erstellen Sie die Block-Katalog  
 Ein Bausteinkatalog ermöglicht Benutzern die Auswahl aus einer Liste von *Dokumentbausteinen* in ein Dokument eingefügt. Ein Dokumentbaustein ist ein Inhaltselement, das erstellt wurde, um mehrere Male verwendet zu werden, z. B. eine allgemeine Titelseite, eine formatierte Tabelle oder ein Header . Weitere Informationen finden Sie unter dem <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl>-Typ. Weitere Informationen zu Bausteinen finden Sie unter [Neuigkeiten für Entwickler in Word 2007](/previous-versions/office/developer/office-2007/bb266218(v=office.12)).  
  
### <a name="check-box"></a>Kontrollkästchen  
 Ein Kontrollkästchen stellt eine Benutzeroberfläche zur Verfügung, die einen binären Zustand darstellt: aktiviert oder deaktiviert.  
  
 Im Gegensatz zu anderen Typen von Inhaltssteuerelementen stellt die [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] keinen bestimmten Typ bereit, der ein Kontrollkästchen-Inhaltssteuerelement darstellt. Es gibt also keinen `CheckBoxContentControl`-Typ. Sie können jedoch trotzdem ein Kontrollkästchen-Inhaltssteuerelement erstellen, indem Sie ein generisches <xref:Microsoft.Office.Tools.Word.ContentControl> einem Dokument programmgesteuert hinzufügen. Weitere Informationen finden Sie unter [Kontrollkästchen-Inhaltssteuerelemente in Word-Projekten](#checkbox).  
  
### <a name="combo-box"></a>Kombinationsfeld  
 Ein Kombinationsfeld zeigt eine Liste von Elementen an, die Benutzer auswählen können. Im Gegensatz zu einer Dropdownliste ermöglicht das Kombinationsfeld das Hinzufügen eigener Elemente. Weitere Informationen finden Sie unter dem <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>-Typ.  
  
### <a name="date-picker"></a>Datumsauswahl  
 Eine Datumsauswahl stellt eine Kalenderbenutzeroberfläche zum Auswählen eines Datums zur Verfügung. Der Kalender wird angezeigt, wenn der Endbenutzer auf den Dropdownpfeil im Steuerelement klickt. Sie können regionale Kalender und verschiedene Datumsformate verwenden. Weitere Informationen finden Sie unter dem <xref:Microsoft.Office.Tools.Word.DatePickerContentControl>-Typ.  
  
### <a name="drop-down-list"></a>Dropdownliste  
 Eine Dropdownliste zeigt eine Liste von Elementen an, die Benutzer auswählen können. Im Gegensatz zu einem Kombinationsfeld ermöglicht die Dropdownliste Benutzern nicht das Hinzufügen oder Bearbeiten von Elementen. Weitere Informationen finden Sie unter dem <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>-Typ.  
  
### <a name="group"></a>Gruppieren  
 Ein Gruppensteuerelement definiert einen geschützten Bereich eines Dokuments, den Benutzer weder bearbeiten noch löschen können. Ein Gruppensteuerelement kann beliebige Dokumentelemente enthalten, z. B. Text, Tabellen, Grafiken und andere Inhaltssteuerelemente. Weitere Informationen finden Sie unter dem <xref:Microsoft.Office.Tools.Word.GroupContentControl>-Typ.  
  
### <a name="picture"></a>Picture  
 Ein Bildsteuerelement zeigt ein Bild an. Sie können das Bild zur Entwurfszeit oder zur Laufzeit angeben, oder Benutzer können auf dieses Steuerelement klicken, um ein Bild auszuwählen, das in das Dokument eingefügt werden soll. Weitere Informationen finden Sie unter dem <xref:Microsoft.Office.Tools.Word.PictureContentControl>-Typ.  
  
### <a name="rich-text"></a>Rich-text  
 Ein Rich-Text-Steuerelement enthält Text oder andere Elemente, z. B. Tabellen, Bilder oder andere Inhaltssteuerelemente. Weitere Informationen finden Sie unter dem <xref:Microsoft.Office.Tools.Word.RichTextContentControl>-Typ.  
  
### <a name="plain-text"></a>Nur-Text  
 Ein Nur-Text-Steuerelement enthält Text. Ein Nur-Text-Steuerelement kann keine anderen Elemente (z. B. Tabellen, Bilder oder andere Inhaltssteuerelemente) enthalten. Darüber hinaus weist der gesamte Text in einem Nur-Text-Steuerelement die gleiche Formatierung auf. Wenn Sie z. B. ein Wort in einem Satz kursiv formatieren, das sich in einem Nur-Text-Steuerelement befindet, wird der gesamte Text im Steuerelement kursiv formatiert. Weitere Informationen finden Sie unter dem <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>-Typ.  
  
### <a name="generic-content-control"></a>Generisches Inhaltssteuerelement  
 Ein generisches Inhaltssteuerelement ist ein <xref:Microsoft.Office.Tools.Word.ContentControl>-Objekt, das jeden der verfügbaren Typen von Steuerelementen darstellen kann. Sie können ein <xref:Microsoft.Office.Tools.Word.ContentControl>-Objekt so ändern, dass es sich wie ein anderer Typ von Inhaltssteuerelement verhält, indem Sie die Eigenschaft <xref:Microsoft.Office.Tools.Word.ContentControl.Type%2A> verwenden. Wenn Sie z. B. ein <xref:Microsoft.Office.Tools.Word.ContentControl>-Objekt erstellen, das ein Nur-Text-Steuerelement darstellt, können Sie dieses zur Laufzeit so ändern, dass es sich wie ein Kombinationsfeld verhält.  
  
 Sie können <xref:Microsoft.Office.Tools.Word.ContentControl>-Objekte nur zur Laufzeit erstellen, nicht zur Entwurfszeit. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Inhaltssteuerelementen zu Word-Dokumenten](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
## <a name="common-features-of-content-controls"></a>Allgemeine Funktionen von Inhaltssteuerelementen  
 Die meisten Inhaltssteuerelemente verwenden eine Sammlung von Elementen gemeinsam, die Sie verwenden können, um allgemeine Aufgaben auszuführen. In der folgenden Tabelle werden einige der Aufgaben beschrieben, die Sie mithilfe dieser Elemente ausführen können.  
  
|Aufgabe:|Vorgehensweise:|  
|--------------------|--------------|  
|Abrufen oder Festlegen des Texts, der im Steuerelement angezeigt wird.|Verwenden der **Text** Eigenschaft. **Hinweis**:  Die Typen <xref:Microsoft.Office.Tools.Word.PictureContentControl> und <xref:Microsoft.Office.Tools.Word.ContentControl> verfügen nicht über diese Eigenschaft.|  
|Abrufen oder Festlegen des temporären Texts, der im Steuerelement angezeigt wird, bis ein Benutzer das Steuerelement bearbeitet, das Steuerelement mit Daten aus einer Datenquelle aufgefüllt wird oder der Inhalt des Steuerelements gelöscht wird.|Verwenden der **PlaceholderText** Eigenschaft. **Hinweis**:  Der <xref:Microsoft.Office.Tools.Word.PictureContentControl>-Typ verfügt nicht über diese Eigenschaft.|  
|Abrufen oder Festlegen des Titels, der im Rahmen des Inhaltssteuerelements angezeigt wird, wenn der Benutzer darauf klickt.|Verwenden der **Titel** Eigenschaft.|  
|Automatisches Entfernen des Steuerelement aus dem Dokument, nachdem der Benutzer das Steuerelement bearbeitet hat. (Der Text im Steuerelement verbleibt im Dokument.)|Verwenden der **temporäre** Eigenschaft.|  
|Ausführen von Code, wenn der Benutzer im Inhaltssteuerelement klickt oder wenn der Cursor programmgesteuert in das Inhaltssteuerelement verschoben wird.|Behandeln des <xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering>-Ereignisses des Steuerelements.|  
|Ausführen von Code, wenn der Benutzer außerhalb des Inhaltssteuerelements klickt oder der Cursor programmgesteuert aus dem Inhaltssteuerelement verschoben wird.|Behandeln des <xref:Microsoft.Office.Tools.Word.ContentControlBase.Exiting>-Ereignisses des Steuerelements.|  
|Ausführen von Code, nachdem das Inhaltssteuerelement als Ergebnis eines Vorgangs "Wiederholen" oder "Rückgängig" dem Dokument hinzugefügt wurde.|Behandeln des <xref:Microsoft.Office.Tools.Word.ContentControlBase.Added>-Ereignisses des Steuerelements.|  
|Ausführen von Code, kurz bevor das Inhaltssteuerelement aus dem Dokument gelöscht wird.|Behandeln des <xref:Microsoft.Office.Tools.Word.ContentControlBase.Deleting>-Ereignisses des Steuerelements.|  
  
##  <a name="Protection"></a> Schützen von Teilen von Dokumenten mithilfe von Inhaltssteuerelementen  
 Wenn Sie einen Teil eines Dokuments schützen, verhindern Sie dass Benutzer den Inhalt in diesem Teil des Dokuments ändern oder löschen können. Es gibt mehrere Möglichkeiten, wie Sie Teile eines Dokuments mithilfe von Inhaltssteuerelementen schützen können.  
  
 Wenn sich der Bereich, den Sie schützen möchten, innerhalb eines Inhaltssteuerelements befindet, können Sie Eigenschaften des Inhaltssteuerelements verwenden, um zu verhindern, dass Benutzer das Steuerelement bearbeiten oder löschen können:  
  
- Die **LockContents** Eigenschaft verhindert, dass Benutzer den Inhalt bearbeiten.  
  
- Die **LockContentControl** Eigenschaft verhindert, dass Benutzer das Steuerelement löschen.  
  
  Wenn sich der Bereich, den Sie schützen möchten, nicht innerhalb eines Inhaltssteuerelements befindet, oder wenn Sie einen Bereich schützen möchten, der Inhaltssteuerelemente und andere Inhaltstypen enthält, können Sie den gesamten Bereich in einem <xref:Microsoft.Office.Tools.Word.GroupContentControl> positionieren. Im Gegensatz zu anderen Inhaltssteuerelementen stellt ein <xref:Microsoft.Office.Tools.Word.GroupContentControl> keine Benutzeroberfläche zur Verfügung, die für den Benutzer sichtbar ist. Sein einziger Zweck besteht darin, einen Bereich zu definieren, den Benutzern nicht bearbeiten können.  
  
> [!NOTE]  
>  Wenn Sie ein <xref:Microsoft.Office.Tools.Word.GroupContentControl> erstellen, das eingebettete Inhaltssteuerelemente enthält, sind die eingebetteten Inhaltssteuerelemente nicht automatisch geschützt. Verwenden Sie die **LockContents** -Eigenschaft jedes eingebetteten Steuerelements verwenden, um zu verhindern, dass Benutzer ihren Inhalt zu bearbeiten.  
  
 Weitere Informationen zur Verwendung von Inhaltssteuerelementen zum Schützen von Teilen von Dokumenten finden Sie unter [Vorgehensweise: Schützen von Teilen von Dokumenten mithilfe von Inhaltssteuerelementen](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md).  
  
##  <a name="DataBinding"></a> Binden von Daten an Inhaltssteuerelemente  
 Sie können Daten in Dokumenten anzeigen, indem Sie ein Inhaltssteuerelement an eine Datenquelle binden. Wenn die Datenquelle aktualisiert wird, spiegelt das Inhaltssteuerelement die Änderungen. Sie können Änderungen auch in der Datenquelle speichern.  
  
 Inhaltssteuerelemente stellen die folgenden Datenbindungsoptionen zur Verfügung:  
  
- Sie können Inhaltssteuerelemente an Datenbankfelder oder verwaltete Objekte binden, indem Sie das gleiche Datenbindungsmodell wie Windows Forms verwenden.  
  
- Sie können Inhaltssteuerelemente an Elemente im XML-Elemente binden (auch als *benutzerdefinierte XML-Elemente*), die im Dokument eingebettet sind.  
  
  Einen Überblick über das Binden von Hoststeuerelementen in Office-Projektmappen mit Daten finden Sie unter [Binden von Daten an Steuerelemente in Office-Projektmappen](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
### <a name="use-the-windows-forms-data-binding-model"></a>Verwenden Sie das Windows Forms-Datenbindungsmodell verwendet  
 Die meisten Inhaltssteuerelemente unterstützen das einfache Datenbindungsmodell, das Windows Forms verwendet. Einfache Datenbindung bedeutet, dass ein Steuerelement an ein einzelnes Datenelement gebunden ist, z. B. an einen Wert in einer Spalte einer Datentabelle. Weitere Informationen finden Sie unter [Datenbindung und Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
 In Projekten auf Dokumentebene können Sie Daten an Inhaltssteuerelemente binden, indem Sie mit der **Datenquellen** -Fensters im [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Weitere Informationen zur Vorgehensweise beim Hinzufügen von datengebundenen Inhaltssteuerelementen für Dokumente finden Sie unter [Vorgehensweise: Auffüllen von Dokumenten mit Daten aus einer Datenbank](../vsto/how-to-populate-documents-with-data-from-a-database.md) und [Vorgehensweise: Auffüllen von Dokumenten mit Daten aus Objekten](../vsto/how-to-populate-documents-with-data-from-objects.md).  
  
 Die folgende Tabelle listet die Inhaltssteuerelemente, die Sie für jeden Datentyp in binden können die **Datenquellen** Fenster.  
  
|Datentyp|Standard-Inhaltssteuerelement|Andere Inhaltssteuerelemente, die an diesen Datentyp gebunden werden können|  
|---------------|-----------------------------|----------------------------------------------------------------|  
|<xref:System.Boolean><br /><br /> <xref:System.Byte><br /><br /> <xref:System.Char><br /><br /> <xref:System.Double><br /><br /> <xref:System.Enum><br /><br /> <xref:System.Guid><br /><br /> <xref:System.Int16><br /><br /> <xref:System.Int32><br /><br /> <xref:System.Int64><br /><br /> <xref:System.SByte><br /><br /> <xref:System.Single><br /><br /> <xref:System.String><br /><br /> <xref:System.TimeSpan><br /><br /> <xref:System.UInt16><br /><br /> <xref:System.UInt32><br /><br /> <xref:System.UInt64>|<xref:Microsoft.Office.Tools.Word.PlainTextContentControl>|<xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.DatePickerContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.RichTextContentControl>|  
|<xref:System.DateTime>|<xref:Microsoft.Office.Tools.Word.DatePickerContentControl>|<xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.PlainTextContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.RichTextContentControl>|  
|<xref:System.Drawing.Image><br /><br /> <xref:System.Byte>-Array|<xref:Microsoft.Office.Tools.Word.PictureContentControl>|Keine|  
  
 In Projekten auf Dokumentebene und VSTO-Add-In-Projekten können Sie ein Inhaltssteuerelement programmgesteuert an eine Datenquelle mithilfe der Methode <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> der Eigenschaft <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> des Steuerelements binden. Wenn Sie dies tun, übergeben Sie in der Zeichenfolge **Text** auf die *PropertyName* Parameter der <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> Methode. Die **Text** -Eigenschaft ist die Standard-Datenbindungseigenschaft von Inhaltssteuerelementen.  
  
 Inhaltssteuerelemente unterstützen auch bidirektionale Datenbindung, bei der Änderungen im Steuerelement in der Datenquelle aktualisiert werden. Weitere Informationen finden Sie unter [Vorgehensweise: Aktualisieren einer Datenquelle mit Daten eines Hoststeuerelements](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).  
  
> [!NOTE]  
>  Inhaltssteuerelemente unterstützen keine komplexe Datenbindung. Wenn Sie ein <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> oder <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> mithilfe des Windows Forms-Datenmodells an eine Datenquelle binden, wird Benutzern beim Klicken auf das Steuerelement nur ein einziger Wert angezeigt. Wenn Sie diese Steuerelemente an einen Satz von Datenwerten binden möchten, aus denen Benutzer auswählen können, können Sie diese Steuerelemente an Elemente in einem benutzerdefinierten XML-Abschnitt binden.  
  
### <a name="bind-content-controls-to-custom-xml-parts"></a>Binden von Inhaltssteuerelementen an benutzerdefinierte XML-Abschnitte  
 Sie können einige Inhaltssteuerelemente an Elemente in benutzerdefinierten XML-Abschnitten binden, die im Dokument eingebettet sind. Weitere Informationen zu benutzerdefinierten XML-Elementen, finden Sie unter [Übersicht über benutzerdefinierte XML-Abschnitte](../vsto/custom-xml-parts-overview.md).  
  
 Um ein Inhaltssteuerelement an ein Element in einem benutzerdefinierten XML-Abschnitt binden möchten, verwenden die **XMLMapping** -Eigenschaft des Steuerelements. Im folgenden Codebeispiel wird veranschaulicht, wie ein <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> an das Element `Price` unter dem Knoten `Product` in einem benutzerdefinierten XML-Abschnitt gebunden wird, der dem Dokument bereits hinzugefügt wurde.  
  
```vb  
plainTextContentControl1.XMLMapping.SetMapping("/Product/Price")  
```  
  
```csharp  
plainTextContentControl1.XMLMapping.SetMapping("/Product/Price", String.Empty, null);  
```  
  
 Eine exemplarische Vorgehensweise, die zum Binden von Inhaltssteuerelementen an benutzerdefinierte XML-Elemente im Detail veranschaulicht, finden Sie unter [Exemplarische Vorgehensweise: Binden von Inhaltssteuerelementen an benutzerdefinierte XML-Abschnitte](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md).  
  
 Wenn Sie ein Inhaltssteuerelement an einen benutzerdefinierten XML-Abschnitt binden, wird die bidirektionale Datenbindung automatisch aktiviert. Wenn ein Benutzer Text im Steuerelement bearbeitet, werden die entsprechenden XML-Elemente automatisch aktualisiert. Wenn Elementwerte in den benutzerdefinierten XML-Abschnitten geändert werden, zeigen die Inhaltssteuerelemente, die an die XML-Elemente gebunden sind, auf ähnliche Weise die neuen Daten an.  
  
 Sie können die folgenden Typen von Inhaltssteuerelementen an benutzerdefinierte XML-Abschnitte binden:  
  
-   <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.DatePickerContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.PictureContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>  
  
### <a name="data-bind-events-for-content-controls"></a>Ereignisse für Inhaltssteuerelemente Binden von Daten  
 Alle Inhaltssteuerelemente stellen einen Satz von Ereignissen bereit, die Sie behandeln können, um datenbezogene Aufgaben auszuführen. Sie können z. B. überprüfen, ob der Text in einem Steuerelement bestimmte Kriterien erfüllt, bevor die Datenquelle aktualisiert wird. Die folgende Tabelle listet die Inhaltssteuerelement-Ereignisse auf, die mit der Datenbindung zusammenhängen.  
  
|Aufgabe|event|  
|----------|-----------|  
|Ausführen von Code , kurz bevor Word automatisch den Text in einem Inhaltssteuerelement aktualisiert, das an einen benutzerdefinierten XML-Abschnitt gebunden ist.|<xref:Microsoft.Office.Tools.Word.ContentControlBase.ContentUpdating>|  
|Ausführen von Code, kurz bevor Word automatisch die Daten in einem benutzerdefinierten XML-Abschnitt aktualisiert, der an ein Inhaltssteuerelement gebunden ist (d. h. nachdem sich der Text im Inhaltssteuerelement ändert).|<xref:Microsoft.Office.Tools.Word.ContentControlBase.StoreUpdating>|  
|Ausführen Ihres eigenen Codes, um den Inhalt des Steuerelements gemäß benutzerdefinierten Kriterien zu überprüfen.|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Validating>|  
|Ausführen von Code, nachdem der Inhalt des Steuerelements erfolgreich überprüft wurde.|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Validated>|  
  
## <a name="limitations-of-content-controls"></a>Einschränkungen von Inhaltssteuerelementen  
 Wenn Sie Inhaltssteuerelemente in Office-Projekten verwenden, beachten Sie auf die folgenden Einschränkungen.  
  
### <a name="behavior-differences-between-design-time-and-runtime"></a>Unterschiede im Verhalten zwischen Entwurfs- und Laufzeit  
 Viele der Einschränkungen, die Microsoft Office Word-Inhaltssteuerelementen zur Laufzeit auferlegt, werden zur Entwurfszeit nicht erzwungen. Beim Entwerfen der Benutzeroberfläche einer Projektmappe auf Dokumentebene in [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] sollten Sie Inhaltssteuerelemente nur auf eine Weise ändern, die zur Laufzeit unterstützt wird.  
  
 Wenn Sie ein Inhaltssteuerelement zur Entwurfszeit auf eine Weise ändern, die das Steuerelement zur Laufzeit nicht unterstützt, warnt Sie der [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]-Designer nicht vor den nicht unterstützten Änderungen. Allerdings wird beim Debuggen oder Ausführen des Projekts oder beim Speichern und erneuten Öffnen des Projekts von Word eine Fehlermeldung angezeigt und die Berechtigung zum Reparieren des Dokuments angefordert. Wenn Sie das Dokument reparieren, entfernt Word alle nicht unterstützten Inhalte und Formatierungen aus dem Steuerelement.  
  
 Word verhindert z. B. nicht, dass Sie einem <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> zur Entwurfszeit eine Tabelle hinzufügen. Da <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>-Objekte jedoch zur Laufzeit keine Tabellen enthalten dürfen, zeigt Word eine Fehlermeldung an, wenn das Dokument geöffnet wird.  
  
 Beachten Sie außerdem, dass viele Eigenschaften, die das Verhalten von Inhaltssteuerelementen definieren, zur Entwurfszeit keine Auswirkungen besitzen. Wenn Sie festlegen, z. B. die **LockContents** Eigenschaft eines Inhaltssteuerelements, **"true"** zur Entwurfszeit können Sie weiterhin Text im Steuerelement im Bearbeiten der [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Designer. Diese Eigenschaft verhindert nur, dass Benutzer das Steuerelement zur Laufzeit bearbeiten können.  
  
### <a name="event-limitations"></a>Ereigniseinschränkungen  
 Inhaltssteuerelemente stellen kein Ereignis zur Verfügung, das ausgelöst wird, wenn der Benutzer Text oder andere Elemente im Steuerelement ändert. Es ist z. B. kein Ereignis vorhanden, das ausgelöst wird, wenn ein Benutzer ein anderes Element in einem <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> oder <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> auswählt.  
  
 Wenn Sie ermitteln möchten, wenn ein Benutzer den Inhalt eines Inhaltssteuerelements bearbeitet, können Sie das Steuerelement an einen benutzerdefinierten XML-Abschnitt binden und dann das Ereignis <xref:Microsoft.Office.Tools.Word.ContentControlBase.StoreUpdating> behandeln. Dieses Ereignis wird ausgelöst, wenn der Benutzer den Inhalt eines Steuerelements ändert, das an einen benutzerdefinierten XML-Abschnitt gebunden ist. Eine exemplarische Vorgehensweise, die zeigt, wie Sie ein Inhaltssteuerelement an einen benutzerdefinierten XML-Abschnitt binden, finden Sie unter [Exemplarische Vorgehensweise: Binden von Inhaltssteuerelementen an benutzerdefinierte XML-Abschnitte](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md).  
  
###  <a name="checkbox"></a> Aktivieren Sie das Kontrollkästchen-Inhaltssteuerelemente in Word-Projekten  
 Mit Word 2010 wurde eine neue Art von Steuerelement eingeführt, das ein Kontrollkästchen darstellt. Allerdings die [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] bietet keinen entsprechenden CheckBoxContentControl-Typ für die Sie in Office-Projekten verwenden. Verwenden Sie zum Erstellen eines Kontrollkästchen-Inhaltssteuerelements in einem [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]- oder Word 2010-Projekt die Methode <xref:Microsoft.Office.Tools.Word.ControlCollection.AddContentControl%2A> zum Erstellen eines <xref:Microsoft.Office.Tools.Word.ContentControl>-Objekts, und übergeben Sie den Wert <xref:Microsoft.Office.Interop.Word.WdContentControlType.wdContentControlCheckBox> an die Methode, um ein Kontrollkästchen-Inhaltssteuerelement anzugeben. Das folgende Codebeispiel veranschaulicht, wie Sie dabei vorgehen:  
  
 [!code-vb[Trin_ContentControlReference#800](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/checkbox.vb#800)]
 [!code-csharp[Trin_ContentControlReference#800](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/checkbox.cs#800)]  
  
## <a name="see-also"></a>Siehe auch  
 [Automatisieren von Word mithilfe von erweiterten Objekten](../vsto/automating-word-by-using-extended-objects.md)   
 [Vorgehensweise: Hinzufügen von Inhaltssteuerelementen zu Word-Dokumenten](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Exemplarische Vorgehensweise: Erstellen Sie eine Vorlage mithilfe von Inhaltssteuerelementen](../vsto/walkthrough-creating-a-template-by-using-content-controls.md)   
 [Daten in Office-Projektmappen](../vsto/data-in-office-solutions.md)   
 [Binden von Daten an Steuerelemente in Office-Projektmappen](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Einschränkungen für programmgesteuerte Aufgaben von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
