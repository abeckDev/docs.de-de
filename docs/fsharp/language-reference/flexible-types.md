---
title: Flexible Typen (F#)
description: Erfahren Sie, wie f# flexible typanmerkung verwendet wird, der angibt, dass ein Parameter, eine Variable oder ein Wert ein Typs mit einem angegebenen Typ kompatibel ist.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c8b510f2-3405-4cc9-b55b-e47b35e2b15b
ms.openlocfilehash: 7c5e4eb97791b9c6c56fe2847755866e8240e038
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2017
---
# <a name="flexible-types"></a>Flexible Typen

Ein *flexible typanmerkung* gibt an, dass ein Parameter, eine Variable oder ein Wert ein Typs ist kompatibel mit einem angegebenen Typ, in denen die Kompatibilität anhand der Position in einer objektorientierten Hierarchie von Klassen oder Schnittstellen bestimmt. Flexible Typen sind sinnvoll, insbesondere, wenn die automatische Konvertierung in Typen, die in der Hierarchie höher nicht erfolgt, aber immer noch die Funktionalität zum Arbeiten mit beliebigen Typs in der Hierarchie und für alle Typen, die eine Schnittstelle implementiert werden soll.

## <a name="syntax"></a>Syntax

```fsharp
#type
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *Typ* ein Basistyp oder eine Schnittstelle darstellt.

Ein flexibler Typ entspricht einem generischen Typ, der eine Einschränkung aufweist, die die zulässigen Typen für Typen beschränkt, die mit dem Typ Basis oder Schnittstelle kompatibel sind. D. h. entsprechen den folgenden zwei Codezeilen.

```fsharp
#SomeType

'T when 'T :> SomeType
```

Flexible Typen sind in verschiedenen Arten von Situationen nützlich. Bei einer Funktion höherer Ordnung (Funktion, die eine Funktion als Argument akzeptiert), ist es beispielsweise oft sinnvoll, verwenden die Funktion einen flexiblen Typ zurückgeben. Im folgenden Beispiel die Verwendung eines flexiblen Typs mit einem Sequenzargument in `iterate2` ermöglicht die Funktion höheren Ordnung arbeiten mit Funktionen, die Sequenzen, Arrays, Listen und aufzählbare andersartiges zu generieren.

Berücksichtigen Sie die folgenden beiden Funktionen, des welche eine Sequenz zurückgibt, von denen andere einen flexiblen Typ zurückgibt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

Betrachten Sie als weiteres Beispiel die [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) Library-Funktion:

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

Sie können eine der folgenden aufzählbaren Sequenzen dieser Funktion übergeben:

- Eine Liste mit Listen
- Eine Liste von arrays
- Ein Array von Listen
- Ein Array von Sequenzen
- Eine beliebige andere Kombination von aufzählbare Sequenzen

Der folgende code verwendet `Seq.concat` der Szenarien veranschaulicht, die Sie über flexible Typen unterstützen können.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

Die Ausgabe lautet wie folgt.

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

In F# erläutert sind wie in anderen objektorientierten Sprachen Kontexte vorhanden in denen abgeleiteten Typen oder Typen, die Schnittstellen implementieren automatisch in einen Basistyp oder Schnittstellentyp konvertiert werden. Diese automatische Konvertierungen erfolgen in direkten Argumente, aber nicht, wenn der Typ in einer untergeordneten Position, im Rahmen eines komplexen Typs wie z. B. einen Rückgabetyp eines Funktionstyps oder als Typargument ist. Daher ist die flexiblen Typ Notation primär nützlich, wenn der Typ, den sie zum Anwenden eines komplexen Typs gehört.

## <a name="see-also"></a>Siehe auch

[F#-Sprachreferenz](index.md)

[Generika](generics/index.md)
