---
title: T4-Vorlagenanweisung
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 337560d6db6d8747b1aedd23d789f2ef56d045c9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53885287"
---
# <a name="t4-template-directive"></a>T4-Vorlagenanweisung

Eine Visual Studio T4-Textvorlage beginnt normalerweise mit einer `template` Anweisung, die angibt, wie die Vorlage verarbeitet werden sollen. In einer Textvorlage und allen darin enthaltenen Dateien darf nur eine Vorlagenanweisung vorhanden sein.

Eine allgemeine Übersicht über das Schreiben von Textvorlagen finden Sie unter [Schreiben einer T4-Textvorlage](../modeling/writing-a-t4-text-template.md).

## <a name="using-the-template-directive"></a>Verwenden der Vorlagenanweisung

```
<#@ template [language="VB"] [compilerOptions="options"] [culture="code"] [debug="true"] [hostspecific="true"] [inherits="templateBaseClass"] [visibility="internal"] [linePragmas="false"] #>
```

Die `template`-Anweisung besitzt mehrere Attribute, mit denen Sie verschiedene Aspekte der Transformation angeben können. Alle Attribute sind optional.

## <a name="compileroptions-attribute"></a>compilerOptions-Attribut

Beispiel:

`compilerOptions="optimize+"`

Gültige Werte:
 
Alle gültigen Compileroptionen.

Ignoriert für Laufzeitvorlagen (vorverarbeitete Vorlagen).

Diese Optionen werden übernommen, wenn die Vorlage in [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] oder [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)] konvertiert wurde. Der daraus resultierende Code wird kompiliert.

## <a name="culture-attribute"></a>Kulturattribut

Beispiel:
 
`culture="de-CH"`

Gültige Werte:
 
"", die invariante Kultur (Standard).

Eine als Zeichenfolge im Format xx-XX ausgedrückte Kultur. Beispiel: en-US, ja-JP, de-CH, de-DE. Weitere Informationen finden Sie unter <xref:System.Globalization.CultureInfo?displayProperty=fullName>.

Das Kulturattribut gibt die Kultur an, die verwendet werden soll, wenn ein Ausdrucksblock in Text konvertiert wird.

## <a name="debug-attribute"></a>debug-Attribut

Beispiel:

```
debug="true"
```

Gültige Werte:
 
`true`
 
`false` (Standardwert)
 
Wenn das `debug`-Attribut `true` ist, enthält die Zwischencodedatei Informationen, mit denen der Debugger genauer die Position in der Vorlage erkennen kann, an der eine Unterbrechung oder Ausnahme aufgetreten ist.

Für Entwurfszeitvorlagen wird die Zwischencodedatei in geschrieben Ihre **% TEMP%** Verzeichnis.

Um eine Entwurfszeitvorlage im Debugger auszuführen, speichern Sie die Textvorlage, und klicken Sie dann im Kontextmenü der Textvorlage im Projektmappen-Explorer öffnen, und wählen **T4-Vorlage Debuggen**.

## <a name="hostspecific-attribute"></a>hostspecific-Attribut

Beispiel:

```
hostspecific="true"
```

Gültige Werte:

`true`
 
`false` (Standardwert)
 
`trueFromBase`

Wenn Sie den Wert dieses Attributs auf `true` festlegen, wird der von der Textvorlage generierten Klasse eine Eigenschaft mit dem Namen `Host` hinzugefügt. Die Eigenschaft ist ein Verweis auf den Host des Transformations-Engine und wird als <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> deklariert. Wenn Sie einen benutzerdefinierten Host definiert haben, können Sie ihn in den benutzerdefinierten Hosttyp umwandeln.

Da der Typ dieser Eigenschaft vom Typ des Hosts abhängt, ist sie nur nützlich, wenn Sie eine Textvorlage schreiben, für die ein bestimmter Host verwendet werden muss. Es gilt für [Entwurfszeitvorlagen](../modeling/design-time-code-generation-by-using-t4-text-templates.md), aber nicht [Laufzeitvorlagen](../modeling/run-time-text-generation-with-t4-text-templates.md).

