---
title: Einführung in Visual Studio für Mac
description: In diesem Artikel werden die Features von Visual Studio für Mac eingeführt.
author: conceptdev
ms.author: crdun
ms.date: 11/03/2018
ms.assetid: 3A130EC1-DD8C-4125-9034-B08D7AF7EA65
ms.openlocfilehash: 10b27c26fcef622687b64f225dd04ae966f43cd5
ms.sourcegitcommit: ae46be4a2b2b63da7e7049e9ed67cd80897c8102
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2018
ms.locfileid: "52895677"
---
# <a name="introducing-visual-studio-for-mac"></a>Einführung in Visual Studio für Mac

Visual Studio für Mac ist eine moderne, anspruchsvolle IDE mit vielen Features zur Erstellung von mobilen, Desktop- und Webanwendungen. Die folgenden Entwicklungstypen werden unterstützt:

* Mobile Apps mit .NET: Android, iOS, tvOS, watchOS
* Mac-Desktop-Apps
* .NET Core-Anwendungen
* ASP.NET Core-Webanwendungen
* Plattformübergreifende Unity-Spiele

Es umfasst Features wie einen umfangreichen Editor, Debugfunktionen, native Plattformintegration in iOS, Mac und Android und integrierte Quellcodeverwaltung.

Dieser Artikel behandelt verschiedene Abschnitte von Visual Studio für Mac und stellt Features vor, die es zu einem leistungsstarken Tool zur Erstellung von plattformübergreifenden Anwendungen macht.

> [!TIP]
> Die Vorschauversion von Visual Studio 2019 für Mac kann jetzt getestet werden. Befolgen Sie die [Anweisungen zur Installation](install-preview.md), und sehen Sie sich eine [Übersicht der IDE](ide-tour.md) an.

## <a name="installation"></a>Installation

Führen Sie die im Leitfaden für [Installation](install-preview.md) beschriebenen Schritte aus, um Visual Studio für Mac herunterzuladen und zu installieren.

## <a name="language-support"></a>Sprachenunterstützung

Visual Studio für Mac unterstützt standardmäßig die Entwicklung in C# und F#.

### <a name="c"></a>C#

C# ist die am häufigsten verwendete Sprache zum Erstellen von plattformübergreifenden Anwendungen in Visual Studio für Mac. Alle Features von C# 7 werden vollständig von IDE unterstützt.

### <a name="f"></a>F#

F# ist eine stark typisierte funktionale Programmiersprache, die für die Ausführung auf .NET entwickelt wurde. Es ist für die Benutzer von Visual Studio für Mac auf Android, Mac und iOS als Programmiersprache verfügbar. Weitere Informationen zur Verwendung von F# und in der Sprache erstellte Beispiele finden Sie im Leitfaden für [F#](https://developer.xamarin.com/guides/cross-platform/fsharp/).

## <a name="platform-support"></a>Plattformunterstützung

## <a name="net-core"></a>.NET Core

