---
title: 'Exemplarische Vorgehensweise: Aufzeichnen von Grafikinformationen programmgesteuert | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5adeff9-afaf-4047-b5ce-ef0aefe710eb
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 59853bf733364f2db8a60e3c9515e2771c8e4ebe
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-capturing-graphics-information-programmatically"></a>Exemplarische Vorgehensweise: Programmgesteuertes Erfassen von Grafikinformationen
Sie können die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] -Grafikdiagnose zur programmgesteuerten Erfassung von Grafikinformationen aus einer Direct3D-App verwenden.  
  
 Programmgesteuerte Erfassung ist in Szenarien wie den folgenden nützlich:  
  
-   Beginnen Sie programmgesteuerte Erfassung, wenn Ihre Grafik-App kein vorhandenes Swapchain verwendet, etwa wenn sie auf einer Textur rendert.  
  
-   Beginnen Sie programmgesteuerte Erfassung, wenn Ihre Grafik-App überhaupt kein Rendern ausführt, etwa wenn in ihr DirectCompute verwendet wird, um Berechnungen auszuführen.  
  
-   Rufen Sie `CaptureCurrentFrame`auf, wenn ein Renderingproblem schwer durch manuelles Testen zu antizipieren und zu erfassen ist, aber programmgesteuert mithilfe von Informationen über den Status der App zur Laufzeit vorhergesagt werden kann.  
  
