---
title: Vorbereitung zum Debuggen von Windows-Services | Microsoft-Dokumentation
ms.custom: seodec18
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], Windows services
- Windows Service applications, debugging
ms.assetid: ac0a99f7-ec3d-4a20-b17f-698a817fdcc2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 86a80c6c24fdba594a5bfb5c11650b69eb2de693
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2018
ms.locfileid: "53065011"
---
# <a name="debugging-preparation-windows-services"></a>Vorbereitung zum Debuggen: Windows-Dienste
Ein Windows-Dienst ist ein Programm, das unter Microsoft Windows im Hintergrund ausgeführt wird. Beispiele hierfür sind der Telnet-Dienst und der Windows-Zeitdienst, durch den die auf dem Computer angezeigte Systemuhrzeit aktualisiert wird. Da ein Windows-Dienst innerhalb von [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nicht lauffähig ist, muss er im Kontext des Dienststeuerungs-Managers ausgeführt werden. Weitere Informationen finden Sie unter [Erstellen von Windows-Diensten](/dotnet/framework/windows-services/how-to-create-windows-services), [Debuggen von Windows-Dienstanwendungen](/dotnet/framework/windows-services/how-to-debug-windows-service-applications) und [Entwickeln von Windows-Dienstanwendungen](/dotnet/framework/windows-services/index).  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von verwaltetem Code](../debugger/debugging-managed-code.md)   
 [C#-, F#- und Visual Basic-Projekttypen](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Project Settings for  C# Debug Configurations (Projekteinstellungen für C#-Debugkonfigurationen)](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Project Settings for a Visual Basic Debug Configuration (Projekteinstellungen für eine Visual Basic-Debugkonfiguration)](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Vorgehensweise: Debuggen der OnStart-Methode](../debugger/how-to-debug-the-onstart-method.md)