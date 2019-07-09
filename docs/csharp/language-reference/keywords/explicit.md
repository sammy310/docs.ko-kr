---
title: explicit 키워드 - C# 참조
ms.custom: seodec18
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: a260c6f1ccac6e09770f1cb8f43d5d872b4b2650
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610096"
---
# <a name="explicit-c-reference"></a>explicit(C# 참조)

`explicit` 키워드는 캐스트를 통해 호출해야 하는 사용자 정의 형식 변환 연산자를 선언합니다.

다음 예제에서는 `Fahrenheit` 클래스에서 `Celsius` 클래스로 변환하는 연산자를 정의합니다. 연산자는 `Fahrenheit` 클래스 또는 `Celsius` 클래스 내에서 정의되어야 합니다.

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

다음 예제와 같이 캐스트를 사용하여 정의된 변환 연산자를 호출합니다.

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

변환 연산자는 소스 형식을 대상 형식으로 변환합니다. 소스 형식은 변환 연산자를 제공합니다. 암시적 변환과 달리 명시적 변환 연산자는 캐스트를 통해 호출해야 합니다. 변환 연산으로 인해 예외가 발생하거나 정보가 손실될 경우 `explicit`로 표시해야 합니다. 이렇게 하면 컴파일러가 결과를 예측할 수 없는 변환 연산을 자동으로 호출하는 것을 방지할 수 있습니다.

캐스트를 생략하면 컴파일 시간 오류 CS0266이 발생합니다.

자세한 내용은 [변환 연산자 사용](../../programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.

## <a name="example"></a>예

다음 예제에서는 `Fahrenheit` 및 `Celsius` 클래스를 제공하며, 각 클래스는 다른 클래스에 명시적 변환 연산자를 제공합니다.

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a>예

다음 예제에서는 한 자리 숫자를 나타내는 `Digit` 구조체를 정의합니다. `byte`에서 `Digit`로 변환하는 연산자를 정의하지만 일부 바이트는 `Digit`로 변환할 수 없기 때문에 명시적 변환이 됩니다.

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [implicit](implicit.md)
- [연산자 오버로드](../operators/operator-overloading.md)
- [방법: 구조체 간의 사용자 정의 변환 구현](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
- [Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)(C#의 연결된 사용자 정의 명시적 변환)
