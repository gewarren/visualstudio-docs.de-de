---
title: CreatePkgDef-Hilfsprogramm | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- package definition
- create pkgdef
- pkgdef
- createpkgdef
ms.assetid: c745cb76-47a6-49ff-9eed-16af0f748e35
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c5c18e77405cd4e48c89d3b481937c7d837488cd
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53910934"
---
# <a name="createpkgdef-utility"></a>CreatePkgDef-Hilfsprogramm
Eine DLL-Datei für Visual Studio-Erweiterung als Parameter akzeptiert und erstellt eine *PKGDEF* Datei zur Ergänzung der *DLL* Datei. Die *PKGDEF* -Datei enthält alle Informationen, die in die systemregistrierung andernfalls geschrieben werden sollen, wenn die Erweiterung installiert ist.  
  
> [!NOTE]
>  Erstellen Sie die Projektvorlagen, die automatisch in Visual Studio SDK enthalten sind die meisten *PKGDEF* Dateien als Teil des Buildprozesses. Dieses Dokument richtet sich für diejenigen, die Pakete manuell erstellen, oder konvertieren Sie vorhandene Pakete verwenden möchten *PKGDEF* Bereitstellung.  
  
## <a name="syntax"></a>Syntax  
  
```  
CreatePkgDef /out=<FileName> [/codebase] [/assembly] <AssemblyPath>  
```  
  
## <a name="arguments"></a>Argumente  
 **/ out =&lt;Dateiname&gt;**  
 Erforderlich. Legt den Namen der der *PKGDEF* Ausgabedatei &lt;FileName&gt;.  
  
 **/codebase**  
 Dies ist optional. Erzwingt, dass die Registrierung mit dem **Codebasis** Hilfsprogramm.  
  
 **/ Assembly**  
 Erzwingt, dass die Registrierung mit dem **Assembly** Hilfsprogramm.  
  
 **&lt;Assemblypfad&gt;**  
 Der Pfad des der *DLL* Datei, die von dem Sie generieren möchten die *PKGDEF*.  
  
## <a name="remarks"></a>Hinweise  
 Bereitstellung von Erweiterungen mit *PKGDEF* Dateien ersetzt, die Anforderungen der Registrierung von früheren Versionen von Visual Studio.  
  
 Die *PKGDEF* Dateien müssen in einem der folgenden Speicherorte installiert sein: 

- *%LocalAppData%\Microsoft\Visual Studio\14.0\Extensions\\* 
 
- *%VSInstallDir%\Common7\IDE\Extensions\\*
    
  Wenn der Installationsordner *%localappdata%\Microsoft\Visual Studio\14.0\Extensions\\*, die Erweiterung wird von Visual Studio erkannt, aber standardmäßig deaktiviert sein. Der Benutzer kann mit die Erweiterung aktivieren **Erweiterungen und Updates**. 
   
  Wenn der Installationsordner *%vsinstalldir%\Common7\IDE\Extensions\\*, die Erweiterung ist standardmäßig aktiviert.  
  
> [!NOTE]
>  Die **Erweiterungen und Updates** Tool kann nicht verwendet werden, um eine Erweiterung zugreifen, es sei denn, es als Teil eines VSIX-Pakets installiert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CreateExpInstance-Hilfsprogramm](../../extensibility/internals/createexpinstance-utility.md)