---
title: 'Schleifen: while...do-Ausdruck (F#)'
description: "Finden Sie unter wie die while... führen Ausdruck wird verwendet, um den iterativen Ausführung (Schleife) ausführen, wenn eine angegebene testbedingung \"true\" ist."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0416ffca-7ed9-4aff-9493-e001fdba8c9b
ms.openlocfilehash: 5f10fda84a5e748856eb7b2c63ad46cc1fba44bb
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2017
---
# <a name="loops-whiledo-expression"></a>Schleifen: while...do-Ausdruck

Die `while...do` Ausdruck wird verwendet, um den iterativen Ausführung (Schleife) ausführen, wenn eine angegebene testbedingung "true" ist.


## <a name="syntax"></a>Syntax

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Hinweise
Die *Testausdruck* ausgewertet wird, ist er `true`, *Text-Ausdruck* ausgeführt wird und der Testausdruck erneut ausgewertet wird. Die *Text-Ausdruck* muss einen Typ aufweisen `unit`. Wenn der Testausdruck ist `false`, die Iteration beendet.

Das folgende Beispiel veranschaulicht die Verwendung der `while...do` Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

Die Ausgabe des vorherigen Codes ist einen Stream von Zufallszahlen zwischen 1 und 20, der letzten, von denen 10 verwendet.

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
Können Sie `while...do` in Sequenzausdrücken und andere Berechnungsausdrücke in diesem Fall, dass eine angepasste Version von den `while...do` Ausdruck verwendet wird. Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Schleifen: `for...in`-Ausdruck](loops-for-in-expression.md)

[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)
