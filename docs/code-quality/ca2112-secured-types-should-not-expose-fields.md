---
title: 'CA2112: Gesicherte Typen sollten keine Felder verfügbar machen.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d4786b51536d9df7c51c8551b5fbd8d863879875
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53920403"
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112: Gesicherte Typen sollten keine Felder verfügbar machen.

|||
|-|-|
|TypeName|SecuredTypesShouldNotExposeFields|
|CheckId|CA2112|
|Kategorie|Microsoft.Security|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Ein öffentlicher oder geschützter Typ enthält öffentliche Felder und wird geschützt, indem eine [Verknüpfungsaufrufe](/dotnet/framework/misc/link-demands).

## <a name="rule-description"></a>Regelbeschreibung
 Wenn Code auf eine Instanz eines Typs zugreifen muss, der durch einen Linkaufruf gesichert ist, muss der Code für den Zugriff auf die Felder des Typs nicht die Anforderungen des Linkaufrufs erfüllen.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, legen Sie die Felder als nicht öffentlich, und fügen Sie öffentliche Eigenschaften oder Methoden, die die Felddaten zurückgeben. LinkDemand-sicherheitsüberprüfungen für Typen Schützen des Zugriffs auf die Eigenschaften und Methoden des Typs. Codezugriffssicherheit gilt jedoch nicht auf Felder.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Für Sicherheitsprobleme und ein guter Entwurf sollten Sie Regelverstöße beheben, dazu nicht öffentlichen öffentliche Felder. Sie können eine Warnung dieser Regel unterdrücken, wenn das Feld keine Informationen enthält, die gesichert bleiben soll, und Sie verlassen sich nicht auf den Inhalt des Felds.

## <a name="example"></a>Beispiel
 Im folgende Beispiel besteht aus einem Typ "Klassenbibliothek" (`SecuredTypeWithFields`) für unsichere Felder, die einen Typ (`Distributor`), die Instanzen des Typs Bibliothek erstellen, falsche übergibt-Instanzen, um Typen sind nicht berechtigt, diese zu erstellen und Anwendungscode, der können eine Instanz der Felder zu lesen, obwohl sie nicht über die Berechtigung verfügt, die den Typ sichert.

 Der folgende Bibliothekscode verstößt gegen die Regel.

 [!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]

## <a name="example-1"></a>Beispiel 1
 Die Anwendung kann nicht aufgrund der Linkaufruf, der den gesicherten Typ schützt, eine Instanz erstellen. Die folgende Klasse ermöglicht die Anwendung um eine Instanz des gesicherten Typs abzurufen.

 [!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]

## <a name="example-2"></a>Beispiel 2
 Die folgende Anwendung dargestellt, ohne Berechtigungen für den Zugriff auf eine gesicherte Typ-Methoden, Code die Felder zugreifen kann.

 [!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]

Dieses Beispiel erzeugt die folgende Ausgabe:

```txt
Creating an instance of SecuredTypeWithFields.
Secured type fields: 22, 33
Changing secured type's field...
Cached Object fields: 99, 33
```

## <a name="related-rules"></a>Verwandte Regeln

- [CA1051: Sichtbare Instanzfelder nicht deklarieren](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)

## <a name="see-also"></a>Siehe auch

- [Verknüpfungsaufrufe](/dotnet/framework/misc/link-demands)
- [Daten und Modellierung](/dotnet/framework/data/index)