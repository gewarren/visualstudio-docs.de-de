---
title: 'Fehler: Der Webserver konnte die angeforderte Ressource nicht gefunden | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: 1ceeaf30-918c-42bb-ace1-96944530fef3
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f490006d21f51f48cd8b2d97da262015ab170f39
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51808296"
---
# <a name="error-the-web-server-could-not-find-the-requested-resource"></a>Fehler: Der Webserver konnte die angeforderte Ressource nicht finden
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Aufgrund von Sicherheitsüberlegungen wurde von IIS ein generischer Fehler zurückgegeben.  
  
 Eine mögliche Ursache ist die Sicherheitskonfiguration des Servers. In IIS 6.0 und früheren Versionen wurde ein Zusatzhardwareprogramm, das als URLScan bekannt ist, zum Herausfiltern verdächtiger und fehlerhafter Anforderungen verwendet. Bei IIS 7.0 ist zu diesem Zweck die Anforderungsfilterung integriert. In beiden Fällen kann übermäßig einschränkende Anforderungsfilterung Visual Studio am Debuggen des Servers hindern.  
  
 Für diesen Fehler sind viele Ursachen möglich. Einige der häufigsten Ursachen schließen ein Problem mit der IIS-Installation oder der Konfigurationsroutine, der Websitekonfiguration oder den Berechtigungen im Dateisystem ein. Sie können versuchen, mit einem Browser auf die Ressource zuzugreifen. Abhängig von der IIS-Konfiguration müssen Sie möglicherweise einen lokalen Browser auf dem Server verwenden oder das IIS-Fehlerprotokoll überprüfen, um eine ausführliche Fehlermeldung zu erhalten.  
  
 Weitere Informationen zur Problembehandlung bei IIS finden Sie unter [IIS-Verwaltung und Administration](http://go.microsoft.com/fwlink/?LinkId=255872).  
  
## <a name="see-also"></a>Siehe auch  
 [UrlScan-Sicherheitstool](http://www.microsoft.com/technet/security/tools/urlscan.mspx)   
 [Fehler: Der Webserver wurde gesperrt und blockiert das DEBUG-Verb](../debugger/error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb.md)



