---
title: 'CA2239: Geben Sie Deserialisierungsmethoden für optionale Felder | Microsoft-Dokumentation'
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
- CA2239
- ProvideDeserializationMethodsForOptionalFields
helpviewer_keywords:
- ProvideDeserializationMethodsForOptionalFields
- CA2239
ms.assetid: 6480ff5e-0caa-4707-814e-2f927cdafef5
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d3054e12261701702c25d6164d2a2d85ead3a202
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49877269"
---
# <a name="ca2239-provide-deserialization-methods-for-optional-fields"></a>CA2239: Deserialisierungsmethoden für optionale Felder angeben
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ProvideDeserializationMethodsForOptionalFields|
|CheckId|CA2239|
|Kategorie|Microsoft.Usage|
|Unterbrechende Änderung|Nicht unterbrechende Änderung|

## <a name="cause"></a>Ursache
 Ein Typ verfügt über ein Feld, das mit markiert ist die <xref:System.Runtime.Serialization.OptionalFieldAttribute?displayProperty=fullName> -Attribut und der Typ stellt keine Deserialisierung Ereignisbehandlungsmethoden bereit.

## <a name="rule-description"></a>Regelbeschreibung
 Die <xref:System.Runtime.Serialization.OptionalFieldAttribute> Attribut hat keine Auswirkungen, bei der Serialisierung, ein Feld mit dem Attribut markiert wird serialisiert. Allerdings wird das Feld wird bei der Deserialisierung ignoriert, und behält den Standardwert, der mit dem Typ verknüpft ist. Ereignishandler für die Deserialisierung müssen deklariert werden, um das Feld festgelegt werden, während der Deserialisierung.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Um einen Verstoß gegen diese Regel zu beheben, fügen Sie Methoden in den Typ Deserialisierungsereignisbehandlung hinzu.

## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?
 Es ist sicher eine Warnung dieser Regel zu unterdrücken, wenn das Feld während der Deserialisierung ignoriert werden sollen.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt einen Typ mit einem optionalen Feld und die Deserialisierungsereignisbehandlung Methoden für die Behandlung.

 [!code-csharp[FxCop.Usage.OptionalFields#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OptionalFields/cs/FxCop.Usage.OptionalFields.cs#1)]
 [!code-vb[FxCop.Usage.OptionalFields#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.OptionalFields/vb/FxCop.Usage.OptionalFields.vb#1)]

## <a name="related-rules"></a>Verwandte Regeln
 [CA2236: Basisklassenmethoden auf ISerializable-Typen aufrufen](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: ISerializable ordnungsgemäß implementieren](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Serialisierungskonstruktoren implementieren](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Serialisierungsmethoden korrekt implementieren](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: Alle nicht serialisierbaren Felder markieren](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237: Markieren von ISerializable-Typen mit SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2120: Sichere Serialisierungskonstruktoren](../code-quality/ca2120-secure-serialization-constructors.md)



