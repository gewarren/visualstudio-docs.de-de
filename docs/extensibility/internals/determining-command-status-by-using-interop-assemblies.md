---
title: Bestimmen des Befehlsstatus mithilfe von Interop-Assemblys | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- interop assemblies, determining command status
- command handling with interop assemblies, status
ms.assetid: 2f5104d1-7b4c-4ca0-a626-50530a8f7f5c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8d3c6a0f74f6f9f684e35c927bafc2ead7c19485
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53967747"
---
# <a name="determine-command-status-by-using-interop-assemblies"></a>Bestimmen des Befehlsstatus mithilfe von Interop-Assemblys
Eine VSPackage muss den Status der Befehle von verfolgt, die er verarbeiten kann. Die Umgebung kann nicht bestimmt werden, wenn ein Befehl in einem VSPackage behandelt aktiviert oder deaktiviert wird. Es ist Aufgabe Ihres VSPackage informiert die Umgebung zum Status von Befehl, z. B. der Zustand der allgemeine Befehle wie z. B. **Ausschneiden**, **Kopie**, und **einfügen**.  
  
## <a name="status-notification-sources"></a>Status-Benachrichtigung-Quellen  
 Die Umgebung empfängt Informationen zu Befehlen durch den VSPackages' <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> -Methode, die Teil der VSPackage Implementierung ist von der <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> Schnittstelle. Die Umgebung Ruft die <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> -Methode des VSPackages unter zwei Bedingungen:  
  
- Wenn ein Benutzer ein Hauptmenü oder ein Kontextmenü (durch Rechtsklick) geöffnet wird, führt die Umgebung die <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> Methode für alle Befehle in diesem Menü, deren Status zu bestimmen.  
  
- Wenn das VSPackage angefordert wird, dass die Umgebung auf die aktuelle Benutzeroberfläche (UI) aktualisieren. Dieses Update tritt auf, wie die Befehle, die derzeit für den Benutzer sichtbar, z. B. sind die **Ausschneiden**, **Kopie**, und **einfügen** auf der Standardsymbolleiste gruppieren, werden aktiviert und deaktiviert als Reaktion auf Kontext und Benutzeraktionen.  
  
  Da die Shell auf mehreren VSPackages hostet, würde die Shell unerwartet Leistungseinbußen es mussten jedes VSPackage, um zu bestimmen, den Befehlsstatus abrufen. Stattdessen sollte das VSPackage die Umgebung aktiv benachrichtigen, wenn es sich bei ändert sich die Benutzeroberfläche zum Zeitpunkt der Änderung. Weitere Informationen zu updatebenachrichtigung, finden Sie unter [die Benutzeroberfläche aktualisiert](../../extensibility/updating-the-user-interface.md).  
  
## <a name="status-notification-failure"></a>Fehler beim Status-Benachrichtigung  
 Fehler Ihres VSPackage, um die Umgebung von einer Zustandsänderung für den Befehl zu benachrichtigen, kann die Benutzeroberfläche in einem inkonsistenten Zustand platzieren. Denken Sie daran, dass keines Ihre Menübefehle im Menü oder Kontext durch den Benutzer auf einer Symbolleiste platziert werden kann. Aus diesem Grund ist die Benutzeroberfläche aktualisiert, nur, wenn ein Menü oder die Kontext-Menü geöffnet wird nicht ausreichend.  
  
## <a name="see-also"></a>Siehe auch  
 [Wie VSPackages Benutzeroberflächenelemente hinzufügen](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Implementation (Implementierung)](../../extensibility/internals/command-implementation.md)