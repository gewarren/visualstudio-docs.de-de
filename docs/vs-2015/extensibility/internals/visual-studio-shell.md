---
title: Visual Studio-Shell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- shell, Visual Studio
- Visual Studio, shell
ms.assetid: cb124ef4-1a6b-4bfe-bfbf-295ef9c07f36
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7ebe79d8ee93206e8d7950112386793a65812d38
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51748916"
---
# <a name="visual-studio-shell"></a>Visual Studio Shell
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Shell ist der primäre Agent der Integration in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Die Shell bietet die erforderliche Funktionalität zum Aktivieren von VSPackages allgemeine Dienste gemeinsam verwenden. Da das architektonische Ziel [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] besteht darin, primäre Funktionalität in der VSPackages, steht Ihnen zu die Shell ist ein Framework Grundfunktionen und als auch die Kommunikation zwischen der Komponente VSPackages zu unterstützen.  
  
## <a name="shell-responsibilities"></a>Shell-Aufgaben  
 Die Shell hat folgende wichtigsten Aufgaben:  
  
- Unterstützung von grundlegenden Elemente der Benutzeroberfläche (UI) (über COM-Schnittstellen). Dazu gehören Standardmenüs und Symbolleisten, Dokument-Fenster-Frames oder mit mehreren Dokumentschnittstelle (MDI) untergeordnete Fenster, und Toolfenster-Frames und andockunterstützung.  
  
- Verwalten eine fortlaufend aktualisierte Liste aller aktuell geöffneten Dokumente in eine aktive Dokumenttabelle (RDT) aus, um die Persistenz von Dokumenten zu koordinieren und sicherzustellen, dass dieses eine Dokument nicht in mehr als eine Möglichkeit, oder klicken Sie auf inkompatible Weise geöffnet werden kann.  
  
- Der Befehl-routing und Behandlung von Befehlen-Schnittstelle unterstützen `IOleCommandTarget`.  
  
- Laden von VSPackages zu geeigneten Zeitpunkten. Verzögertes Laden eine VSPackage muss zum Verbessern der Leistung der Shell zur Verfügung.  
  
- Verwalten bestimmte gemeinsame Dienste, z. B. <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>, die grundlegende Shell stellt Funktionen bereit, und <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>, der grundlegende fensterverwaltungsfunktionalität bietet bereitstellt.  
  
- Verwalten die Projektmappendateien (.sln) an. Projektmappen enthalten Gruppen von verwandten Projekten, ähnlich wie die Dateien des gruppenarbeitsbereichs (.dsw) in Visual C++ 6.0.  
  
- Überwachung-Shell-Wide-Auswahl, Kontext und Währung. Die Shell verfolgt nach, die folgenden Elementtypen:  
  
  -   Das aktuelle Projekt  
  
  -   Die aktuelle Projektelement oder das aktuelle Element-ID <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>  
  
  -   Die aktuelle Auswahl für die **Eigenschaften** Fenster oder `SelectionContainer`  
  
  -   Die UI-Kontext-IDs oder CmdUIGuids, die steuern, die Sichtbarkeit der Befehle, Menüs und Symbolleisten  
  
  -   Die derzeit aktiven Elemente wie z. B. das aktive Fenster, Dokument und rückgängig-manager  
  
  -   Die Kontext-Attribute, mit denen dynamische Hilfe  
  
  Die Shell vermittelt auch die Kommunikation zwischen den installierten VSPackages und Dienste. Es unterstützt die Kernfunktionen von der Shell, und stellt sie zur Verfügung, die alle integrierten VSPackages [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Diese Core-Features gehören die folgenden Elemente:  
  
- **Informationen zu** Dialogfeld Box und Splash-Bildschirm  
  
- **Hinzufügen von New "und" Vorhandenes Element hinzufügen** Dialogfelder  
  
- **Klassenansicht** Fenster und **Objektkatalog**  
  
- **Verweise** (Dialogfeld)  
  
- **Dokumentgliederung** Fenster  
  
- **Dynamische Hilfe** Fenster  
  
- **Suchen** und **ersetzen**  
  
- **Projekt öffnen** und **geöffnete Datei** Dialogfelder auf die **neu** Menü  
  
- **Optionen** Dialogfeld auf die **Tools** Menü  
  
- **Eigenschaftenfenster**  
  
- **Projektmappen-Explorer**  
  
- **Aufgabenliste für** Fenster  
  
- **Werkzeugkasten**  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>   
 [VSPackages](../../extensibility/internals/vspackages.md)

