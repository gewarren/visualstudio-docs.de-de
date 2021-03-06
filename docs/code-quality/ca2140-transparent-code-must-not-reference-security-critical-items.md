---
title: 'CA2140: Transparenter Code muss nicht auf sicherheitskritische Elemente verweisen.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2129
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2140
helpviewer_keywords:
- CA2140
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2129
ms.assetid: 251a12da-0557-47f5-a4f7-0229d590ae7b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d434094cff19cbeac2ba1b363a82ab1577f8220
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53860714"
---
# <a name="ca2140-transparent-code-must-not-reference-security-critical-items"></a>CA2140: Transparenter Code muss nicht auf sicherheitskritische Elemente verweisen.

|||
|-|-|
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|
|CheckId|CA2140|
|Kategorie|Microsoft.Security|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache

Eine transparente Methode:

- verarbeitet einen Sicherheit sicherheitsrelevanten Ausnahmetyp

- verfügt über einen Parameter, der als einen sicherheitskritischen Typ gekennzeichnet ist.

- verfügt über einen generischen Parameter mit einem kritischen sicherheitseinschränkungen

- verfügt über eine lokale Variable, der einen sicherheitskritischen Typ

- verweist auf einen Typ, der als sicherheitskritisch markiert ist

- Ruft eine Methode, die als sicherheitskritisch markiert ist

- verweist auf ein Feld, die als sicherheitskritisch markiert ist

- Gibt einen Typ, der als sicherheitskritisch markiert ist

## <a name="rule-description"></a>Regelbeschreibung

Ein Codeelement an, die mit der <xref:System.Security.SecurityCriticalAttribute> -Attribut ist sicherheitskritisch. Eine transparente Methode kann kein sicherheitskritisches Element verwenden. Wenn ein transparenter Typ versucht, einen sicherheitskritischen Typ zu verwenden eine <xref:System.TypeAccessException>, <xref:System.MethodAccessException> , oder <xref:System.FieldAccessException> ausgelöst wird.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen

Führen Sie eine der folgenden Schritte aus, um einen Verstoß gegen diese Regel zu beheben:

- Markieren Sie das Codeelement, das die sicherheitskritischem Code mit verwendet die <xref:System.Security.SecurityCriticalAttribute> Attribut

     \- oder –

- Entfernen Sie die <xref:System.Security.SecurityCriticalAttribute> Attribut aus den Codeelementen, die als sicherheitskritisch markiert sind, und markieren Sie sie mit stattdessen die <xref:System.Security.SecuritySafeCriticalAttribute> oder <xref:System.Security.SecurityTransparentAttribute> Attribut.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken

Unterdrücken Sie keine Warnung dieser Regel.

## <a name="example"></a>Beispiel

Eine transparente Methode versucht, in den folgenden Beispielen wird eine generische Auflistung mit Sicherheit wichtig, ein sicherheitskritisches Feld und eine wichtige Methode verweisen.

[!code-csharp[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../code-quality/codesnippet/CSharp/ca2140-transparent-code-must-not-reference-security-critical-items_1.cs)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Security.SecurityTransparentAttribute>
- <xref:System.Security.SecurityCriticalAttribute>
- <xref:System.Security.SecurityTransparentAttribute>
- <xref:System.Security.SecurityTreatAsSafeAttribute>
- <xref:System.Security?displayProperty=fullName>