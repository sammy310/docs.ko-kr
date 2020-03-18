---
title: break 문 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: ef276fd9e8da0ea25695c5afdf06a300bbd2a123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713759"
---
# <a name="break-c-reference"></a>break(C# 참조)

`break` 문은 배치된 지점에서 가장 가까운 바깥쪽 루프 또는 [switch](./switch.md) 문을 종료합니다. 제어는 종료된 문 뒤의 문으로 전달됩니다(있는 경우).

## <a name="example"></a>예제

이 예제의 조건문에는 1부터 100까지 개수를 계산하는 카운터가 포함되지만 `break` 문은 4회 계산 후에 루프를 종료합니다.

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a>예제

이 예제에서는 `break`switch[ 문에서 ](./switch.md)의 사용을 보여 줍니다.

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

`4`를 입력하면 다음과 같이 출력됩니다.

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a>예제

이 예제에서 `break` 문은 내부 중첩 루프를 중단하고 제어를 외부 루프에 반환하는 데 사용됩니다. 컨트롤은 중첩된 루프에서 _오직_ 반환된 한 레벨 업입니다.

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a>예제

이 예제에서 `break` 문은 루프의 각 반복 중에 현재 분기를 중단하는 데만 사용됩니다. 루프 자체는 중첩된 `break`switch[ 문에 속하는 ](./switch.md)의 인스턴스에 영향을 받지 않습니다.

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](./index.md)
- [switch](./switch.md)
