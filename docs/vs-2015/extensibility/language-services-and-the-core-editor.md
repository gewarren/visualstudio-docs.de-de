---
title: Sprachdienste und die Kern-Editor | Microsoft-Dokumentation
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
- editors [Visual Studio SDK], legacy - language services
ms.assetid: e03199a6-ad5f-4075-bfba-8d36865112b7
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 503924f435dda2d4432c915f9566846f0f4dd964
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51727303"
---
# <a name="language-services-and-the-core-editor"></a>Sprachdienste und die Kern-Editor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Editoren von Visual Studio werden häufig von einem Sprachdienst zugeordnet. Unter anderem bietet ein Sprachdienst, farbige syntaxmarkierung, Anweisungsvervollständigung, IntelliSense und textformatierung.  
  
## <a name="core-editors-and-document-data-objects"></a>Core-Editoren und Dokumentdatenobjekten  
 Wenn Sie die Kern-Editor zuzugreifen, Sie Dokumentdaten und dokumentenansichtsobjekten nicht erstellen. Die IDE erstellt und diesen beiden Objekten steuert, und Sie verarbeitet werden, indem Sie die entsprechenden Aufrufe in Ihrem Editor Factoryimplementierung machen abrufen.  
  
 Weitere Informationen finden Sie unter [ermitteln welcher Editor öffnet eine Datei in einem Projekt](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md).  
  
## <a name="language-services-and-the-core-editor"></a>Sprachdienste und die Kern-Editor  
 Implementieren Sie einen Sprachdienst, können Sie steuern, wie Daten in der Dokumentenansicht angezeigt werden. Ein Sprachdienst, bietet Informationen und Verhaltensweisen, die für eine bestimmte Sprache, z. B. Visual C++ spezifisch sind. Beim Erstellen von eines Textpuffers und bestimmen die Dateierweiterung für das zu öffnende Dokument, bestimmt der Textpuffer den Sprachdienst, der mit dieser Dateierweiterung aus einem Registrierungsschlüssel, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Editors verknüpft ist \\{YourLanguageService GUID} \Extensions. Laden die Prozedur dann standard VSPackage lädt das VSPackage, und eine Instanz des Sprachdiensts wird erstellt.  
  
 Ein einfachen Sprachdiensts wird in der folgenden Abbildung angezeigt.  
  
 ![Sprachdienstmodell](../extensibility/media/vslanguageservicemodel.gif "VsLanguageServiceModel")  
Core-Editoren und Sprachen Dienstobjekte  
  
 Das dokumentendatenobjekt für die Kern-Editor wird aufgerufen, einen Textpuffer und wird durch die <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> Objekt. Das dokumentenansichtsobjekt eine Textansicht aufgerufen wird, und wird durch die <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> Objekt. Diese beiden Objekte arbeiten zusammen, über den Sprachdienst einen einheitlichen Überblick über die Kern-Editor angeben. Informationen aus dem Textpuffer und zeigt den Text in einem Dokumentfenster wird ein Code-Fenster aufgerufen. Das Dokument der Code-Fenster wird durch einen Codefenster-Manager verwaltet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 [Einen Dienstkontext für die Sprache bereitstellt, mit der Legacy-API](../extensibility/providing-a-language-service-context-by-using-the-legacy-api.md)   
 [Hosten von IntelliSense](../extensibility/intellisense-hosting.md)   
 [Enthaltene Sprachen](../extensibility/contained-languages.md)   
 [Entwickeln eines Legacysprachdiensts](../extensibility/internals/developing-a-legacy-language-service.md)

