---
title: Elementfunktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild, Item functions
ms.assetid: 5e6df3cc-2db8-4cbd-8fdd-3ffd03ac0876
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 85dd03080a9dda58532d656161c3c44ae4943251
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2018
ms.locfileid: "39081347"
---
# <a name="item-functions"></a>Elementfunktionen
Ab MSBuild 4.0 kann Code in Tasks und Zielen Elementfunktionen aufrufen, um Informationen zu den Elementen des Projekts zu erhalten. Diese Funktionen vereinfachen das Abrufen von Distinct()-Elementen, und mit ihnen erfolgt der Abruf schneller als beim Durchlaufen der Elemente.  
  
## <a name="string-item-functions"></a>Zeichenfolgenelementfunktionen  
 Sie können Zeichenfolgenmethoden und -eigenschaften in .NET Framework für jeden Elementwert verwenden. Geben Sie für <xref:System.String>-Methoden den Methodennamen an. Geben Sie für <xref:System.String>-Eigenschaften den Eigenschaftennamen hinter „get_“ an.  
  
 Für Elemente mit mehreren Zeichenfolgen wird die Zeichenfolgenmethode oder -eigenschaft für jede Zeichenfolge ausgeführt.  
  
 Das folgende Beispiel veranschaulicht die Verwendung dieser Zeichenfolgenelementfunktionen.  
  
```xml  
<ItemGroup>  
    <theItem Include="andromeda;tadpole;cartwheel" />  
</ItemGroup>  
  
<Target Name = "go">  
    <Message Text="IndexOf  @(theItem->IndexOf('r'))" />  
    <Message Text="Replace  @(theItem->Replace('tadpole', 'pinwheel'))" />  
    <Message Text="Length   @(theItem->get_Length())" />  
    <Message Text="Chars    @(theItem->get_Chars(2))" />  
</Target>  
  
  <!--  
  Output:  
    IndexOf  3;-1;2  
    Replace  andromeda;pinwheel;cartwheel  
    Length   9;7;9  
    Chars    d;d;r  
  -->  
```  
  
## <a name="intrinsic-item-functions"></a>Intrinsische Elementfunktionen  
 In der unten stehenden Tabelle werden die systeminternen Funktionen aufgelistet, die für Elemente zur Verfügung stehen.  
  
|Funktion|Beispiel|Beschreibung |  
|--------------|-------------|-----------------|  
|`Count`|`@(MyItem->Count())`|Gibt die Anzahl der Elemente zurück|  
|`DirectoryName`|`@(MyItem->DirectoryName())`|Gibt das entsprechende `Path.DirectoryName`-Objekt für jedes Element zurück|  
|`Distinct`|`@(MyItem->Distinct())`|Gibt Elemente zurück, die eindeutige `Include`-Werte aufweisen Metadaten werden ignoriert. Beim Vergleich wird die Groß- und Kleinschreibung nicht berücksichtigt.|  
|`DistinctWithCase`|`@(MyItem->DistinctWithCase())`|Gibt Elemente zurück, die eindeutige `itemspec`-Werte aufweisen Metadaten werden ignoriert. Beim Vergleich wird die Groß- und Kleinschreibung berücksichtigt.|  
|`Reverse`|`@(MyItem->Reverse())`|Gibt die Elemente in umgekehrter Reihenfolge zurück|  
|`AnyHaveMetadataValue`|`@(MyItem->AnyHaveMetadataValue("MetadataName", "MetadataValue"))`|Gibt einen `boolean`-Wert zurück, der angibt, ob ein Element einen angegebenen Metadatennamen und -wert aufweist. Beim Vergleich wird die Groß- und Kleinschreibung nicht berücksichtigt.|  
|`ClearMetadata`|`@(MyItem->ClearMetadata())`|Gibt Elemente mit gelöschten Metadaten zurück. Nur das `itemspec`-Objekt wird beibehalten.|  
|`HasMetadata`|`@(MyItem->HasMetadata("MetadataName"))`|Gibt Elemente zurück, die den angegebenen Metadatennamen aufweisen Beim Vergleich wird die Groß- und Kleinschreibung nicht berücksichtigt.|  
|`Metadata`|`@(MyItem->Metadata("MetadataName"))`|Gibt die Werte der Metadaten zurück, die den Metadatennamen aufweisen|  
|`WithMetadataValue`|`@(MyItem->WithMetadataValue("MetadataName", "MetadataValue"))`|Gibt Elemente zurück, die den angegebenen Metadatennamen und -wert aufweisen. Beim Vergleich wird die Groß- und Kleinschreibung nicht berücksichtigt.|  
  
 In folgendem Beispiel wird veranschaulicht, wie Sie systeminterne Elementfunktionen verwenden können.  
  
```xml  
<ItemGroup>  
    <TheItem Include="first">  
        <Plant>geranium</Plant>  
    </TheItem>  
    <TheItem Include="second">  
        <Plant>algae</Plant>  
    </TheItem>  
    <TheItem Include="third">  
        <Plant>geranium</Plant>  
    </TheItem>  
</ItemGroup>  
  
<Target Name="go">  
    <Message Text="MetaData:    @(TheItem->Metadata('Plant'))" />  
    <Message Text="HasMetadata: @(theItem->HasMetadata('Plant'))" />  
    <Message Text="WithMetadataValue: @(TheItem->WithMetadataValue('Plant', 'geranium'))" />  
    <Message Text=" " />  
    <Message Text="Count:   @(theItem->Count())" />  
    <Message Text="Reverse: @(theItem->Reverse())" />  
</Target>  
  
  <!--   
  Output:  
    MetaData:    geranium;algae;geranium  
    HasMetadata: first;second;third  
    WithMetadataValue: first;third  
  
    Count:   3  
    Reverse: third;second;first  
  -->  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Elemente](../msbuild/msbuild-items.md)
