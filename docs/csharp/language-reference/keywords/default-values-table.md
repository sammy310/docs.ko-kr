---
title: 기본값 표 - C# 참조
ms.custom: seodec18
description: C# 값 형식의 기본 값은 무엇인지 알아봅니다.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: 4fc9a35f69540e047a97c21788015ca8e54068a0
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422026"
---
# <a name="default-values-table-c-reference"></a>기본값 표(C# 참조)

다음 표는 [값 형식](value-types.md)의 기본값을 보여줍니다.

|값 형식|기본값|
|----------------|-------------------|
|[bool](bool.md)|`false`|
|[byte](byte.md)|0|
|[char](char.md)|'\0'|
|[decimal](decimal.md)|0M|
|[double](double.md)|0.0D|
|[enum](enum.md)|식 `(E)0`로 생성한 값이며 여기서 `E`는 열거형 식별자입니다.|
|[float](float.md)|0.0F|
|[int](int.md)|0|
|[long](long.md)|0L|
|[sbyte](sbyte.md)|0|
|[short](short.md)|0|
|[struct](struct.md)|모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.|
|[uint](uint.md)|0|
|[ulong](ulong.md)|0|
|[ushort](ushort.md)|0|

## <a name="remarks"></a>주의

C#에서 초기화되지 않은 변수를 사용할 수 없습니다. 해당 형식의 기본값을 사용하여 변수를 초기화할 수 있습니다. 또한 형식의 기본 값을 사용하여 메서드의 [선택적 인수](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments)의 기본값을 지정할 수도 있습니다.

[기본값 식](../../programming-guide/statements-expressions-operators/default-value-expressions.md)을 사용하여 다음 예제와 같이 형식의 기본값을 생성합니다.

```csharp
int a = default(int);
```

C# 7.1부터 [`default` 리터럴](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference)을 사용하여 해당 형식의 기본값으로 변수를 초기화할 수 있습니다.

```csharp
int a = default;
```

매개 변수 없는 생성자 또는 암시적 매개 변수 없는 생성자를 사용하여 다음 예제와 같이 값 형식의 기본값을 생성할 수도 있습니다. 생성자에 대한 자세한 내용은 [생성자](../../programming-guide/classes-and-structs/constructors.md) 문서를 참조하세요.

```csharp
int a = new int();
```

모든 [참조 형식](reference-types.md)의 기본값은 `null`입니다. [nullable 형식](../../programming-guide/nullable-types/index.md)의 기본값은 <xref:System.Nullable%601.HasValue%2A> 속성은 `false`이고 <xref:System.Nullable%601.Value%2A> 속성은 정의되지 않은 인스턴스입니다.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [값 형식](value-types.md)
- [값 형식 표](value-types-table.md)
- [기본 제공 형식 표](built-in-types-table.md)
