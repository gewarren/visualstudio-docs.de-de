---
title: Analysieren der CPU-Auslastung | Microsoft-Dokumentation
ms.custom: seodec18
ms.date: 11/04/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7501a20d-04a1-480f-a69c-201524aa709d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4b3d4d6a352d2ff1b71796d64c34992af493867a
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2018
ms.locfileid: "53063262"
---
# <a name="analyze-cpu-usage"></a>Analysieren der CPU-Auslastung 

Ein guter Ausgangspunkt für die Untersuchung von Leistungsproblemen in Ihrer App ist die CPU-Auslastung. Das Leistungstool für die **CPU-Auslastung** zeigt die CPU-Zeit und den prozentualen Anteil an, der für die Ausführung von Code in C++, C#/Visual Basic und JavaScript-Apps verwendet wird. 

Das Tool für die **CPU-Auslastung** kann auf einem geöffneten Visual Studio-Projekt oder auf einer installierten Microsoft Store-App ausgeführt oder an eine laufende App oder einen laufenden Prozess angefügt werden. Sie können das Tool auf lokalen Computern oder Remotecomputern sowie auf einem Simulator oder Emulator ausführen. Weitere Informationen finden Sie unter [Ausführen von Profilerstellungstools mit oder ohne Debugger](../profiling/running-profiling-tools-with-or-without-the-debugger.md). 

Sie können das Tool für die **CPU-Auslastung** mit oder ohne Debuggen ausführen. Im Debugger können Sie die CPU-Profilerstellung aktivieren bzw. deaktivieren sowie sich eine funktionsbezogene Aufschlüsselung der CPU-Auslastung ansehen. Sie können die Ergebnisse für die CPU-Auslastung anzeigen, wenn die Ausführung angehalten wurde, zum Beispiel an einem Breakpoint.  

Die folgenden Anweisungen zeigen, wie Sie das Tool für die **CPU-Auslastung** ohne den Debugger mit dem Visual Studio-**Leistungsprofiler** verwenden. In den Beispielen wird ein Releasebuild verwendet, der auf einem lokalen Computer erstellt wurde. Releasebuilds bieten die beste Ansicht der tatsächlichen App-Leistung. Informationen zur Analyse der CPU-Auslastung mit Debugbuilds finden Sie unter [Profilerstellung für die Anwendungsleistung in Visual Studio](../profiling/beginners-guide-to-performance-profiling.md).

In der Regel repliziert der lokale Computer die Ausführung der installierten App am besten. Bei Windows Phone-Apps bietet das Sammeln von Daten direkt vom Gerät die genauesten Daten. Führen Sie die App direkt auf dem Gerät und nicht über eine Remotedesktopverbindung aus, um Daten von einem Remotegerät zu sammeln. 

>[!NOTE]
>Für die Verwendung des [Leistungsprofilers](../profiling/profiling-feature-tour.md) ist Windows 7 oder höher erforderlich.
  
##  <a name="collect-cpu-usage-data"></a>Erfassen von CPU-Auslastungsdaten  
  
1. Legen Sie im Visual Studio-Projekt die Konfiguration der Projektmappe auf **Release** fest, und wählen Sie als Bereitstellungsziel **Lokaler Computer** aus.  
  
    ![Wählen Sie „Release“ und „Lokaler Computer“ aus](../profiling/media/cpuuse_selectreleaselocalmachine.png "Select Release and Local Machine")  
  
1. Wählen Sie **Debuggen** > **Leistungsprofiler** aus.  
  
1. Wählen Sie unter **Verfügbare Tools** die Option **CPU-Auslastung** und dann **Starten** aus.  
  
    ![Wählen Sie „CPU-Auslastung“ aus](../profiling/media/cpuuse_lib_choosecpuusage.png "Select CPU Usage")  
  
4. Nach dem Start der App beginnt die Diagnosesitzung, und es werden die CPU-Auslastungsdaten angezeigt. Wenn Sie mit dem Sammeln der Daten fertig sind, klicken Sie auf **Sammlung beenden**.  
  
   ![Beenden der Sammlung von CPU-Auslastungsdaten](../profiling/media/cpu_use_wt_stopcollection.png "Stop CPU Usage data collection")  
  
   Das CPU-Auslastungstool analysiert die Daten und zeigt den Bericht an.  
  
   ![CPU-Auslastungsbericht](../profiling/media/cpu_use_wt_report.png "CPU Usage report")  
  

