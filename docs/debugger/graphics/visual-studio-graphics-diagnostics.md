---
title: Diagnose von Grafiken | Microsoft-Dokumentation
ms.custom: seodec18
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics
ms.assetid: fa69c550-62a7-41b5-bb1f-7eb04af1a6e8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e40a8ce0f2785aa606922d3f9c49f3aad48f7591
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2018
ms.locfileid: "53058616"
---
# <a name="visual-studio-graphics-diagnostics"></a>Visual Studio-Grafikdiagnose
Visual Studio*Grafikdiagnose* ist ein Satz von Tools zum Aufzeichnen, und klicken Sie dann Analysieren von Rendering- und Leistungsproblemen in Direct3D-apps. Die Grafikdiagnose kann für Apps verwendet werden, die lokal auf Ihrem Windows-PC, in einem Windows-Geräteemulator oder auf einem Remotecomputer oder-gerät ausgeführt werden.  

 Der Grafikdiagnose-Workflow beginnt mit der Erfassung eines Datensatzes zur Verwendung von Direct3D durch Ihre App – live, während der Ausführung –, damit das Verhalten sofort analysiert, freigegeben oder für die spätere Nutzung gespeichert werden kann. Erfassungssitzungen können manuell aus Visual Studio oder mit dem Befehlszeilenerfassungstool **dxcap.exe** initiiert und gesteuert werden. Erfassungssitzungen können auch programmgesteuert mit Grafikdiagnose-Erfassungs-APIs initiiert und gesteuert werden.  

 Nachdem eine Erfassungssitzung aufgezeichnet wurde, kann der Inhalt der *Visual Studio-Grafikanalyse* zu einem beliebigen Zeitpunkt wiedergegeben werden, wobei die aufgezeichneten Frames durch genau dieselben Ressourcen neu erstellt und die von der App verwendeten Befehle gerendert werden. Anschließend können mit den Tools im Grafikanalyse-Fenster alle aufgezeichneten Frames im Detail analysiert werden. Diese Tools können verwendet werden, um Direct3D-API-Aufrufe, Ressourcen, Pipelinezustandsobjekte, Pipelinestufen oder sogar den vollständigen Verlauf jedes Pixels in einem erfassten Frame zu untersuchen. Durch die kombinierte Verwendung dieser Tools kann ein Renderingproblem intuitiv untersucht werden, beginnend bei der Anzeige in einem erfassten Frame bis zu den Grundursachen in Quellcode, Shadern oder Grafikressourcen der App.  

 Sie können einen erfassten Frame mithilfe des Tools *Frame-Analyse* analysieren, um Leistungsprobleme zu diagnostizieren. Das Tool ermittelt, ob ein Potenzial zur Leistungsoptimierung vorhanden ist, indem es automatisch die Art und Weise ändert, in der die App Direct3D verwendet, und Vergleichstests zu allen Varianten ausführt. In der Vergangenheit haben Sie diese Änderungen möglicherweise manuell vorgenommen und die Ergebnisse gemessen, um herauszufinden, welche Unterschiede auftreten. Mit Frame-Analyse müssen Sie nur noch die Änderungen vornehmen, von denen Sie wissen, dass sie sich auszahlen.  

 Grafikdiagnose hilft Ihnen, Aussehen und Funktion einer grafisch aufwendigen Direct3D-App zu optimieren.  

 Weiterhin [Übersicht](overview-of-visual-studio-graphics-diagnostics.md) erfahren Sie, was Visual Studio Grafikdiagnose bietet.  

## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht](overview-of-visual-studio-graphics-diagnostics.md)  
 Bietet eine Einführung in den Workflow und die Tools der Grafikdiagnose.  

 [Erste Schritte](getting-started-with-visual-studio-graphics-diagnostics.md)  
 In diesem Abschnitt erfahren Sie, wie Sie Visual Studio-Grafikdiagnose installieren und mit der Direct3D-App verwenden.  

 [Capturing Graphics Information](capturing-graphics-information.md)  
 Um die Grafikdiagnose zur Untersuchung eines Renderingproblems zu verwenden, zeichnen Sie zuerst Informationen darüber auf, wie die App DirectX verwendet. In der Aufzeichnungssitzung, während der Ihre App normal ausgeführt wird, können Sie die gewünschten Frames *aufzeichnen*, d. h. auswählen. Die Aufzeichnungen enthalten ausführliche Informationen darüber, wie die Frames gerendert werden. Sie können die aufgezeichneten Informationen als Grafikprotokolldokument speichern, um sie später zu untersuchen oder für andere Teammitglieder freizugeben.  

 [GPU-Nutzung](gpu-usage.md)  
 Zur Profilerstellung Ihrer App mit der Grafikdiagnose verwenden Sie das GPU-Auslastungstool. Die GPU-Auslastung kann zusammen mit anderen Tools zur Profilerstellung, z. B. CPU-Nutzung, verwendet werden, um einen Zusammenhang zwischen CPU- und GPU-Aktivität und daraus resultierenden Leistungsproblemen in Ihrer App herzustellen.  

 [Grafikprotokolldokument](graphics-log-document.md)  
 Wählen Sie über das Dokumentfenster „Grafikprotokolle“ einen aufgezeichneten Frame – oder sogar ein bestimmtes Pixel, damit Sie dann die *Ereignisse* genauer untersuchen können (d. h. die DirectX-API-Aufrufe), die eine Auswirkung auf den Frame oder das Pixel haben. So können die Überprüfung eines aufgezeichneten Grafikprotokolls starten.  

 [Frame-Analyse](graphics-frame-analysis.md)  
 Nach der Auswahl eines Frames verwenden Sie die Grafikframe-Analyse, um Ihre Renderingleistung zu untersuchen und anzupassen.  

 [Ereignisliste](graphics-event-list.md)  
 Nachdem Sie einen Frame ausgewählt haben, untersuchen Sie mithilfe der **Grafikereignisliste** dessen Ereignisse, und überprüfen Sie, ob diese mit dem Renderingproblem zusammenhängen.  

 [Zustand](graphics-state.md)  
 Das Statusfenster hilft Ihnen, den während des aktuellen Ereignisses aktiven Status der Grafik zu verstehen.  

 [Pipelinestufen](graphics-pipeline-stages.md)  
 Untersuchen Sie im Fenster **Grafikpipelinestufen**, wie das aktuell ausgewählte Ereignis in den einzelnen Stufen der Grafikpipeline verarbeitet wird, damit Sie feststellen können, wo das Renderingproblem zuerst auftritt. Die Untersuchung der Pipelinephasen ist besonders hilfreich, wenn ein Objekt aufgrund einer falschen Transformation nicht angezeigt wird, oder wenn eine der Stufen eine Ausgabe erzeugt, die nicht mit der in der nächsten Phase erwarteten Ausgabe übereinstimmt.  

 [Ereignisaufrufliste](graphics-event-call-stack.md)  
 Mithilfe der **Aufrufliste des Grafikereignisses** können Sie die Aufrufliste des aktuell ausgewählten Ereignisses überprüfen und so zum App-Code navigieren, der mit dem Renderingproblem zusammenhängt.  

 [Pixelverlauf](graphics-pixel-history.md)  
 Im Fenster **Grafikpixelverlauf** können Sie analysieren, wie sich die Ereignisse auf das derzeit ausgewählte Pixel auswirken, und Sie können das Ereignis oder die Kombination der Ereignisse identifizieren, die bestimmte Arten von Renderingproblemen verursachen. Der Pixelverlauf ist besonders hilfreich, wenn ein Objekt falsch gerendert wird, da entweder die Ausgabe des Pixel-Shaders falsch ist oder falsch mit dem Framepuffer kombiniert wurde. Der Pixelverlauf ist ebenfalls aufschlussreich, wenn ein Objekt gar nicht angezeigt wird, da seine Pixel verworfen wurden, bevor sie den Framepuffer erreicht haben.  

 [Objekttabelle](graphics-object-table.md)  
 Mithilfe der **Grafikobjekttabelle** können Sie die Eigenschaften und Inhalte bestimmter Direct3D-Objekte und -ressourcen untersuchen, die für das aktuell ausgewählte Ereignis gültig sind. Die Objekttabelle unterstützt Sie bei der Ermittlung des Grafikgerätekontexts, der während eines Ereignisses aktiv ist, und bei der Untersuchung von Inhalten aus Grafikressourcen, wie Konstantenpuffer, Vertexpuffer und Texturen.  

 [HLSL-Debugger](hlsl-shader-debugger.md)  
 Verwenden Sie den **HLSL-Debugger**, um zu untersuchen, wie sich der Shadercode für die aktuell ausgewählte Ereignis- und Grafikpipelinestufe verhält. Mit dem HLSL-Debugger können Sie den Code schrittweise ausführen, den Inhalt von Variablen untersuchen und andere typische Debugaufgaben durchführen. Mit dem HLSL-Debugger können Sie auch den Compute-Shader-Code unabhängig davon untersuchen, ob die Ergebnisse weiter durch die Grafikpipeline verarbeitet oder nur von der Anwendung eingelesen werden.  

 [Befehlszeilen-Erfassungstool](command-line-capture-tool.md)  
 Verwenden Sie das Befehlszeilen-Erfassungstool, umGrafikinformationen schnell aufzuzeichnen und ohne Verwendung von Visual Studio oder programmgesteuerter Erfassung wiederzugeben. Insbesondere können Sie das Befehlszeilen-Erfassungstool für die Automatisierung oder in einer Testumgebung verwenden.  

 [Beispiele](graphics-diagnostics-examples.md)  
 Hier finden Sie einige Beispiele, die zeigen, wie die Grafikdiagnosetools gemeinsam zur Diagnose unterschiedlicher Renderingprobleme verwendet werden.  

## <a name="related-sections"></a>Verwandte Abschnitte  

| Titel | Beschreibung |
| - | - |
| [Debugger – Featuretour](../debugging-in-visual-studio.md) | Stellt die Debuggingfunktionen in [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vor. |
| [DirectX-Grafiken und -Spiele](http://go.microsoft.com/fwlink/?LinkId=256498) | Enthält Artikel, in denen die DirectX-Grafiktechnologien erläutert werden. |