##  <a name="CaptureDX11_2"></a> Programmgesteuerte Erfassung in Windows 8.1  
 In diesem Teil der exemplarischen Vorgehensweise wird die programmgesteuerte Erfassung in Apps gezeigt, die die DirectX 11.2-API unter Windows 8.1 verwenden, in der die Methode der stabilen Erfassung verwendet wird. Informationen zur Verwendung der programmgesteuerten Erfassung in Apps, die frühere Versionen von DirectX unter Windows 8.0 verwenden, finden Sie unter [Programmatic capture in Windows 8.0 and earlier](#CaptureDX11_1) weiter unten in diesem Artikel.  
  
 In diesem Abschnitt wird gezeigt, wie folgende Aufgaben ausgeführt werden:  
  
-   Vorbereiten Ihrer App für die Verwendung der programmgesteuerten Erfassung  
  
-   Abrufen der Schnittstelle IDXGraphicsAnalysis  
  
-   Aufzeichnen von Grafikinformationen  
  
> [!NOTE]
>  Frühere Implementierungen der programmgesteuerten Erfassung basieren auf Remotetools für [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , um Erfassungsfunktionalität bereitzustellen. Windows 8.1 unterstützt Erfassung direkt über Direct3D 11.2. Deshalb ist es unter Windows 8.1 nicht mehr erforderlich, dass Sie die Remotetools für programmgesteuerte Erfassung installieren.  
  
### <a name="preparing-your-app-to-use-programmatic-capture"></a>Vorbereiten Ihrer App für die Verwendung der programmgesteuerten Erfassung  
 Um programmgesteuerte Erfassung in Ihrer App verwenden zu können, muss diese die erforderlichen Header enthalten. Diese Header sind Bestandteile des Windows 8.1 SDK.  
  
##### <a name="to-include-programmatic-capture-headers"></a>So schließen Sie die Header für die programmgesteuerte Erfassung ein  
  
-   Schließen Sie diese Header in die Quelldatei ein, in der Sie die IDXGraphicsAnalysis-Schnittstelle definieren:  
  
    ```  
    #include <DXGItype.h>  
    #include <dxgi1_2.h>  
    #include <dxgi1_3.h>  
    #include <DXProgrammableCapture.h>  
    ```  
  
    > [!IMPORTANT]
    >  Schließen Sie nicht die Header-Datei vsgcapture.h—which unterstützt die programmgesteuerte Erfassung unter Windows 8.0 und früher –, die programmgesteuerte Erfassung in Ihren Windows 8.1-apps auszuführen. Dieser Header ist nicht mit DirectX 11.2 kompatibel. Wenn diese Datei enthalten ist, nachdem die d3d11_2.h-Header enthalten ist, gibt der Compiler eine Warnung aus. Wenn vor dem d3d11_2.h vsgcapture.h enthalten ist, wird die app nicht gestartet.  
  
    > [!NOTE]
    >  Wenn das DirectX SDK vom Juni 2010 auf Ihrem Computer installiert wurde und der Include-Pfad Ihres Projekts `%DXSDK_DIR%includex86`enthält, verschieben Sie diesen Teil an das Ende des Include-Pfads. Gehen Sie beim Bibliothekspfad genauso vor.  
  
#### <a name="windows-phone-81"></a>Windows Phone 8.1  
 Da das Windows Phone 8.1 SDK den Header DXProgrammableCapture.h umfasst, müssen Sie definieren die `IDXGraphicsAnalysis` Schnittstelle selbst, sodass Sie verwenden können, die `BeginCapture()` und `EndCapture()` Methoden. Schließen Sie die anderen Header so ein, wie dies im vorherigen Abschnitt beschrieben ist.  
  
###### <a name="to-define-the-idxgraphicsanalysis-interface"></a>So definieren Sie die IDXGraphicsAnalysis-Schnittstelle  
  
-   Definieren Sie die IDXGraphicsAnalysis-Schnittstelle in derselben Datei, in die Sie die Headerdateien eingeschlossen haben.  
  
    ```  
    interface DECLSPEC_UUID("9f251514-9d4d-4902-9d60-18988ab7d4b5") DECLSPEC_NOVTABLE  
    IDXGraphicsAnalysis : public IUnknown  
    {  
        STDMETHOD_(void, BeginCapture)() PURE;  
        STDMETHOD_(void, EndCapture)() PURE;  
    };  
    ```  
  
 Der Einfachheit halber können Sie diese Schritte in einer neuen Header-Datei ausführen und diese dann dort einschließen, wo Sie sie in Ihrer App benötigen.  
  
### <a name="getting-the-idxgraphicsanalysis-interface"></a>Abrufen der Schnittstelle IDXGraphicsAnalysis  
 Bevor Sie Grafikinformationen von DirectX 11.2 erfassen können, müssen Sie die DXGI-Debugschnittstelle abrufen.  
  
> [!IMPORTANT]
>  Wenn Sie programmgesteuerte Erfassung verwenden, müssen Sie weiterhin Ihre app unter der Grafikdiagnose ausführen (Alt + F5 in [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]) oder unter der [Befehlszeilen-Erfassungs-Tool](command-line-capture-tool.md).  
  
##### <a name="to-get-the-idxgraphicsanalysis-interface"></a>So rufen Sie die IDXGraphicsAnalysis-Schnittstelle ab  
  
-   Verwenden Sie den folgenden Code, um die IDXGraphicsAnalysis-Schnittstelle an die DXGI-Debugschnittstelle anzuschließen.  
  
    ```  
    IDXGraphicsAnalysis* pGraphicsAnalysis;  
    HRESULT getAnalysis = DXGIGetDebugInterface1(0, __uuidof(pGraphicsAnalysis), reinterpret_cast<void**>(&pGraphicsAnalysis));  
    ```  
  
     Prüfen Sie unbedingt das von `HRESULT` zurückgegebene `DXGIGetDebugInterface1` , um sicherzugehen, dass Sie eine gültige Schnittstelle verwenden:  
  
    ```  
    if (FAILED(getAnalysis))  
    {  
        // Abort program or disable programmatic capture in your app.  
    }  
    ```  
  
    > [!NOTE]
    >  Wenn `DXGIGetDebugInterface1` den Wert `E_NOINTERFACE` zurückgibt (`error: E_NOINTERFACE No such interface supported`), müssen Sie sicherstellen, dass die App unter der Grafikdiagnose (Alt+F5 in [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]).  
  
### <a name="capturing-graphics-information"></a>Aufzeichnen von Grafikinformationen  
 Wenn Sie nun über eine gültige `IDXGraphicsAnalysis` -Schnittstelle verfügen, können Sie `BeginCapture` und `EndCapture` verwenden, um Grafikinformationen zu erfassen.  
  
##### <a name="to-capture-graphics-information"></a>So erfassen Grafikinformationen  
  
-   Verwenden Sie `BeginCapture`, um mit der Erfassung von Grafikinformationen zu beginnen:  
  
    ```  
    ...  
    pGraphicsAnalysis->BeginCapture();  
    ...  
    ```  
  
     Die Erfassung beginnt sofort, wenn `BeginCapture` aufgerufen wird; es wird auf den nächsten Frame gewartet. Die Erfassung stoppt, wenn der aktuelle Frame dargestellt wird oder wenn Sie `EndCapture`aufrufen:  
  
    ```  
    ...  
    pGraphicsAnalysis->EndCapture();  
    ...  
    ```  
  
##  <a name="CaptureDX11_1"></a> Programmatic capture in Windows 8.0 and earlier  
 In diesem Teil der exemplarischen Vorgehensweise wird die programmgesteuerte Erfassung in Apps Windows 8.0 und früher gezeigt, die die DirectX 11.1-API verwenden, in der die frühere Erfassungsmethode verwendet wird. Informationen zur Verwendung der programmgesteuerten Erfassung in Apps, die DirectX 11.2 unter Windows 8.1 verwenden, finden Sie unter [Programmgesteuerte Erfassung in Windows 8.1](#CaptureDX11_2) weiter oben in diesem Artikel.  
  
 In diesem Teil werden folgende Aufgaben vorgestellt:  
  
-   Vorbereiten Ihres Computers für die Verwendung der programmgesteuerten Erfassung  
  
-   Vorbereiten Ihrer App für die Verwendung der programmgesteuerten Erfassung  
  
-   Konfigurieren des Namens und des Ortes der Grafikprotokolldatei  
  
-   Verwenden der `CaptureCurrentFrame` -API  
  
### <a name="preparing-your-computer-to-use-programmatic-capture"></a>Vorbereiten Ihres Computers für die Verwendung der programmgesteuerten Erfassung  
 Die API für die programmgesteuerte Erfassung verwendet Remote-Tools für [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , um die Erfassungsfunktionen bereitzustellen. Auf dem Computer, auf dem die App läuft, müssen die Remote-Tools installiert sein, auch wenn Sie die programmgesteuerte Erfassung auf Ihrem lokalen Computer anwenden. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] muss nicht laufen, wenn Sie die programmgesteuerte Erfassung auf einem lokalen Computer durchführen.  
  
 Um die APIs für die Remote-Erfassung in einer App zu verwenden, die auf einem Computer läuft, müssen Sie zuerst die Remote-Tools für [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] auf diesem Computer installieren. Verschiedene Versionen der Remote-Tools unterstützen verschiedene Hardwareplattformen. Informationen zur Installation der Remotetools finden Sie auf der Download-Website von Microsoft auf der [Downloadseite für Remotetools](http://go.microsoft.com/fwlink/p/?LinkId=246691) .  
  
 Alternativ werden durch [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] die erforderlichen Komponenten zur Durchführung der Remote-Erfassung für 32-Bit-Apps installiert.  
  
> [!NOTE]
>  Da die meisten Windows-Desktop-Apps – darunter [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]– unter [!INCLUDE[win8](../includes/win8_md.md)] für ARM-Geräte nicht unterstützt werden, ist die Verwendung von Remote-Tools für [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zusammen mit der API für die programmgesteuerte Erfassung der einzige Weg, um Grafikdiagnosen auf ARM-Geräten zu erfassen.  
  
### <a name="preparing-your-app-to-use-programmatic-capture"></a>Vorbereiten Ihrer App für die Verwendung der programmgesteuerten Erfassung  
 Sie müssen zunächst die benötigten Grafikinformationen erfassen, um die Grafikdiagnosetools verwenden zu können. Sie können die Informationen mithilfe der `CaptureCurrentFrame` -API programmgesteuert erfassen.  
  
##### <a name="to-prepare-your-app-to-capture-graphics-information-programmatically"></a>So bereiten Sie Ihre App für die programmgesteuerte Erfassung von Grafikinformationen vor  
  
1.  Stellen Sie sicher, dass der Header `vsgcapture.h` im Quellcode für die App enthalten ist. Dieser kann an nur einem Ort eingeschlossen werden – z. B. in der Quellcodedatei, in der Sie die API für die programmgesteuerte Erfassung aufrufen, oder in einer vorkompilierten Headerdatei zum Aufrufen der API aus mehreren Quellcodedateien.  
  
2.  Rufen Sie im Quellcode für die App immer dann, wenn Sie den Rest des aktuellen Frames erfassen möchten, `g_pVsgDbg->CaptureCurrentFrame()`auf. Mit dieser Methode werden keine Parameter übernommen und keine Werte zurückgegeben.  
  
### <a name="configuring-the-name-and-location-of-the-graphics-log-file"></a>Konfigurieren des Namens und des Ortes der Grafikprotokolldatei  
 Das Grafikprotokoll wird an dem Ort erstellt, der durch die Makros `DONT_SAVE_VSGLOG_TO_TEMP` und `VSG_DEFAULT_RUN_FILENAME` definiert ist.  
  
##### <a name="to-configure-the-name-and-location-of-the-graphics-log-file"></a>So konfigurieren Sie den Namen und den Ort der Grafikprotokolldatei  
  
-   Fügen Sie vor der Zeile `#include <vsgcapture.h>` Folgendes ein, um zu verhindern, dass das Grafikprotokoll in das Temp-Verzeichnis geschrieben wird:  
  
    ```  
    #define DONT_SAVE_VSGLOG_TO_TEMP  
    ```  
  
     Sie können diesen Wert definieren, um das Grafikprotokoll an einen Ort zu schreiben, der sich im Arbeitsverzeichnis befindet, oder in einen absoluten Pfad, wenn die Definition von `VSG_DEFAULT_RUN_FILENAME` ein absoluter Pfad ist.  
  
-   Fügen Sie vor der Zeile `#include <vsgcapture.h>` Folgendes ein, um das Grafikprotokoll an einem anderen Ort zu speichern oder ihm einen anderen Dateinamen zu geben:  
  
    ```  
    #define VSG_DEFAULT_RUN_FILENAME <filename>  
    ```  
  
     Wenn Sie diesen Schritt nicht ausführen, lautet der Dateiname default.vsglog. Wenn Sie `DONT_SAVE_VSGLOG_TO_TEMP`nicht definiert haben, ist der Speicherort der Datei relativ zum Temp-Verzeichnis; andernfalls ist er relativ zum Arbeitsverzeichnis oder an einem anderen Speicherort, wenn Sie einen absoluten Dateinamen angegeben haben.  
  
 Für [!INCLUDE[win8_appname_long](../includes/win8_appname_long_md.md)] apps, den Ort des temp-Verzeichnisses ist für jeden Benutzer und jede app spezifisch und befindet sich in der Regel an einem Ort wie z. B. C:\users\\*Benutzername*\AppData\Local\Packages\\ *paketfamiliennamen*\TempState\\. Bei desktop-apps der Ort des temp-Verzeichnisses für jeden Benutzer spezifisch und befindet sich in der Regel an einem Ort wie z. B. C:\Users\\*Benutzername*\AppData\Local\Temp\\.  
  
> [!NOTE]
>  Um in einen speziellen Speicherort zu schreiben, müssen Sie über die entsprechende Berechtigungen verfügen; andernfalls tritt ein Fehler auf. Denken Sie daran, dass [!INCLUDE[win8_appname_long](../includes/win8_appname_long_md.md)] -Apps Daten in weniger Orte schreiben können als Desktop-Apps und dass eventuell eine zusätzliche Konfiguration erforderlich ist, um in bestimmte Speicherorte zu schreiben.  
  
### <a name="capturing-the-graphics-information"></a>Erfassung der Grafikinformationen  
 Wenn Sie die App für die programmgesteuerte Erfassung vorbereitet und optional den Speicherort und den Namen der Grafikprotokolldatei konfiguriert haben, erstellen Sie die App, und führen Sie sie dann aus, oder debuggen Sie sie, um die Daten zu erfassen; starten Sie nicht die Grafikdiagnose aus [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , wenn Sie die API für die programmgesteuerte Erfassung verwenden. Das Grafikprotokoll wird in den von Ihnen angegebene Speicherort geschrieben. Wenn Sie diese Version des Protokolls behalten möchten, verschieben Sie sie an einen anderen Speicherort; andernfalls wird sie überschrieben, wenn Sie die App erneut ausführen.  
  
> [!TIP]
>  Sie können Grafikinformationen auch während der programmgesteuerten Erfassung weiterhin manuell erfassen – drücken Sie einfach **Bildschirm drucken**, während die App aufgerufen ist. Sie können dieses Verfahren anwenden, um zusätzliche Grafikinformationen zu erfassen, die nicht von der API für die programmgesteuerte Erfassung erfasst werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 In dieser exemplarische Vorgehensweise wurde veranschaulicht, wie Grafikinformationen programmatisch erfasst werden. Im nächsten Schritt haben Sie folgende Möglichkeit:  
  
-   Erfahren Sie, wie Sie erfasste Grafikinformationen mithilfe der Grafikdiagnose-Tools analysieren können. Finden Sie unter [Übersicht](overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Aufzeichnen von Grafikinformationen](walkthrough-capturing-graphics-information.md)   
 [Aufzeichnen von Grafikinformationen](capturing-graphics-information.md)   
 [Befehlszeilen-Erfassungstool](command-line-capture-tool.md)