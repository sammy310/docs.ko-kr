---
title: with 식 - C# 참조
description: C# 레코드의 비파괴적 변경을 수행하는 with 식에 대해 알아봅니다.
ms.date: 11/12/2020
f1_keywords:
- with_CSharpKeyword
helpviewer_keywords:
- with expression [C#]
- with operator [C#]
ms.openlocfilehash: 8412dfe8663703d3b201fe98b5f4752da1b344cf
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2020
ms.locfileid: "94556714"
---
# <a name="with-expression-c-reference"></a>with 식(C# 참조)

C# 9.0 이상에서 사용 가능한 `with` 식은 지정된 속성 및 필드를 수정하여 해당 [레코드](../../whats-new/csharp-9.md#record-types) 피연산자의 복사본을 생성합니다.

:::code language="csharp" source="snippets/with-expression/BasicExample.cs" :::

위 예제와 같이 [개체 이니셜라이저](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) 구문을 사용하여 수정할 멤버와 새 값을 지정합니다. `with` 식에서 왼쪽 피연산자는 레코드 형식이어야 합니다.

다음 예제와 같이 `with` 식의 결과는 식의 피연산자와 동일한 런타임 형식입니다.

:::code language="csharp" source="snippets/with-expression/InheritanceExample.cs" :::

참조 형식 멤버인 경우 레코드가 복사될 때 인스턴스에 대한 참조만 복사됩니다. 복사본과 원본 레코드 모두 동일한 참조 형식 인스턴스에 액세스할 수 있습니다. 다음 예제에서는 해당 동작을 보여줍니다.

:::code language="csharp" source="snippets/with-expression/ExampleWithReferenceType.cs" :::

모든 레코드 형식에 ‘복사 생성자’가 있습니다. 이 생성자는 레코드 형식의 단일 매개 변수를 사용합니다. 또한 인수의 상태를 새 레코드 인스턴스로 복사합니다. `with` 식을 평가할 때 복사 생성자가 호출되어 원본 레코드를 기반으로 새 레코드 인스턴스를 인스턴스화합니다. 그런 다음, 지정된 수정 사항에 따라 새 인스턴스가 업데이트됩니다. 기본적으로 복사 생성자는 암시적으로, 컴파일러에서 생성합니다. 레코드 복사 의미 체계를 사용자 지정해야 하는 경우 원하는 동작으로 복사 생성자를 명시적으로 선언합니다. 다음 예제에서는 명시적 복사 생성자를 사용하여 위의 예제를 업데이트합니다. 새 복사 동작은 레코드가 복사될 때 목록 참조 대신 목록 항목을 복사하는 것입니다.

:::code language="csharp" source="snippets/with-expression/UserDefinedCopyConstructor.cs" :::

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [레코드 기능 제안 노트](~/_csharplang/proposals/csharp-9.0/records.md)의 다음 섹션을 참조하세요.

- [`with` 식](~/_csharplang/proposals/csharp-9.0/records.md#with-expression)
- [멤버 복사 및 복제](~/_csharplang/proposals/csharp-9.0/records.md#copy-and-clone-members)

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 연산자 및 식](index.md)
