---
title: 'CA1708: Bezeichner sollten sich durch die Groß-/Kleinschreibung unterscheiden.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4fd2ac35d5c6df5e1ffc3d49ea3089bb4ee3ea77
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53833244"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: Bezeichner sollten sich durch die Groß-/Kleinschreibung unterscheiden.

|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|Kategorie|Microsoft.Naming|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Die Namen von zwei Typen, Member, Parameter oder den vollqualifizierten Namespaces sind identisch, wenn sie in Kleinbuchstaben konvertiert wurden.

## <a name="rule-description"></a>Regelbeschreibung
 Bezeichner für Namespaces, Typen, Member und Parameter dürfen sich nicht nur durch die Groß-/Kleinschreibung unterscheiden, weil Sprachen, die auf die Common Language Runtime abzielen, nicht zwischen Groß- und Kleinschreibung unterscheiden müssen. Z. B. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] ist eine weit verbreitete Sprache, Groß-/Kleinschreibung.

 Mit dieser Regel wird für öffentlich sichtbaren Member nur ausgelöst werden.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Wählen Sie einen Namen, der eindeutig ist, wenn er mit anderen Bezeichnern in Groß-und Kleinschreibung verglichen wird.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Unterdrücken Sie keine Warnung dieser Regel. Die Bibliothek kann nicht in allen verfügbaren Sprachen in .NET Framework verwendet werden.

## <a name="example-of-a-violation"></a>Beispiel eines Verstoßes
 Das folgende Beispiel zeigt einen Verstoß gegen diese Regel.

 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]

## <a name="related-rules"></a>Verwandte Regeln
 [CA1709: Bezeichner sollten beachtet werden](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)