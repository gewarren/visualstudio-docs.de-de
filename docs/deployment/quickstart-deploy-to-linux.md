---
title: Veröffentlichen in App Service unter Linux
ms.custom: ''
ms.date: 07/23/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: aa4afce6ef50284f1f966054e805b55c86f4daaf
ms.sourcegitcommit: 4f82c178b1ac585dcf13b515cc2a9cb547d5f949
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341747"
---
# <a name="publish-an-aspnet-core-app-to-app-service-on-linux-using-visual-studio"></a>Veröffentlichen einer ASP.NET Core-App in Azure App Service mit Visual Studio unter Linux

Sie können das Tool zum **Veröffentlichen** verwenden, um ASP.NET Core-Apps unter Linux in Azure App Service zu veröffentlichen.

Für die Bereitstellung in App Service unter Linux mithilfe des Tools zum **Veröffentlichen** muss Visual Studio 2017, Version 15.7, installiert sein.

[!INCLUDE [quickstart-prereqs-azure-linux](includes/quickstart-prereqs-azure-linux.md)]

## <a name="publish-to-app-service-on-linux"></a>Veröffentlichen in App Service unter Linux

1. Klicken Sie im Projektmappen-Explorer erst mit der rechten Maustaste auf das Projekt und anschließend mit der linken auf **Veröffentlichen**. Alternativ können Sie auch das Menüelement **Erstellen** > **Veröffentlichen** verwenden.

    ![Der Befehl „Veröffentlichen“ im Kontextmenü des Projekts im Projektmappen-Explorer](../deployment/media/quickstart-publish.png "Auswahl der Option „Veröffentlichen“")

1. Wenn Sie bereits Veröffentlichungsprofile konfiguriert haben, wird der Bereich **Veröffentlichen** angezeigt. Wenn dies der Fall ist, klicken Sie auf **Neues Profil erstellen**.

1. Vergewissern Sie sich im Dialogfeld **Pick a publish target** (Veröffentlichungsziel auswählen), dass **App Service Linux** ausgewählt ist.

    ![Auswahl von Azure App Service](../deployment/media/quickstart-publish-linux.png "Choose Azure App Service")

1. Wählen Sie **Veröffentlichen**. Dann wird das Dialogfeld **App Service erstellen** angezeigt. Melden Sie sich ggf. mit Ihrem Azure-Konto an. Dann werden die Felder mit den Standardeinstellungen für App Service aufgefüllt.

    ![App Service erstellen](../deployment/media/quickstart-publish-settings-app-service-linux.png "Azure App Service erstellen")

1. Wählen Sie **Erstellen** aus. Dann stellt Visual Studio die App in Azure App Service bereit und die Web-App wird in Ihrem Browser geladen. Im Bereich **Veröffentlichen** werden in den Projekteigenschaften die Website-URL und andere Details angezeigt.

    ![Eigenschaftenbereich „Veröffentlichen“, in dem eine Profilzusammenfassung angezeigt wird](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="clean-up-resources"></a>Bereinigen von Ressourcen

Sie haben bereits eine Azure-Ressource in einer Ressourcengruppe erstellt. Wenn Sie sich sicher sind, dass Sie diese Ressourcen in Zukunft nicht mehr benötigen, können Sie sie löschen, indem Sie die Ressourcengruppe entfernen.
Klicken Sie links im Azure-Portal erst auf **Ressourcengruppen** und dann auf **myResourceGroup**.
Vergewissern Sie sich auf der Seite „Ressourcengruppe“, dass die dort aufgeführten Ressourcen auch wirklich die sind, die Sie löschen möchten.
Klicken Sie auf **Löschen**, geben Sie **myResourceGroup** in das Textfeld ein, und klicken Sie erneut auf **Löschen**.

## <a name="next-steps"></a>Nächste Schritte

In diesem Schnellstart haben Sie erfahren, wie Sie Visual Studio unter Linux verwenden können, um ein Veröffentlichungsprofil für die Bereitstellung in App Service zu erstellen. Möglicherweise benötigen Sie weitere Informationen zum Veröffentlichen mit Azure unter Linux.

> [!div class="nextstepaction"]
> [Linux App Service](/azure/app-service/containers/app-service-linux-intro)
