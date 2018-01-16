---
title: 'Vorgehensweise: Anpassen von Klassendiagrammen (Klassen-Designer) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class diagrams, customizing
- shapes, removing type from class diagrams
- type shapes, removing from class diagrams
- class diagrams, removing type shapes
ms.assetid: e9030aea-c77d-4cc1-b8f6-b6ca469b692d
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ab6776ccdf8f3abe98190855ec41dc226677db61
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-class-diagrams-class-designer"></a>Gewusst wie: Anpassen von Klassendiagrammen (Klassen-Designer)
Sie können die Art und Weise ändern, in der in Klassendiagrammen Informationen angezeigt werden. Sie können das gesamte Diagramm oder die einzelnen Typen auf der Entwurfsoberfläche anpassen.  
  
Beispielsweise können Sie den Zoomfaktor eines gesamten Klassendiagramms einstellen, die Gruppierung und Sortierung einzelner Typmember ändern, Beziehungen anzeigen oder ausblenden, und einzelne Typen oder mehrere Typen gemeinsam an eine beliebige Position auf dem Diagramm verschieben.  
  
> [!NOTE]
>  Durch das Anpassen der Art und Weise, wie Formen im Diagramm angezeigt werden, wird der zugrunde liegende Code für die im Diagramm angezeigten Typen nicht geändert.  
  
Abschnitte, die Typmember enthalten, wie beispielsweise der Abschnitt "Eigenschaften" in einer Klasse, werden als Depots bezeichnet. Sie können einzelne Depots und Typmember anzeigen oder ausblenden.  
  
**Inhalt**  
  
