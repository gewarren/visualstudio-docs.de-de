---
title: 'CA1047: Geschützte Member in versiegelten Typen nicht deklarieren'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b46e64fb4092f8e0f773671ff13eb401b6b67890
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53912853"
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047: Geschützte Member in versiegelten Typen nicht deklarieren

|||
|-|-|
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|
|CheckId|CA1047|
|Kategorie|Microsoft.Design|
|Unterbrechende Änderung|Nicht unterbrechend|

## <a name="cause"></a>Ursache
 Ist ein öffentlicher Typ `sealed` (`NotInheritable` in Visual Basic), und deklarieren Sie einen geschützten Member oder einen geschützten geschachtelten Typ. Diese Regel meldet keine Verstöße für <xref:System.Object.Finalize%2A> -Methoden, die diesem Muster folgen müssen.

## <a name="rule-description"></a>Regelbeschreibung
 Typen deklarieren geschützte Member, damit erbende Typen auf den Member zugreifen oder diesen überschreiben können. Per Definition können nicht Sie aus einem versiegelten Typ erben, d. h., die geschützten Methoden in versiegelten Typen nicht aufgerufen werden kann.

 Der c#-Compiler gibt eine Warnung für diesen Fehler.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, ändern Sie die Zugriffsebene des Members in privat, oder ändern Sie den Typ geerbt.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Unterdrücken Sie keine Warnung dieser Regel. Verlassen den Typ im aktuellen Zustand kann dazu führen, dass Wartungsprobleme und bietet keine Vorteile.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt einen Typ, der gegen diese Regel verstößt.

 [!code-vb[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/VisualBasic/ca1047-do-not-declare-protected-members-in-sealed-types_1.vb)]
 [!code-csharp[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/CSharp/ca1047-do-not-declare-protected-members-in-sealed-types_1.cs)]