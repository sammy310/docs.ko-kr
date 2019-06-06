---
title: typeof - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 7962a3d0a5885e64701cb9d9a4d689cd982b9830
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422545"
---
# <a name="typeof-c-reference"></a>typeof(C# 참조)

형식의 <xref:System.Type?displayProperty=nameWithType> 개체를 가져오는 데 사용됩니다. `typeof` 식의 형식은 다음과 같습니다.

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a>설명

식의 런타임 형식을 가져오려면 다음 예제와 같이 .NET Framework 메서드 <xref:System.Object.GetType%2A>을 사용할 수 있습니다.

```csharp
int i = 0;
System.Type type = i.GetType();
```

`typeof` 연산자를 오버로드할 수 없습니다.

열린 제네릭 형식에서 `typeof` 연산자를 사용할 수도 있습니다. 둘 이상의 형식 매개 변수가 있는 형식의 사양에 적절한 개수의 쉼표가 있어야 합니다. 예를 들어 <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType>에는 두 개의 형식 인수가 있으므로 다음과 같이 하나의 쉼표를 사용합니다.

```csharp
Type t = typeof(System.Collection.Generic.Dictionary<,>);
```

다음 예제에서는 메서드의 반환 형식이 제네릭 <xref:System.Collections.Generic.IEnumerable%601>인지 여부를 확인하는 방법을 보여 줍니다. 반환 형식이 <xref:System.Collections.Generic.IEnumerable%601> 제네릭 형식이 아닌 경우 <xref:System.Type.GetInterface%2A?displayProperty=nameWithType>은 `null`을 반환합니다.

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a>예제

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a>예제

이 샘플에서는 <xref:System.Object.GetType%2A> 메서드를 사용하여 숫자 계산의 결과를 포함하는 데 사용되는 형식을 결정합니다. 이 형식은 결과 숫자의 스토리지 요구 사항에 따라 달라집니다.

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [typeof 연산자](~/_csharplang/spec/expressions.md#the-typeof-operator)를 참조하세요. C# 언어 사양은 C# 구문 및 사용법에 대한 신뢰할 수 있는 소스입니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Type?displayProperty=nameWithType>
- [C# 참조](../../../csharp/language-reference/index.md)
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)
- [C# 키워드](../../../csharp/language-reference/keywords/index.md)
- [is](../../../csharp/language-reference/keywords/is.md)
