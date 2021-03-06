---
title: StartProfile | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- StartProfile
ms.assetid: 1761311d-c9d5-48f5-b1f8-b3605829940a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d08c2041d0432bb215b46401521583c921bcbc92
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49934891"
---
# <a name="startprofile"></a>StartProfile
Die `StartProfile`-Funktion legt den Zähler für die angegebene Profilerstellungsebene auf 1 (ON) fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
PROFILE_COMMAND_STATUS PROFILERAPI StartProfile(  
                        PROFILE_CONTROL_LEVEL Level,   
                        unsigned int dwId);  
```  
  
#### <a name="parameters"></a>Parameter  
 `Level`  
  
 Gibt die Profilebene an, auf die die Sammlung von Leistungsdaten angewendet werden kann. Die folgenden **PROFILE_CONTROL_LEVEL**-Enumeratoren können verwendet werden, um eine der drei Ebenen anzugeben, auf die die Sammlung der Leistungsdaten angewendet werden kann:  
  
|Enumerator|Beschreibung |  
|----------------|-----------------|  
|PROFILE_GLOBALLEVEL|Die Einstellung globaler Ebene wirkt sich auf alle Prozesse und Threads bei der Profilerstellung aus.|  
|PROFILE_PROCESSLEVEL|Die Einstellung auf Prozessebene wirkt sich auf alle Threads aus, die Teil des angegebenen Prozesses sind.|  
|PROFILE_THREADLEVEL|Die Einstellung auf Threadebene der Profilerstellung wirkt sich auf den angegebenen Thread aus.|  
  
 `dwId`  
  
 Der Prozess- oder Threadbezeichner, der vom System generiert wird.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Die Funktion gibt mithilfe der **PROFILE_COMMAND_STATUS**-Enumeration einen Erfolg oder Fehler an. Einer der folgenden Werte kann zurückgegeben werden:  
  
|Enumerator|Beschreibung |  
|----------------|-----------------|  
|PROFILE_ERROR_ID_NOEXIST|Die Profilerstellungselement-ID ist nicht vorhanden.|  
|PROFILE_ERROR_LEVEL_NOEXIST|Die angegebene Profilerstellungsebene ist nicht vorhanden.|  
|PROFILE_ERROR_MODE_NEVER|Der Profilerstellungsmodus wurde beim Aufruf der Funktion auf NEVER festgelegt.|  
|PROFILE_ERROR_NOT_YET_IMPLEMENTED|Der Funktionsaufruf der Profilerstellung, die Profilerstellungsebene oder eine Kombination aus dem Aufruf und der Ebene sind noch nicht implementiert.|  
|PROFILE_OK|Der Aufruf war erfolgreich.|  
  
## <a name="remarks"></a>Hinweise  
 StartProfile und StopProfile steuern den Start/Stop-Status der Profilerstellungsebene. Der Standardwert von Start/Stop ist 1. Der Anfangswert kann in der Registrierung geändert werden. Jeder Aufruf von StartProfile legt den Zähler von Start/Stop auf 1 fest, jeder Aufruf von StopProfile legt ihn auf 0 fest.  
  
 Wenn Start/Stop größer als 0 (null) ist, wird der Status von Start/Stop der Ebene auf ON festgelegt. Wenn Start/Stop kleiner oder gleich 0 (null) ist, wird der Status von Start/Stop auf OFF festgelegt.  
  
 Wenn sowohl der Status von Start/Stop als auch der von Suspend/Resume auf ON festgelegt ist, ist auch der Profilerstellungsstatus der Ebene auf ON festgelegt. Damit ein Profil für einen Thread erstellt werden kann, muss der Status des Threads auf globaler, Prozess- und Threadebene ON sein.  
  
## <a name="net-framework-equivalent"></a>.NET Framework-Entsprechung  
 *Microsoft.VisualStudio.Profiler.dll*  
  
## <a name="function-information"></a>Funktionsinformationen  
 Header: in *VSPerf.h* deklariert  
  
 Importbibliothek: *VSPerf.lib*  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht den StartProfile-Funktionsaufruf.  
  
```cpp  
void ExerciseStartProfile()  
{  
    // StartProfile and StopProfile control the  
    // Start/Stop state for the profiling level.   
    // The default initial value of Start/Stop is 1.   
    // The initial value can be changed in the registry.   
    // Each call to StartProfile sets Start/Stop to 1;   
    // each call to StopProfile sets it to 0.   
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare enumeration to hold return value of   
    // the call to StartProfile.  
    PROFILE_COMMAND_STATUS profileResult;  
  
    profileResult = StartProfile(  
        PROFILE_THREADLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("StartProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, profileResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz für Profiler-APIs in Visual Studio (nativ)](../profiling/visual-studio-profiler-api-reference-native.md)