---
description: var - C# 참조
title: var - C# 참조
ms.date: 10/02/2020
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: d04bea9bcf5be726d3e81a1a53abed31f59330a0
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608714"
---
# <a name="var-c-reference"></a>var (C# 참조)

C# 3부터 메서드 범위에서 선언된 변수에 암시적 “형식” `var`을 사용할 수 있습니다. 암시적 형식 지역 변수는 형식을 직접 선언한 것처럼 강력한 형식이지만 컴파일러가 형식을 결정합니다. `i`의 다음 두 선언은 기능이 동일합니다.

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

> [!IMPORTANT]
> [null 허용 참조 형식](../builtin-types/nullable-reference-types.md)을 사용하도록 설정하고 `var`를 사용하면 식 형식이 null 허용이 아니더라도 항상 null 허용 참조 형식을 의미합니다.

`var` 키워드는 일반적으로 생성자 호출 식과 함께 사용됩니다. `var`를 사용하면 다음 예제와 같이 변수 선언 및 개체 인스턴스화에서 형식 이름을 반복하지 않을 수 있습니다.

```csharp
var xs = new List<int>();
```

C# 9.0부터 대상으로 형식화된 [`new` 식](../operators/new-operator.md)을 대신 사용할 수 있습니다.

```csharp
List<int> xs = new();
List<int>? ys = new();
```

## <a name="example"></a>예제

다음 예제에서는 두 가지 쿼리 식을 보여 줍니다. 첫 번째 식에서는 `var`을 사용할 수 있지만, 쿼리 결과의 형식을 `IEnumerable<string>`으로 명시적으로 정의할 수 있기 때문에 필요하지 않습니다. 그러나 두 번째 식에서 `var`은 결과가 익명 형식의 컬렉션이 되도록 허용하고 해당 형식의 이름은 컴파일러 자체에만 액세스할 수 있습니다. `var`을 사용하면 결과에 대한 새 클래스를 만들 필요가 없습니다. 예제 #2에서는 `foreach` 반복 변수 `item`도 암시적 형식이어야 합니다.

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [암시적 형식 지역 변수](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
- [LINQ 쿼리 작업의 형식 관계](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
