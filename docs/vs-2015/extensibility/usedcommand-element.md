---
title: UsedCommand-Element | Microsoft-Dokumentation
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
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8b34c2dbafe9126339638691bc345cab1d347924
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51742529"
---
# <a name="usedcommand-element"></a>UsedCommand-Element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Aktiviert ein VSPackage einen Befehl auf, der in eine andere VSCT-Datei definiert ist. Wenn das VSPackage der Standard verwendet z. B. **kopieren** -Befehl, der vom definiert wird die [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Shell, Sie können den Befehl zu einem Menü oder Symbolleiste ohne hinzufügen erneut zu implementieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|guid|Erforderlich. Die GUID der GUID-ID-Paar, die den Befehl identifiziert.|  
|id|Erforderlich. Die ID des das GUID-ID-Paar, die den Befehl identifiziert.|  
|Bedingung|Dies ist optional. Finden Sie unter [bedingte Attribute](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Keiner||  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[UsedCommands-Element](../extensibility/usedcommands-element.md)|Gruppen UsedCommand-Elementen und anderen UsedCommands Gruppierungen.|  
  
## <a name="remarks"></a>Hinweise  
 Durch das Hinzufügen eines Befehls in die `<UsedCommands>` -Element, um eine VSPackage informiert die [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Umgebung, die das VSPackage der Befehl erfordert. Sie sollten Hinzufügen einer `<UsedCommand>` -Element für jeden Befehl, der das Paket erfordert, kann nicht in allen Versionen und Konfigurationen von Visual Studio eingeschlossen werden. Z. B. Wenn Ihr Paket einen Befehl, die Visual C++-spezifisch ist aufruft, der Befehl wird nicht für Benutzer von Visual Web Developer, sofern Sie keine `<UsedCommand>` -Element für den Befehl.  
  
## <a name="example"></a>Beispiel  
  
```  
<UsedCommands>  
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>  
</UsedCommands>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [UsedCommands-Element](../extensibility/usedcommands-element.md)   
 [VSCT-Dateien (Visual Studio Command Table)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

