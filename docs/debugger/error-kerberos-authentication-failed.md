---
title: 'Fehler: Fehler bei der Kerberosauthentifizierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.callback_kerberos_auth_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0cf34885ee715a5685e4c2ced8b5a116e5c33e8d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49857658"
---
# <a name="error-kerberos-authentication-failed"></a>Fehler: Fehler bei der Kerberos-Authentifizierung
Beim Versuch, das Remotedebuggen auszuführen, kann die folgende Fehlermeldung ausgegeben werden:  
  
```cmd
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Kerberos authentication failed.  
```  
  
 Dieser Fehler tritt auf, wenn der Visual Studio-Remotedebugmonitor unter dem lokalen Systemkonto oder dem Netzwerkdienstkonto ausgeführt wird. Der Remotedebugger muss unter einem dieser Konten eine Verbindung für die Kerberos-Authentifizierung herstellen, um die Kommunikation mit dem Visual Studio Debugger-Hostcomputer zu ermöglichen.  
  
 Unter den folgenden Bedingungen ist die Kerberos-Authentifizierung nicht verfügbar:  
  
- Entweder der Zielcomputer oder der Debuggerhostcomputer befindet sich in einer Arbeitsgruppe anstatt in einer Domäne  
  
   \- oder –  
  
- Kerberos wurde auf dem Domänencontroller deaktiviert  
  
  Wenn die Kerberos-Authentifizierung nicht verfügbar ist, ändern Sie das zum Ausführen des Visual Studio-Remotedebugmonitors verwendete Konto. Die Prozedur finden Sie unter [Fehler: die Visual Studio Remote Debugger-Dienst auf dem Zielcomputer kann keine Verbindung hergestellt, rückverbindung mit diesem Computer](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).  
  
  Wenn beide Computer mit derselben Domäne verbunden sind und weiterhin diese Meldung ausgegeben wird, stellen Sie sicher, dass der Name des Debuggerhostcomputers vom DNS auf dem Zielcomputer ordnungsgemäß aufgelöst wird. Siehe folgendes Verfahren.  
  
### <a name="to-verify-that-dns-on-the-target-computer-is-correctly-resolving-the-debugger-host-computer-name"></a>So überprüfen Sie, ob der Name des Debuggerhostcomputers vom DNS auf dem Zielcomputer ordnungsgemäß aufgelöst wird  
  
1.  Öffnen Sie auf dem Zielcomputer die **starten** Startmenü **Zubehör** , und klicken Sie dann auf **Eingabeaufforderung**.  
  
2.  In der **Eingabeaufforderung** geben:  
  
    ```cmd
    ping <debugger_host_computer_name>  
    ```  
  
3.  Die erste Zeile der `ping`-Antwort enthält den vollständigen Computernamen und die vollständige IP-Adresse, die vom DNS für den angegebenen Computer zurückgegeben wurden.  
  
4.  Öffnen Sie auf den Hostcomputer des Debuggers, eine **Eingabeaufforderung** Fenster, und führen `ipconfig`.  
  
5.  Vergleichen Sie die IP-Adresswerte.  
  
## <a name="see-also"></a>Siehe auch  
 [Remotedebuggen – Fehler und Problembehandlung](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)
