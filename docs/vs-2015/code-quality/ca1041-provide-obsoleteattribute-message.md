---
title: 'CA1041: ObsoleteAttribute-Meldung bereitstellen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f67bbd93816da3bcae389493b74623f0cf4776c0
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49914722"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: ObsoleteAttribute-Meldung bereitstellen
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|Kategorie|Microsoft.Design|
|Unterbrechende Änderung|Nicht unterbrechend|

## <a name="cause"></a>Ursache
 Einen Typ oder Member ist markiert, indem eine <xref:System.ObsoleteAttribute?displayProperty=fullName> -Attribut, das nicht der <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> angegebene Eigenschaft.

## <a name="rule-description"></a>Regelbeschreibung
 <xref:System.ObsoleteAttribute> Dient zum Kennzeichnen als veraltet markierte von Bibliothekstypen und Member. Consumer sollten die Verwendung von einem beliebigen Typ oder Member, der als veraltet markiert ist. Dies ist, da er möglicherweise nicht unterstützt und in späteren Versionen der Bibliothek entfernt werden. Wenn ein Typ oder Member mit markiert <xref:System.ObsoleteAttribute> kompiliert wurde, die <xref:System.ObsoleteAttribute.Message%2A> -Eigenschaft des Attributs wird angezeigt. Auf diese Weise erhält der Benutzer Informationen zum veralteten Typ oder Member. Diese Informationen umfassen im Allgemeinen, wie langen den veralteten Typ oder Member wird von der Bibliotheks-Designer und die bevorzugte Ersetzung verwenden unterstützt.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, fügen die `message` Parameter, um die <xref:System.ObsoleteAttribute> Konstruktor.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Unterdrücken Sie eine Warnung dieser Regel nicht, da die <xref:System.ObsoleteAttribute.Message%2A> Eigenschaft enthält wichtige Informationen zu den veralteten Typ oder Member.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt einen veralteten Member, die einer ordnungsgemäß deklarierten <xref:System.ObsoleteAttribute>.

 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cpp/FxCop.Design.ObsoleteAttributeOnMember.cpp#1)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cs/FxCop.Design.ObsoleteAttributeOnMember.cs#1)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/vb/FxCop.Design.ObsoleteAttributeOnMember.vb#1)]

## <a name="see-also"></a>Siehe auch
 <xref:System.ObsoleteAttribute?displayProperty=fullName>



