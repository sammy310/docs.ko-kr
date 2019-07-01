---
title: float 키워드 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
ms.openlocfilehash: db0139f2000c1bc2c5a13a3a542164201e73f0fb
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424216"
---
# <a name="float-c-reference"></a>float(C# 참조)

`float` 키워드는 32비트 부동 소수점 값을 저장하는 단순 형식을 나타냅니다. 다음 표에서는 `float` 형식의 전체 자릿수와 근사 범위를 보여 줍니다.

|형식|근사 범위|전체 자릿수|.NET 형식|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|±1.5 x 10<sup>−45</sup> ~ ±3.4 x 10<sup>38</sup>|~6-9개 자릿수|<xref:System.Single?displayProperty=nameWithType>|  

## <a name="literals"></a>리터럴

기본적으로 대입 연산자 오른쪽의 실수 리터럴은 [double](double.md)로 처리됩니다. 따라서 부동 변수를 초기화하려면 다음 예제와 같이 접미사 `f` 또는 `F`를 사용합니다.

```csharp
float x = 3.5F;
```

이전 선언에서 접미사를 사용하지 않은 경우 [double](double.md) 값을 `float` 변수에 저장하려고 하기 때문에 컴파일 오류가 발생합니다.

## <a name="conversions"></a>변환

식에서 숫자 정수 형식과 부동 소수점 형식을 함께 사용할 수 있습니다. 이 경우 정수 형식이 부동 소수점 형식으로 변환됩니다. 식의 계산은 다음 규칙에 따라 수행됩니다.

- 부동 소수점 형식 중 하나가 [double](double.md)이면 식은 같음에 대한 관계형 비교 또는 비교에서 [double](double.md) 또는 [bool](bool.md)로 계산됩니다.

- 식에 [double](double.md) 형식이 없는 경우 식은 같음에 대한 관계형 비교 또는 비교에서 `float` 또는 [bool](bool.md)로 계산됩니다.

부동 소수점 식에는 다음과 같은 값 집합이 포함될 수 있습니다.

- 양수 및 음수 0

- 양수 및 음수 무한대

- NaN(Not-a-Number) 값

- 한정된 0이 아닌 값의 집합

이러한 값에 대한 자세한 내용은 [IEEE](https://www.ieee.org) 웹 사이트에서 제공되는 이진 부동 소수점 연산에 대한 IEEE 표준을 참조하세요.

## <a name="example"></a>예

다음 예제에서는 [int](../builtin-types/integral-numeric-types.md), [short](../builtin-types/integral-numeric-types.md) 및 `float`가 수학 식에 포함되어 `float` 결과를 제공합니다. (`float`는 <xref:System.Single?displayProperty=nameWithType> 형식의 별칭입니다.) 식에 [double](double.md)이 없습니다.

[!code-csharp[csrefKeywordsTypes#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#13)]

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참고 항목

- <xref:System.Single>
- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [캐스팅 및 형식 변환](../../programming-guide/types/casting-and-type-conversions.md)
- [C# 키워드](index.md)
- [정수 형식](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [기본 제공 형식 표](built-in-types-table.md)
- [암시적 숫자 변환 표](implicit-numeric-conversions-table.md)
- [명시적 숫자 변환 표](explicit-numeric-conversions-table.md)