[.NET Core](https://www.microsoft.com/net/core#macos) ist eine Plattform zum Erstellen von Anwendungen, die sowohl unter Windows und Linux als auch unter Mac ausgeführt werden können. Visual Studio für Mac verfügt über Unterstützung zum Laden, Erstellen, Ausführen und Debuggen von .NET Core-Projekten. 

Das Herunterladen und Installieren des .NET Core SDK wird empfohlen, um .NET Core-Projekte ausführen zu können.

Die .NET Core-Unterstützung enthält:

* C# und F#-IntelliSense
* .NET Core-Projektvorlagen für Konsolen, Bibliotheken und Webanwendungen
* Vollständige Unterstützung beim Debuggen, u.a. Haltepunkte, Aufruflisten, Überwachungsfenster, usw.
* PackageReferences von NuGet und MSBuild-basiertes Wiederherstellen
* Integrierte Unterstützung von Unittests für das Ausführen und Debuggen von Tests mit der Visual Studio-Testplattform, die im .NET Core SDK enthalten ist.
* Migration vom alten project.json-Format

Informationen zu den ersten Schritten finden Sie in der [hands-on lab (praktischen Testumgebung)](https://github.com/Microsoft/vs4mac-labs/tree/master/Web/Getting-Started) für ASP.NET Core-Web-Apps.

## <a name="xamarin"></a>Xamarin

Mit der herausragenden Unterstützung für [Xamarin](https://developer.xamarin.com/) können Sie beeindruckende native Benutzererfahrungen für Android, macOS, iOS, tvOS sowie watchOS entwickeln. Mit plattformübergreifenden Xamarin.Forms-Anwendungen können Sie XAML-basierten UI-Code zwischen Android, iOS und macOS freigeben, ohne den Zugriff auf native Funktionen einzuschränken.

Informationen zu den ersten Schritten finden Sie in der [hands-on lab (praktischen Testumgebung)](https://github.com/Microsoft/vs4mac-labs/tree/master/Mobile/Getting-Started) für mobile Apps.

### <a name="android"></a>Android

Visual Studio verfügt über einen eigenen integrierten Android SDK Manager.

Für Android-Anwendungen enthält Visual Studio für Mac einen eigenen Designer, der mit `.axml`-Dateien für Android arbeitet, um Benutzeroberflächen visuell zu entwerfen. Visual Studio für Mac öffnet diese Dateien wie im folgenden Bild dargestellt in seinem Android Designer:

![Android-Benutzeroberflächen-Designer](media/intro-image31.png)

Weitere Informationen zum Android Designer finden Sie im Dokument [Designer Overview (Übersicht: Designer)](https://developer.xamarin.com/Android/Guides/User_Interface/Designer_Overview).

### <a name="ios"></a>iOS

Der iOS Designer ist vollständig in Visual Studio für Mac integriert und ermöglicht die visuelle Bearbeitung von -xib- und Storyboard-Dateien, um Übergänge und Benutzeroberflächen für iOS, tvOS und WatchOS zu erstellen. Die gesamte Benutzeroberfläche kann erstellt werden, indem die Drag & Drop-Funktionen zwischen der Toolbox und der Entwurfsoberfläche verwendet werden, während ein intuitiver Ansatz zur Behandlung von Ereignissen verwendet wird. Der iOS Designer unterstützt auch [custom controls (benutzerdefinierte Steuerelemente)](https://developer.xamarin.com/guides/ios/user_interface/designer/ios_designable_controls_overview/) mit dem zusätzlichen Vorteil von Rendering zur Entwurfszeit.

![iOS Storyboard-Designer](media/intro-image30.png)

Weitere Informationen zur Verwendung des iOS Designers finden Sie in den Dokumenten über den [Designer](https://developer.xamarin.com/guides/ios/user_interface/designer).

### <a name="mac"></a>Mac

Xamarin stellt native Mac-API-Bindungen bereit, die Ihnen die Erstellung ansprechender Mac-Anwendungen ermöglicht.

Weitere Informationen zum Schreiben von Mac-Anwendungen mit Visual Studio für Mac finden Sie in der Dokumentation [Xamarin.Mac](https://developer.xamarin.com/guides/#mac).

## <a name="gaming"></a>Spiele

Visual Studio für Mac bietet Unterstützung für die plattformübergreifende Spieleentwicklung mit Unity 5.6.1.

Informationen zu den ersten Schritten finden Sie in der [hands-on lab (praktischen Testumgebung)](https://github.com/Microsoft/vs4mac-labs/tree/master/Unity/Getting-Started) für Unity.

## <a name="enterprise-features"></a>Enterprise-Funktionen

> [!Note]
> Diese Produkte können nur mit einem Abonnement für Visual Studio Enterprise verwendet werden.

### <a name="profiler"></a>Profiler

Der Xamarin Profiler verfügt über drei Instrumente zur Profilerstellung. Der Leitfaden [Introduction to the Xamarin Profiler (Einführung in den Xamarin Profiler)](https://developer.xamarin.com/guides/cross-platform/deployment,_testing,_and_metrics/xamarin-profiler/) erläutert, was diese Instrumente messen und wie sie Ihre Anwendung analysieren. Außerdem wird die Bedeutung der Daten verdeutlicht, die auf jedem Bildschirm dargestellt werden.

### <a name="inspector"></a>Inspector

Der Xamarin Inspector stellt eine interaktive C#-Konsole mit Benutzertools bereit. Er kann bei der Überprüfung aktiver Anwendungen beim Debuggen oder bei der Diagnose behilflich sein und weiterhin als Lerntool, Dokumentationstool oder Experimentiertool verwendet werden.

![Xamarin Inspector](media/intro-inspector.png)

Er besteht aus einer eigenständigen Anwendung, die eine umfangreiche und auf verschiedene Programmierplattformen (Android, iOS, Mac und Windows) ausgerichtete C#-Konsole und eine Integration in den Debuggingworkflow Ihrer IDE bereitstellt. 

Weitere Informationen finden Sie im Leitfaden zum [Xamarin Inspector](https://developer.xamarin.com/guides/cross-platform/inspector/).

## <a name="next-steps"></a>Nächste Schritte

* **Verschaffen Sie sich einen Überblick**: Einen Überblick über viele der wichtigsten Features in Visual Studio für Mac finden Sie in der [IDE-Tour](ide-tour.md) von Visual Studio für Mac.
* **Setup (Einrichtung)**: Informationen zum Herunterladen und Installieren von Visual Studio finden Sie im Leitfaden zur [Installation](installation.md).
* **Xamarin Tutorials (Xamarin-Tutorials)**: Weitere Informationen zum Entwickeln von Code in Xamarin finden Sie im [Developer Center](https://developer.xamarin.com) von Xamarin.
* **Videos**: Weitere Informationen zu anderen Features und Aspekten von Visual Studio für Mac finden Sie in den Videos auf der Website [Xamarin University (Xamarin-Universität)](https://university.xamarin.com).
* **Hands-on Labs (Praktische Testumgebungen)**: Informationen zu den ersten Schritten bei der Arbeit mit verschiedenen Arbeitslasten in Visual Studio für Mac finden Sie in der [hands-on lab (praktischen Testumgebung)](https://github.com/Microsoft/vs4mac-labs).
