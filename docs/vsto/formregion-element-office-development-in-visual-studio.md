---
title: '&lt;FormRegion&gt; -Element (Office-Entwicklung in Visual Studio)'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <formRegion> element
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 86aa6b715a99c962a2f0fd627dd6d3fb7618108a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53987692"
---
# <a name="ltformregiongt-element-office-development-in-visual-studio"></a>&lt;FormRegion&gt; -Element (Office-Entwicklung in Visual Studio)
  Die `formRegion` Element der `vstov4` Namespace identifiziert einen Microsoft Office Outlook-Formularbereich, der einem VSTO-Add-in zugeordnet ist.

## <a name="syntax"></a>Syntax

```xml
<formRegion
  name>
  <messageClass
    name/>
</formRegion>
```

## <a name="elements-and-attributes"></a>Elemente und Attribute
 Das `formRegion` -Element des `vstov4` -Namespace identifiziert einen Formularbereich, der einem VSTO-Add-In für Outlook zugeordnet ist. Es ist nur für Outlook-VSTO-Add-Ins erforderlich, die Formularbereiche einbeziehen.

 Es können mehrere `formRegion` -Elemente in einem `formRegions` -Element für ein einzelnes VSTO-Add-In definiert sein.

 Das `formRegion` -Element hat das folgende Attribut.

|Attribut|Beschreibung|
|---------------|-----------------|
|`name`|Erforderlich. Gibt den Namen des Formularbereichs an.|

 Das `formRegion` -Element weist die folgenden untergeordneten Elemente auf.

### <a name="messageclass"></a>messageClass
 Das `messageClass` -Element identifiziert das Outlook-Formular, das dem Formularbereich zugeordnet ist.

 Das `messageClass` -Element hat das folgende Attribut.

|Attribut|Beschreibung|
|---------------|-----------------|
|`name`|Erforderlich. Identifiziert das Formular, das dem Formularbereich zugeordnet ist.|

## <a name="example"></a>Beispiel
 Das folgende Codebeispiel veranschaulicht ein `formRegion` -Element in einem Anwendungsmanifest für ein mit [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]bereitgestelltes Outlook-VSTO-Add-In. Es gibt drei Nachrichtenklassen, die diesem einen Formularbereich zugeordnet sind. Dieses Codebeispiel ist Teil eines umfangreicheren Beispiels [Anwendungsmanifeste für Office-Projektmappen](../vsto/application-manifests-for-office-solutions.md).

```xml
<vstov4:formRegion
    name="OutlookAddIn1.FormRegion1">
  <vstov4:messageClass name="IPM.Note" />
  <vstov4:messageClass name="IPM.Contact" />
  <vstov4:messageClass name="IPM.Appointment" />
</vstov4:formRegion>
```

## <a name="see-also"></a>Siehe auch

- [Erstellen von Outlook-Formularbereichen](../vsto/creating-outlook-form-regions.md)
- [Anwendungsmanifeste für Office-Projektmappen](../vsto/application-manifests-for-office-solutions.md)
- [Bereitstellungsmanifeste für Office-Projektmappen](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce-Anwendungsmanifest](../deployment/clickonce-application-manifest.md)