---
title: 'CA1713: Ereignisse sollten kein Before- oder after-Präfix aufweisen.'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- EventsShouldNotHaveBeforeOrAfterPrefix
- CA1713
helpviewer_keywords:
- CA1713
- EventsShouldNotHaveBeforeOrAfterPrefix
ms.assetid: 855772a4-aa9e-410b-88c1-c5fba1ca63da
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f5133cf03567eabab9eea95b7fadc52304a1d7c9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53890747"
---
# <a name="ca1713-events-should-not-have-before-or-after-prefix"></a>CA1713: Ereignisse sollten kein Before- oder after-Präfix aufweisen.

|||
|-|-|
|TypeName|EventsShouldNotHaveBeforeOrAfterPrefix|
|CheckId|CA1713|
|Kategorie|Microsoft.Naming|
|Unterbrechende Änderung|Breaking|

## <a name="cause"></a>Ursache
 Der Name eines Ereignisses beginnt mit 'Before' oder 'After'.

## <a name="rule-description"></a>Regelbeschreibung
 Ereignisnamen sollte die Aktion beschreiben, die das Ereignis auslöst. Um verwandte Ereignisse zu benennen, die in einer bestimmten Reihenfolge ausgelöst werden, verwenden Sie die Gegenwarts- oder Vergangenheitsform, um ihre relative Position in der Aktionsfolge anzugeben. Z. B. bei der Benennung von ein Paar von Ereignissen, die ausgelöst wird, wenn eine Ressource zu schließen, können Sie es "Closing" und "Closed" anstelle von "BeforeClose" und "AfterClose" nennen.

 Durch Benennungskonventionen erhalten Bibliotheken, die auf die Common Language Runtime abzielen, ein einheitliches Erscheinungsbild. Dadurch wird der Lernaufwand für neue Softwarebibliotheken verringert. Zudem wird das Kundenvertrauen dahingehend gestärkt, dass die Bibliothek von einem erfahrenen Entwickler für verwalteten Code erstellt wurde.

## <a name="how-to-fix-violations"></a>Behandeln von Verstößen
 Entfernen Sie das Präfix aus der Ereignisname, und ändern Sie den Namen, die die Gegenwarts- oder Vergangenheitsform, ein Verb zu verwenden.

## <a name="when-to-suppress-warnings"></a>Wenn Sie Warnungen unterdrücken
 Unterdrücken Sie keine Warnung dieser Regel.