---
title: 'Vorgehensweise: Angeben von Symboldateispeicherorten über die Befehlszeile | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aa067bb-e8bf-4081-aff0-cfbcf65934a0
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d138166bc0dfdf93df5d4e340fc0d0a62d1828b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51721188"
---
# <a name="how-to-specify-symbol-file-locations-from-the-command-line"></a>Gewusst wie: Angeben von Symboldateispeicherorten über die Befehlszeile
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Um Symbolinformationen, wie z.B. Funktionsnamen und Zeilennummern anzuzeigen, benötigt das VSPerfReport-Befehlszeilentool Zugriff auf die Symboldateien (.pdb) der profilierten Komponenten und die Windows-Systemdateien. Symboldateien werden erstellt, wenn eine Komponente kompiliert wird. Weitere Informationen finden Sie unter [VSPerfReport](../profiling/vsperfreport.md). VSPerfReport sucht automatisch in den folgenden Speicherorten nach Symboldateien:  
  
- Angegeben Pfade in der **/SymbolPath**-Option oder in der **_NT_SYMBOL_PATH**-Umgebungsvariable.  
  
- Der genaue lokale Pfad, in dem eine Komponente kompiliert wurde.  
  
- Das Verzeichnis, das die Profilerstellungsdatendatei (.vsp oder .vsps) enthält.  
  
  Microsoft stellt die PDB-Dateien für viele seiner Produkte online auf einem Symbolserver bereit. Wenn der Computer, den Sie für die Berichterstattung verwenden, mit dem Internet verbunden ist, verbindet sich VSPerfReport mit dem Online-Symbolserver, um automatisch nach Symbolinformationen zu suchen und die Dateien in einem lokalen Speicher zu speichern.  
  
  Sie können den Speicherort der Symboldateien und den Microsoft-Symbolserver folgendermaßen angeben:  
  
- Legen Sie die **_NT_SYMBOL_PATH**-Umgebungsvariable fest.  
  
- Fügen Sie die **/SymbolPath**-Option zur VSPerfReport-Befehlszeile hinzu.  
  
  Sie können auch beide Methoden verwenden.  
  
> [!NOTE]
>  Wenn [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] auf dem lokalen Computer installiert ist, wurde wahrscheinlich bereits ein Speicherort für die Windows-Symboldateien angegeben. Weitere Informationen finden Sie unter [Vorgehensweise: Verweisen auf Windows-Symbolinformationen](../profiling/how-to-reference-windows-symbol-information.md). Sie müssen VSPerfReport dennoch konfigurieren, um den Speicherort und den Server, wie weiter unten in diesem Thema beschrieben, zu verwenden.  
  
## <a name="specifying-windows-symbol-files"></a>Angeben von Windows-Symboldateien  
  
#### <a name="to-configure-the-use-of-the-windows-symbol-server"></a>So konfigurieren Sie die Verwendung des Windows-Symbolservers  
  
1. Falls erforderlich, erstellen Sie ein Verzeichnis, um die Symboldateien lokal zu speichern.  
  
2. Verwenden Sie die folgende Syntax zum Festlegen der **_NT_SYMBOL_PATH**-Umgebungsvariable oder die VSPerfReport /SymbolPath-Option:  
  
    **SRV\\*** *LocalStore* **\*http://msdl.microsoft.com/downloads/symbols**  
  
    wobei *LocalStore* der Pfad des lokalen Verzeichnisses ist, das Sie erstellt haben.  
  
## <a name="specifying-component-symbol-files"></a>Angeben von Komponentensymboldateien  
 Profilerstellungstools suchen nach den PDB-Dateien der Komponenten, die Sie in ihren ursprünglichen Speicherorten erstellen möchten, die in den Komponenten oder in den Ordnern mit der Profilerstellungsdatendatei gespeichert werden. Sie können andere Speicherorte zum Suchen angeben, indem Sie eine oder mehrere Pfade zu **_NT_SYMBOL_PATH** oder der **/SymbolPath**-Option hinzufügen. Separate Pfade mit Semikolons.  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile legt die **_NT_SYMBOL_PATH**-Umgebungsvariable auf den Windows-Symbolserver und das lokale Verzeichnis auf **C:\Symbols**.  
  
 **set _NT_SYMBOL_PATH=srv\*C:\symbols\*http://msdl.microsoft.com/downloads/symbols**  
  
 Die folgende VSPerfReport-Befehlszeile fügt mithilfe der **/SymbolPath**-Option das Verzeichnis C:\Projects\Symbols zum Suchpfad hinzu.  
  
 **VSPerfReport**  *MyApp* **.exe /SymbolPath:C:\Projects\Symbols /summary:all**



