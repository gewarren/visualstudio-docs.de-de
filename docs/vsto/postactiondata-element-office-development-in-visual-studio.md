---
title: '&lt;PostActionData&gt; -Element (Office-Entwicklung in Visual Studio)'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- <postActionData> element
- application manifests [Office development in Visual Studio], <postActionData> element
- postActionData element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f27cf59f157c0760ea0c204a8c079dd4616777da
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53947269"
---
# <a name="ltpostactiondatagt-element-office-development-in-visual-studio"></a>&lt;PostActionData&gt; -Element (Office-Entwicklung in Visual Studio)
  Das `postActionData` -Element des `vstav3` -Namespace gibt die Daten an, die jeder Aktion nach der Bereitstellung zugeordnet sind, die nach der Installation von Office-Projektmappen ausgeführt wird.

## <a name="syntax"></a>Syntax

```xml
<postActionData>
</postActionData>
```

## <a name="elements-and-attributes"></a>Elemente und Attribute
 Das `postActionData` -Element ist optional und befindet sich im `vstav3` -Namespace. In einem Anwendungsmanifest ist für jede Aktion nach der Bereitstellung ein `postActionData` -Element definiert.

 Das `postActions`-Element weist keine Attribute auf.

 `postActions` hat keine untergeordneten Elemente.

## <a name="post-deployment-action-example"></a>Beispiel für die Aktion nach der Bereitstellung

### <a name="description"></a>Beschreibung
 Das folgende Codebeispiel veranschaulicht das `postAction` -Element in einem Anwendungsmanifest für eine mit [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]bereitgestellte Office-Projektmappe. Dieses Codebeispiel ist Teil eines umfangreicheren Beispiels [Anwendungsmanifeste für Office-Projektmappen](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Code

```xml
<vstav3:postActionData>
  data in any format
</vstav3:postActionData>
```

## <a name="see-also"></a>Siehe auch

- [Anwendungsmanifeste für Office-Projektmappen](../vsto/application-manifests-for-office-solutions.md)
- [Bereitstellungsmanifeste für Office-Projektmappen](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce-Anwendungsmanifest](../deployment/clickonce-application-manifest.md)
