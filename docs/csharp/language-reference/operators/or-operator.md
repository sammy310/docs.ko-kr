---
title: '| 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 38f8e21dbd07868441e0c4fbb6074f9897905222
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312880"
---
# <a name="-operator-c-reference"></a>| 연산자(C# 참조)

이항 `|` 연산자는 정수 형식 및 `bool`에 대해 미리 정의되어 있습니다. 정수 형식의 경우 `|` 연산자는 해당 피연산자의 비트 OR 연산자를 계산합니다. `bool` 피연산자의 경우 `|` 연산자는 해당 피연산자의 논리적 OR 연산을 계산합니다. 즉, 피연산자가 둘 다 `false`일 경우에만 결과가 `false`입니다.

## <a name="remarks"></a>주의

이진 `|` 연산자는 [기존 OR 연산자](boolean-logical-operators.md#conditional-logical-or-operator-) `||`와 달리 첫 번째 연산자의 값에 상관없이 두 피연산자를 모두 계산합니다.

사용자 정의 형식은 `|` 연산자를 오버로드할 수 있습니다([operator](../keywords/operator.md) 참조).

## <a name="example"></a>예제

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 연산자](index.md)