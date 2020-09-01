---
description: continue 문 - C# 참조
title: continue 문 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 76578b0ad7e2b969609fbf50df1f9ab7de6e5097
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128441"
---
# <a name="continue-c-reference"></a>continue(C# 참조)

`continue` 문은 자신이 나타나는 바깥쪽 [while](./while.md), [do](./do.md), [for](./for.md) 또는 [foreach](./foreach-in.md) 문의 다음 반복으로 제어를 전달합니다.

## <a name="example"></a>예제

이 예제에서 카운터는 1에서 10까지 계산하도록 초기화됩니다. `continue` 문을 `(i < 9)` 식과 함께 사용하면 `continue`와 `for` 본문의 끝 사이에 있는 문을 건너뜁니다.

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](./index.md)
- [break 문](/cpp/cpp/break-statement-cpp)