Wenn `hostspecific` ist `true` werden Sie mithilfe von Visual Studio, und Sie können eine Typumwandlung `this.Host` in IServiceProvider umwandeln, um den Zugriff auf Visual Studio-Features. Sie können den absoluten Pfad einer Datei im Projekt auch mithilfe von `Host.ResolvePath(filename)` abrufen. Zum Beispiel:

```csharp
<#@ template debug="false" hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#@ import namespace="EnvDTE" #>
<#@ import namespace="System.IO" #>
<#@ import namespace="Microsoft.VisualStudio.TextTemplating" #>
<# // Get the Visual Studio API as a service:
 DTE dte = ((IServiceProvider)this.Host).GetCOMService(typeof(DTE)) as DTE;
#>
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>

<#
 // Find a path within the current project:
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));
#>
Content of myFile is:
<#= myFile #>
```

Wenn Sie die Attribute `inherits` und `hostspecific` zusammen verwenden, geben Sie host="trueFromBase" in der abgeleiteten Klasse sowie host="true" in der Basisklasse an. Dies vermeidet eine doppelte Definition der Eigenschaft `Host` im generierten Code.

## <a name="language-attribute"></a>language-Attribut

Beispiel:

`language="VB"`

Gültige Werte:

`C#` (Standardwert)

`VB`

Die `language` Attribut gibt die Sprache ([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] oder [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]), die für den Quellcode in anweisungs- und ausdrucksblöcken verwendet. Die Zwischencodedatei, von der die Ausgabe generiert wird, verwendet diese Sprache. Diese Sprache bezieht sich nicht auf die Sprache, die von der Vorlage generiert wird, wobei es sich um eine beliebige Art von Text handeln kann.

Zum Beispiel:

```vb
<#@ template language="VB" #>
<#@ output extension=".txt" #>
Squares of numbers:
<#
  Dim number As Integer
  For number = 1 To 4
#>
  Square of <#= number #> is <#= number * number #>
<#
  Next number
#>
```

## <a name="inherits-attribute"></a>inherits-Attribut

Sie können angeben, dass der Programmcode der Vorlage von einer anderen Klasse erben kann, die auch mit einer Textvorlage generiert werden kann.

### <a name="inheritance-in-a-run-time-preprocessed-text-template"></a>Vererbung in einer Laufzeittextvorlage (vorverarbeiteten Textvorlage)

Sie können Vererbung zwischen Laufzeittextvorlagen verwenden, um eine Basisvorlage zu erstellen, die mehrere abgeleitete Varianten besitzt. Laufzeitvorlagen sind diejenigen, die die **benutzerdefiniertes Tool** -Eigenschaftensatz auf **TextTemplatingFilePreprocessor**. Eine Laufzeitvorlage generiert Code, den Sie in der Anwendung aufrufen können, um den in der Vorlage definierten Text zu erstellen. Weitere Informationen finden Sie unter [Run-Time-Textgenerierung mithilfe von T4-Textvorlagen](../modeling/run-time-text-generation-with-t4-text-templates.md).

Wenn Sie kein `inherits`-Attribut angeben, werden eine Basisklasse und eine abgeleitete Klasse von der Textvorlage generiert. Wenn Sie ein `inherits`-Attribut angeben, wird nur die abgeleitete Klasse generiert. Sie können eine Basisklasse manuell erstellen, doch sie muss über die Methoden verfügen, die von der abgeleiteten Klasse verwendet werden.

In der Regel geben Sie noch eine vorverarbeitete Vorlage als Basisklasse an. Die Basisvorlage beinhaltet allgemeine Textblöcke, die sich mit Text aus den abgeleiteten Vorlagen überlappen können. Sie können mithilfe von Klassenfunktionsblöcken (`<#+ ... #>`) Methoden definieren, die Textfragmente enthalten. Sie können z. B. das Framework des Ausgabetexts in der Basisvorlage platzieren und virtuelle Methoden bereitstellen, die in abgeleiteten Vorlagen überschrieben werden können:

Laufzeittextvorlage "BaseTemplate.tt" (vorverarbeitete Vorlage):