-   [Vergrößern und Verkleinern der Ansicht des Klassendiagramms](how-to-customize-class-diagrams.md#ZoomInOut)  
  
-   [Anpassen der Gruppierung und Sortierung von Typmembern](how-to-customize-class-diagrams.md#CustomizeGroupingSorting)  
  
-   [Ausblenden von Depots für einen Typ](how-to-customize-class-diagrams.md#HideCompartments)  
  
-   [Ausblenden einzelner Member für einen Typ](how-to-customize-class-diagrams.md#HideMembers)  
  
-   [Anzeigen ausgeblendeter Depots und Member für einen Typ](how-to-customize-class-diagrams.md#DisplayHiddenCompartmentsAndMemberrs)  
  
-   [Ausblenden von Beziehungen](how-to-customize-class-diagrams.md#HideAssociationAndInheritance)  
  
-   [Anzeigen ausgeblendeter Beziehungen](how-to-customize-class-diagrams.md#DisplayAssociationAndInheritance)  
  
-   [Entfernen einer Typform aus einem Klassendiagramm](how-to-customize-class-diagrams.md#RemoveCodeAndShape)  
  
-   [Löschen einer Typform und des zugrunde liegenden Codes](how-to-customize-class-diagrams.md#DeleteTypeShapeAndCode)  
  
##  <a name="ZoomInOut"></a> Vergrößern und Verkleinern der Ansicht des Klassendiagramms  
  
1.  Öffnen Sie eine Klassendiagrammdatei im Klassen-Designer, und wählen Sie sie aus.  
  
2.  Klicken Sie auf der Symbolleiste des Klassen-Designers auf die Schaltfläche **Vergrößern** oder **Verkleinern**, um den Zoomfaktor der Designer-Oberfläche zu ändern.  
  
     oder  
  
     Geben Sie einen bestimmten Zoomwert an. Sie können die Dropdownliste **Zoom** verwenden oder einen gültigen Zoomfaktor eingeben (der gültige Bereich liegt bei 10 % bis 400 %).  
  
    > [!NOTE]
    >  Das Ändern des Zoomfaktors wirkt sich nicht auf die Skalierung des ausgedruckten Klassendiagramms aus.  
  
##  <a name="CustomizeGroupingSorting"></a> Anpassen der Gruppierung und Sortierung von Typmembern  
  
1.  Öffnen Sie eine Klassendiagrammdatei im Klassen-Designer, und wählen Sie sie aus.  
  
2.  Klicken Sie mit der rechten Maustaste auf einen leeren Bereich auf der Entwurfsoberfläche, und zeigen Sie auf **Member gruppieren**.  
  
3.  Wählen Sie eine der verfügbaren Optionen aus:  
  
    1.  **Nach Art gruppieren** unterteilt einzelne Typmember in eine gruppierte Liste von Eigenschaften, Methoden, Ereignissen und Feldern. Die einzelnen Gruppen hängen von der Entitätendefinition ab: Beispielsweise wird in einer Klasse keine Gruppe von Ereignissen angezeigt, wenn noch keine Ereignisse für diese Klasse definiert sind.  
  
    2.  **Nach Zugriff gruppieren** unterteilt einzelne Typmember auf der Grundlage der Zugriffsmodifizierer des Members in eine gruppierte Liste. Beispiel: Public und Private.  
  
    3.  **Alphabetisch sortieren** zeigt die Elemente, aus denen eine Entität besteht, als einzelne, alphabetisch sortierte Liste an. Die Liste ist in aufsteigender Reihenfolge sortiert.  
  
##  <a name="HideCompartments"></a> Ausblenden von Depots für einen Typ  
  
1.  Öffnen Sie eine Klassendiagrammdatei im Klassen-Designer, und wählen Sie sie aus.  
  
2.  Klicken Sie mit der rechten Maustaste auf die Memberkategorie in dem Typ, die Sie anpassen möchten (wählen Sie z.B. den Knoten **Methoden** in einer Klasse aus).  
  
3.  Klicken Sie auf **Depot ausblenden**.  
  
     Das ausgewählte Depot wird im Typcontainer ausgeblendet.  
  
##  <a name="HideMembers"></a> Ausblenden einzelner Member für einen Typ  
  
1.  Öffnen Sie eine Klassendiagrammdatei im Klassen-Designer, und wählen Sie sie aus.  
  
2.  Klicken Sie mit der rechten Maustaste in dem Typ auf den Member, den Sie ausblenden möchten.  
  
3.  Klicken Sie auf **Ausblenden**.  
  
     Der ausgewählte Member wird im Typcontainer ausgeblendet.  
  
##  <a name="DisplayHiddenCompartmentsAndMemberrs"></a> Anzeigen ausgeblendeter Depots und Member für einen Typ  
  
1.  Öffnen Sie eine Klassendiagrammdatei im Klassen-Designer, und wählen Sie sie aus.  
  
2.  Klicken Sie mit der rechten Maustaste auf den Namen des Typs mit dem ausgeblendeten Depot.  
  
3.  Klicken Sie auf **Alle Member anzeigen**.  
  
     Alle ausgeblendeten Depots und Member werden im Typcontainer angezeigt.  
  
##  <a name="HideAssociationAndInheritance"></a> Ausblenden von Beziehungen  
  
1.  Öffnen Sie eine Klassendiagrammdatei im Klassen-Designer, und wählen Sie sie aus.  
  
2.  Klicken Sie mit der rechten Maustaste auf die Zuordnungs- oder Vererbungszeile, die Sie ausblenden möchten.  
  
3.  Klicken Sie für Zuordnungszeilen auf **Ausblenden**, und klicken Sie für Vererbungszeilen auf **Vererbungszeile ausblenden**.  
  
4.  Klicken Sie auf **Alle Member anzeigen**.  
  
     Alle ausgeblendeten Depots und Member werden im Typcontainer angezeigt.  
  
##  <a name="DisplayAssociationAndInheritance"></a> Anzeigen ausgeblendeter Beziehungen  
  
1.  Öffnen Sie eine Klassendiagrammdatei im Klassen-Designer, und wählen Sie sie aus.  
  
2.  Klicken Sie mit der rechten Maustaste auf den Typ mit der ausgeblendeten Zuordnung oder Vererbung.  
  
 Klicken Sie für Zuordnungszeilen auf **Alle Member anzeigen**, und klicken Sie für Vererbungszeilen auf **Basisklasse anzeigen** oder **Abgeleitete Klassen anzeigen**.  
  
##  <a name="RemoveCodeAndShape"></a> Entfernen einer Typform aus einem Klassendiagramm  
Sie können eine Typform aus dem Klassendiagramm entfernen, ohne dass dies Auswirkungen auf den zugrunde liegenden Code des Typs hat. Das Entfernen von Typformen aus einem Klassendiagramm wirkt sich nur auf das jeweilige Diagramm aus. Der zugrunde liegende Code, der den Typ definiert, und andere Diagramme, die den Typ anzeigen, sind nicht betroffen.  
  
1.  Wählen Sie im Klassendiagramm die aus dem Diagramm zu entfernende Typform aus.  
  
2.  Klicken Sie im Menü **Bearbeiten** auf **Aus Diagramm entfernen**.  
  
     Die Typform und sämtliche mit der Form verbundene Assoziations- oder Vererbungslinien werden aus dem Diagramm entfernt.  
  
##  <a name="DeleteTypeShapeAndCode"></a> Löschen einer Typform und des zugrunde liegenden Codes  
  
1.  Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf die Form.  
  
2.  Wählen Sie im Kontextmenü die Option **Code löschen** aus.  
  
     Die Form wird aus dem Diagramm entfernt, und der zugrunde liegende Code wird aus dem Projekt gelöscht.  
  
## <a name="see-also"></a>Siehe auch
[Arbeiten mit Klassendiagrammen](working-with-class-diagrams.md)   
[Vorgehensweise: Wechseln zwischen Member- und Zuordnungsnotation](how-to-change-between-member-notation-and-association-notation.md)   
[Vorgehensweise: Anzeigen von vorhandenen Typen](how-to-view-existing-types.md)   
[Anzeigen von Typen und Beziehungen](viewing-types-and-relationships.md)