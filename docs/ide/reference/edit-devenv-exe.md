---
title: -Edit („devenv.exe“)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv switch
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5588d5dbf86039273854ddc372d1bbe096dad70b
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948139"
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
Öffnet die angegebene Datei in einer vorhandenen Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="syntax"></a>Syntax

```cmd
Devenv /edit [file1[ file2]]
```

## <a name="arguments"></a>Argumente
 `file1`

 Dies ist optional. Die Datei, die in einer vorhandenen Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] geöffnet werden soll. Wenn keine Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vorhanden ist, wird eine neue Instanz mit einem vereinfachten Fensterlayout erstellt, und `file1` wird in dieser neuen Instanz geöffnet.

 `file2`

 Dies ist optional. Eine oder mehrere zusätzliche Dateien, die in einer vorhandenen Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] geöffnet werden sollen.

## <a name="remarks"></a>Hinweise
 Wenn keine Datei angegeben ist und es eine vorhandene Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] gibt, wird die vorhandene Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bevorzugt. Wenn keine Datei angegeben ist und es keine Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] gibt, wird eine neue Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] mit einem vereinfachten Fensterlayout erstellt.

 Wenn eine vorhandene Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sich in einem modalen Zustand befindet, zum Beispiel, wenn das [Dialogfeld „Optionen“](../../ide/reference/options-dialog-box-visual-studio.md) offen ist, öffnet sich die Datei in der vorhandenen Instanz, sobald [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sich nicht mehr im modalen Zustand befinden.

## <a name="example"></a>Beispiel
 In diesem Beispiel wird die Datei `MyFile.cs` in einer vorhandenen Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] geöffnet, oder die Datei wird in einer neuen Instanz von [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] geöffnet, falls noch keine Instanz vorhanden ist.

```cmd
devenv /edit MyFile.cs
```

## <a name="see-also"></a>Siehe auch

- [Devenv-Befehlszeilenschalter](../../ide/reference/devenv-command-line-switches.md)