---
title: 'Vorgehensweise: Angeben des zuerst zu erstellenden Ziels | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- DefaultTargets attribute [MSBuild]
- MSBuild, specifying the defalut target
- MSBuild, DefaultTargets attribute
ms.assetid: a580ba5b-2919-42d2-ae38-1af991e0205a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d73ef1935f01a48d756ce39df934f3afa83c2d30
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49864841"
---
# <a name="how-to-specify-which-target-to-build-first"></a>Vorgehensweise: Angeben des zuerst zu erstellenden Ziels
Eine Projektdatei kann ein oder mehrere `Target`-Elemente enthalten, die definieren, wie das Projekt erstellt wird. Die [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)])-Engine erstellt das erste Projekt, das sie findet, sowie alle Abhängigkeiten, es sei denn, die Projektdatei enthält ein `DefaultTargets`-Attribut, ein `InitialTargets`-Attribut oder ein Ziel, das in der Befehlszeile unter Verwendung des Schalters **-target** angegeben ist.  
  
## <a name="use-the-initialtargets-attribute"></a>Verwenden des InitialTargets-Attributs  
 Das `InitialTargets`-Attribut des `Project`-Elements gibt ein Ziel an, das zuerst ausgeführt wird, auch wenn Ziele in der Befehlszeile oder im `DefaultTargets`-Attribut angegeben sind.  
  
#### <a name="to-specify-one-initial-target"></a>Angeben eines ersten Ziels  
  
- Geben Sie das Standardziel im `InitialTargets`-Attribut des `Project`-Elements an. Zum Beispiel:  
  
   `<Project InitialTargets="Clean">`  
  
  Sie können mehrere erste Ziele im `InitialTargets`-Attribut angeben, indem Sie die Ziele nacheinander aufführen und mithilfe eines Semikolons voneinander trennen. Die Ziele in der Liste werden nacheinander ausgeführt.  
  
#### <a name="to-specify-more-than-one-initial-target"></a>Mehr als ein erstes Ziel angeben  
  
-   Listen Sie die ersten Ziele durch Semikolons getrennt im `InitialTargets`-Attribut des `Project`-Elements auf. Geben Sie zum Beispiel zum Ausführen des `Clean`-Ziels und anschließend des `Compile`-Ziels Folgendes ein:  
  
     `<Project InitialTargets="Clean;Compile">`  
  
## <a name="use-the-defaulttargets-attribute"></a>Verwenden des DefaultTargets-Attributs  
 Das `DefaultTargets`-Attribut des `Project`-Elements gibt das Ziel bzw. die Ziele an, die erstellt werden, wenn ein Ziel nicht explizit in der Befehlszeile angegeben wird. Wenn Ziele jeweils in `InitialTargets` und `DefaultTargets`-Attributen angegeben sind und kein Ziel in der Befehlszeile angegeben ist, führt [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] die im `InitialTargets`-Attribut angegebenen Ziele aus, gefolgt von den Zielen, die im `DefaultTargets`-Attribut angegeben sind.  
  
#### <a name="to-specify-one-default-target"></a>Ein Standardziel angeben  
  
- Geben Sie das Standardziel im `DefaultTargets`-Attribut des `Project`-Elements an. Zum Beispiel:  
  
   `<Project DefaultTargets="Compile">`  
  
  Sie können mehrere erste Ziele im `DefaultTargets`-Attribut angeben, indem Sie die Ziele nacheinander aufführen und mithilfe eines Semikolons voneinander trennen. Die Ziele in der Liste werden nacheinander ausgeführt.  
  
#### <a name="to-specify-more-than-one-default-target"></a>Mehr als ein erstes Ziel angeben  
  
-   Listen Sie die ersten Ziele durch Semikolons getrennt im `DefaultTargets`-Attribut des `Project`-Elements auf. Geben Sie zum Beispiel zum Ausführen des `Clean`-Ziels und anschließend des `Compile`-Ziels Folgendes ein:  
  
     `<Project DefaultTargets="Clean;Compile">`  
  
## <a name="use-the--target-switch"></a>Verwenden des Schalters -target  
 Wenn kein Standardziel in der Projektdatei definiert ist oder Sie das Standardziel nicht verwenden möchten, können Sie den Befehlszeilenschalter **-target** verwenden, um ein anderes Ziel anzugeben. Das Ziel oder die Ziele, die mit dem Schalter **-target** angegeben werden, werden anstelle der durch das `DefaultTargets`-Attribut angegebenen Ziele ausgeführt. Die im `InitialTargets`-Attribut angegebenen Ziele werden immer zuerst ausgeführt.  
 
 
#### <a name="to-use-a-target-other-than-the-default-target-first"></a>Zuerst ein anderen Ziels und nicht das Standardziel verwenden  
  
-   Geben Sie das Ziel als das erste Ziel mithilfe des Befehlszeilenschalters **-target** an. Zum Beispiel:  
  
     `msbuild file.proj -target:Clean`  
  
#### <a name="to-use-several-targets-other-than-the-default-targets-first"></a>So können Sie zuerst mehrere Ziele, die nicht die Standardziele sind, verwenden  
  
-   Listen Sie die Ziele (getrennt durch Semikolons oder Kommas) mit dem Befehlszeilenschalter **-target** auf. Zum Beispiel:  
  
     `msbuild <file name>.proj -t:Clean;Compile`  
  
## <a name="see-also"></a>Siehe auch
  [MSBuild](../msbuild/msbuild.md)  
 [Ziele](../msbuild/msbuild-targets.md)   
 [Vorgehensweise: Bereinigen eines Builds](../msbuild/how-to-clean-a-build.md)