## <a name="analyze-the-cpu-usage-report"></a>Analysieren des CPU-Auslastungsberichts  
  
Der Diagnosebericht wird nach **CPU gesamt** vom höchsten zum niedrigsten Wert sortiert. Ändern Sie die Sortierreihenfolge oder sortieren Sie eine Spalte, indem Sie auf die Spaltenüberschrift klicken. Verwenden Sie die Dropdownliste **Filter**, um das Anzeigen von Threads zu aktivieren bzw. deaktivieren. Verwenden Sie das Feld **Suchen**, um nach einem bestimmten Thread oder Knoten zu suchen. 

###  <a name="BKMK_Call_tree_data_columns"></a> Datenspalten der CPU-Auslastung  

|||  
|-|-|  
|**CPU gesamt [Einheit, %]**|![Gesamt % Datengleichung](../profiling/media/cpu_use_wt_totalpercentequation.png "CPU_USE_WT_TotalPercentEquation")<br /><br /> Die Millisekunden und der prozentuale CPU-Anteil, der im ausgewählten Zeitbereich durch Aufrufe der Funktion und die von der Funktion aufgerufenen Funktionen verwendet wurde. Dies unterscheidet sich vom Zeitachsendiagramm **CPU-Auslastung**, das die gesamte CPU-Aktivität in einem Zeitbereich mit der insgesamt verfügbaren CPU vergleicht.|  
|**Eigen-CPU [Einheit, %]**|![Eigen % Gleichung](../profiling/media/cpu_use_wt_selflpercentequation.png "CPU_USE_WT_SelflPercentEquation")<br /><br /> Die Millisekunden und der prozentuale CPU-Anteil, der im ausgewählten Zeitbereich durch Aufrufe der Funktion verwendet wurde. Die von der Funktion aufgerufenen Funktionen sind dabei ausgeschlossen.|  
|**Modul**|Der Name des Moduls, das die Funktion enthält.   
  
###  <a name="BKMK_The_CPU_Usage_call_tree"></a> Die Aufrufstruktur der CPU-Auslastung 

Wählen Sie zum Anzeigen der Aufrufstruktur im Bericht den übergeordneten Knoten aus. Es öffnet sich die Seite **CPU-Auslastung** in der Ansicht **Aufrufer/Aufgerufener**. Wählen Sie in der Dropdownliste **Aktuelle Ansicht** die Option **Aufrufstruktur** aus.  
  
####  <a name="BKMK_Call_tree_structure"></a> Struktur der Aufrufstruktur  

 ![Struktur der Aufrufstruktur](../profiling/media/cpu_use_wt_getmaxnumbercalltree_annotated.png "Call tree structure")  
  
|||  
|-|-|  
|![Schritt 1](../profiling/media/procguid_1.png "ProcGuid_1")|Der oberste Knoten in Aufrufstrukturen der CPU-Auslastung ist ein Pseudoknoten.|  
|![Schritt 2](../profiling/media/procguid_2.png "ProcGuid_2")|In den meisten Apps ist bei deaktivierter Option **Externen Code anzeigen** der Knoten der zweiten Ebene ein **[Externer Code]**-Knoten. Der Knoten enthält den System- und Frameworkcode, der die App startet und beendet, die Benutzeroberfläche zeichnet, die Threadplanung steuert und der App weitere Dienste auf unterer Ebene bereitstellt.|  
|![Schritt 3](../profiling/media/procguid_3.png "ProcGuid_3")|Die untergeordneten Elemente des Knotens der zweiten Ebene sind die Benutzercodemethoden und asynchronen Routinen, die vom System- und Frameworkcode der zweiten Ebene aufgerufen oder erstellt werden.|  
|![Schritt 4](../profiling/media/procguid_4.png "ProcGuid_4")|Untergeordnete Knoten einer Methode enthalten nur Daten für die Aufrufe der übergeordneten Methode. Wenn **Externen Code anzeigen** deaktiviert ist, können App-Methoden auch den Knoten **[Externer Code]** enthalten.|  
  
