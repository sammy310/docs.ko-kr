---
description: 매개 변수 배열의 params 키워드 - C# 참조
title: 매개 변수 배열의 params 키워드 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: a2726c725508cd297001aaabddeff414704d1115
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134473"
---
# <a name="params-c-reference"></a>params(C# 참조)

`params` 키워드를 사용하면 가변 개수의 인수를 사용하는 [메서드 매개 변수](method-parameters.md)를 지정할 수 있습니다. 매개 변수 배열은 1차원 배열이어야 합니다.

메서드 선언에서 `params` 키워드 뒤에는 추가 매개 변수가 허용되지 않으며, `params` 키워드 하나만 메서드 선언에 사용할 수 있습니다.

`params` 매개 변수의 선언된 형식이 1차원 배열이 아닌 경우 컴파일러 오류 [CS0225](../../misc/cs0225.md)가 발생합니다.

`params` 매개 변수를 사용하여 메서드를 호출하면 다음을 전달할 수 있습니다.

- 배열 요소 형식의 쉼표로 구분된 인수 목록입니다.
- 지정된 형식의 인수 배열입니다.
- 인수가 없습니다. 인수를 보내지 않는 경우 `params` 목록의 길이는 0입니다.

## <a name="example"></a>예제

다음 예제에서는 `params` 매개 변수에 인수를 보낼 수 있는 다양한 방법을 보여 줍니다.

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [메서드 매개 변수](method-parameters.md)