```scr
This is the common header.
<#
  SpecificFragment1();
#>
A common central text.
<#
  SpecificFragment2();
#>
This is the common footer.
<#+
  // Declare abstract methods
  protected virtual void SpecificFragment1() { }
  protected virtual void SpecificFragment2() { }
#>
```

Laufzeittextvorlage "DerivedTemplate1.tt" (vorverarbeitete Vorlage):

```csharp
<#@ template language="C#" inherits="BaseTemplate" #>
<#
  // Run the base template:
  base.TransformText();
#>
<#+
// Provide fragments specific to this derived template:
protected override void SpecificFragment1()
{
#>
   Fragment 1 for DerivedTemplate1
<#+
}
protected override void SpecificFragment2()
{
#>
   Fragment 2 for DerivedTemplate1
<#+
}
#>
```

 Anwendungscode zum Aufruf von "DerivedTemplate1":
 ```csharp
Console.WriteLine(new DerivedTemplate().TransformText());
```

 Ergebnis:
 ```
This is the common header.
   Fragment 1 for DerivedTemplate1
A common central text.
   Fragment 2 for DerivedTemplate1
This is the common footer.
```

Sie können die Basisklassen und die abgeleiteten Klassen in verschiedenen Projekten erstellen. Denken Sie daran, so das Basisprojekt oder die Assembly den Verweisen des abgeleiteten Projekts hinzu.

Sie können auch eine gewöhnliche, von Hand geschriebene Klasse als Basisklasse verwenden. Die Basisklasse muss die von der abgeleiteten Klasse verwendeten Methoden beinhalten.

> [!WARNING]
> Wenn Sie die Attribute `inherits` und `hostspecific` zusammen verwenden, geben Sie hostspecific="trueFromBase" in der abgeleiteten Klasse sowie host="true" in der Basisklasse an. Dies vermeidet eine doppelte Definition der Eigenschaft `Host` im generierten Code.

### <a name="inheritance-in-a-design-time-text-template"></a>Vererbung in einer Entwurfszeittextvorlage

Eine Entwurfszeit-Textvorlage ist eine Datei für die **benutzerdefiniertes Tool** nastaven NA hodnotu **TextTemplatingFileGenerator**. Die Vorlage erstellt eine Ausgabedatei mit Code oder Text, die Teil von Visual Studio-Projekt bildet. Um die Ausgabedatei zu generieren, wird die Vorlage zuerst in eine Zwischenprogrammcodedatei übersetzt, die normalerweise nicht sichtbar ist. Das `inherits`-Attribut gibt die Basisklasse für den Zwischencode an.

Für eine Entwurfszeittextvorlage können Sie jede Basisklasse angeben, die von <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName> abgeleitet wird. Verwenden Sie die `<#@assembly#>`-Anweisung, um die Assembly oder das Projekt zu laden, das die Basisklasse enthält.

Weitere Informationen finden Sie unter ["Vererbung in Textvorlagen" im Blog von Gareth Jones](http://go.microsoft.com/fwlink/?LinkId=208373).

## <a name="linepragmas-attribute"></a>LinePragmas-Attribut

Beispiel:

`linePragmas="false"`

Gültige Werte:

`true` (Standardwert)

`false`

Wenn dieses Attribut auf FALSE festgelegt ist, werden die Tags entfernt, die die Zeilennummern im generierten Codes identifizieren. Dies bedeutet, dass der Compiler alle Fehler anhand der Zeilennummern des generierten Codes meldet. Damit erhalten Sie mehr Debugoptionen, da Sie entweder die Textvorlage oder den generierten Code debuggen können.

Dieses Attribut auch hilfreich, wenn Sie erkennen, dass die absoluten Dateinamen in Pragmas irritierende Merges unter quellcodeverwaltung verursachen.

## <a name="visibility-attribute"></a>Sichtbarkeitsattribut

Beispiel:

`visibility="internal"`

Gültige Werte:

`public` (Standardwert)

`internal`

In einer Laufzeittextvorlage wird hiermit das Sichtbarkeitsattribut der generierten Klasse festgelegt. Standardmäßig ist die Klasse Teil der öffentliche API des Codes, aber indem Sie `visibility="internal"` festlegen, können Sie sicherstellen, dass nur der Code die textgenerierende Klasse verwenden kann.