####  <a name="BKMK_External_Code"></a> Externer Code  

 System- und Frameworkfunktionen, die von Ihrem Code ausgeführt werden, werden als *externer Code* bezeichnet. Funktionen mit externem Code starten und beenden die App, zeichnen die Benutzeroberfläche, steuern das Threading und stellen der App weitere Dienste auf unterer Ebene bereit. In den meisten Fällen sind Sie nicht an externem Code interessiert, weshalb die Aufrufstruktur „CPU-Auslastung“ die externen Funktionen einer Benutzermethode in einem **[Externer Code]**-Knoten sammelt.  
  
 Wählen Sie zum Anzeigen der Aufrufpfade von externem Code auf der Hauptseite des Diagnoseberichts in der Dropdownliste **Filter** die Option **Externen Code anzeigen** und dann **Anwenden** aus. In der Ansicht **Aufrufstruktur** der Seite **CPU-Auslastung** werden dann die externen Codeaufrufe erweitert.  
  
 ![Externen Code anzeigen](../profiling/media/cpu_use_wt_filterview.png "Show External Code")  
  
 Viele externe Codeaufrufketten sind tief verschachtelt, sodass die Breite der Kette die Anzeigebreite der Spalte **Funktionsname** überschreiten kann. Die Funktionsnamen werden dann als **...** angezeigt.  
  
 ![Verschachtelter externer Code in der Aufrufstruktur](../profiling/media/cpu_use_wt_showexternalcodetoowide.png "Nested external code in the call tree")  
  
 Verwenden Sie das Suchfeld, um einen Funktionsnamen zu finden. Zeigen Sie auf die ausgewählte Zeile, oder verwenden Sie die horizontale Scrollleiste, um die Daten anzuzeigen.  
  
 ![Suche nach verschachteltem externem Code](../profiling/media/cpu_use_wt_showexternalcodetoowide_found.png "Search for nested external code")  
  
###  <a name="BKMK_Asynchronous_functions_in_the_CPU_Usage_call_tree"></a> Asynchrone Funktionen in der Aufrufstruktur der CPU-Auslastung  

 Wenn der Compiler auf eine asynchrone Methode trifft, erstellt er eine versteckte Klasse zum Steuern der Ausführung der Methode. Vom Konzept her ist die Klasse ein Zustandsautomat. Die Klasse verfügt über vom Compiler generierte Funktionen, die die ursprünglichen Methoden sowie die Rückrufe, Planer und Iteratoren, die für deren Ausführung erforderlich sind, asynchron aufrufen. Wenn eine übergeordnete Methode die ursprüngliche Methode aufruft, entfernt der Compiler die Methode aus dem Ausführungskontext der übergeordneten Methode und führt die Methoden der ausgeblendeten Klasse im Kontext des System- und Frameworkcodes durch, der die Ausführung der App steuert. Die asynchronen Methoden werden oft, jedoch nicht immer, in einem oder mehreren verschiedenen Threads ausgeführt. Dieser Code wird in der Aufrufstruktur **CPU-Auslastung** als untergeordnete Elemente des Knotens **[Externer Code]** direkt unter dem obersten Knoten der Struktur angezeigt.  

Im folgenden Beispiel sind die ersten beiden Knoten unter **[Externer Code]** die vom Compiler generierten Methoden der Zustandsautomatklasse. Der dritte Knoten ist der Aufruf der ursprünglichen Methode. 
  
![Asynchroner Knoten](media/cpu_use_wt_getmaxnumberasync_selected.png "Asynchronous node")  

Erweitern Sie die generierten Methoden, um zu sehen, was passiert:

![Erweiterter asynchroner Knoten](media/cpu_use_wt_getmaxnumberasync_expandedcalltree.png "Expanded asynchronous node")  

- `MainPage::GetMaxNumberAsyncButton_Click` verwaltet nur eine Liste der Aufgabenwerte, berechnet das Maximum der Ergebnisse und zeigt die Ausgabe an.
  
- `MainPage+<GetMaxNumberAsyncButton_Click>d__3::MoveNext` zeigt die erforderliche Aktivität zum Planen und Starten der 48 Aufgaben, die den Aufruf von `GetNumberAsync`umschließen.
  
- `MainPage::<GetNumberAsync>b__b` zeigt die Aktivität der Aufgaben an, die `GetNumber` aufrufen.
