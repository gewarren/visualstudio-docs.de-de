---
title: Angeben des Pfads zu den Profilerstellungstools für die Befehlszeile | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 886c035ddcc14b43200b13d789e59430cf090fdf
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51731272"
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>Angeben des Pfads zu den Profilerstellungstools für die Befehlszeile
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Der Pfad der Befehlszeilentools der [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]-Profilerstellungstools wird der PATH-Umgebungsvariablen nicht hinzugefügt. Auf 32-Bit-Computern befinden sich die Tools in einem einzigen Verzeichnis. Es gibt 32-Bit und 64-Bit-Versionen der Profilerstellungstools auf 64-Bit-Computern.  
  
## <a name="32-bit-computers"></a>32-Bit-Computer  
 Auf 32-Bit-Computern ist das Standardverzeichnis für Profilerstellungstools *Laufwerk*\Programme\Microsoft Visual Studio 11.0\Team Tools\Performance Tools.  
  
## <a name="64-bit-computers"></a>64-Bit-Computer  
 Auf 64-Bit-Computern legen Sie den Pfad entsprechend der Zielplattform der profilierten Anwendung fest.  
  
-   Bei 32-Bit-Anwendungen lautet das Standardverzeichnis für Profilerstellungstools:  
  
     *Laufwerk*\Programme (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools  
  
-   Bei 64-Bit-Anwendungen lautet das Standardverzeichnis für Profilerstellungstools:  
  
     *Laufwerk*\Programme (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools\x64



