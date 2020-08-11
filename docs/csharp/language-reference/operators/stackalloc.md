---
title: stackalloc 식 - C# 참조
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 4f20f3262b77cc2fe16480e53d13960e68d230b5
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916679"
---
# <a name="stackalloc-expression-c-reference"></a>stackalloc 식(C# 참조)

`stackalloc` 식은 스택에 메모리 블록을 할당합니다. 메서드 실행 중에 생성된 스택 할당 메모리 블록은 해당 메서드가 반환될 때 자동으로 삭제됩니다. `stackalloc`을 사용하여 할당된 메모리를 명시적으로 해제할 수 없습니다. 스택 할당 메모리 블록에는 [가비지 수집](../../../standard/garbage-collection/index.md)이 적용되지 않으며, [`fixed` 문](../keywords/fixed-statement.md)을 사용해서 고정하지 않아도 됩니다.

`stackalloc` 식의 결과를 다음 형식 중 하나의 변수에 할당할 수 있습니다.

- C# 7.2부터 <xref:System.Span%601?displayProperty=nameWithType> 또는 <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>(다음 예제 참조):

  [!code-csharp[stackalloc span](snippets/shared/StackallocOperator.cs#AssignToSpan)]

  <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601> 변수에 스택 할당 메모리 블록을 할당할 때 [unsafe](../keywords/unsafe.md) 컨텍스트를 사용하지 않아도 됩니다.

  이러한 형식으로 작업하는 경우 다음 예제와 같이 [조건식](conditional-operator.md) 또는 대입식에 `stackalloc` 식을 사용할 수 있습니다.

  [!code-csharp[stackalloc expression](snippets/shared/StackallocOperator.cs#AsExpression)]

  C# 8.0부터 다음 예제와 같이 <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601> 변수가 허용되는 경우 다른 식 내부에서 `stackalloc` 식을 사용할 수 있습니다.

  [!code-csharp[stackalloc in nested expressions](snippets/shared/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > 스택 할당 메모리로 작업할 때는 가능한 한, <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601> 형식을 사용하는 것이 좋습니다.

- [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)(다음 예제 참조)

  [!code-csharp[stackalloc pointer](snippets/shared/StackallocOperator.cs#AssignToPointer)]

  포인터 형식으로 작업할 때는 위 예제와 같이 `unsafe` 컨텍스트를 사용해야 합니다.

  포인터 형식의 경우 지역 변수 선언에서만 `stackalloc` 식을 사용하여 변수를 초기화할 수 있습니다.

스택에서 사용 가능한 메모리 양이 제한됩니다. 스택에 너무 많은 메모리를 할당하는 경우 <xref:System.StackOverflowException>이 throw됩니다. 이를 방지하려면 다음 규칙을 따르세요.

- `stackalloc`을 사용하여 할당하는 메모리의 양을 제한합니다.

  [!code-csharp[limit stackalloc](snippets/shared/StackallocOperator.cs#LimitStackalloc)]

  스택에서 사용 가능한 메모리 양은 코드를 실행하는 환경에 따라 달라지므로 실제 제한 값을 정의할 때는 신중해야 합니다.

- 루프 내부에서 `stackalloc`을 사용하지 마세요. 루프 외부에서 메모리 블록을 할당하고 루프 내부에서 다시 사용합니다.

새로 할당된 메모리의 콘텐츠는 정의되지 않습니다. 사용하기 전에 초기화해야 합니다. 예를 들어 모든 항목을 `T`형식의 기본값으로 설정하는 <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> 메서드를 사용할 수 있습니다.

C# 7.3부터, 배열 이니셜라이저 구문을 사용하여 새로 할당된 메모리의 콘텐츠를 정의할 수 있습니다. 다음 예제에서는 이 작업을 수행하는 다양한 방법을 보여 줍니다.

[!code-csharp[stackalloc initialization](snippets/shared/StackallocOperator.cs#StackallocInit)]

식 `stackalloc T[E]`에서 `T`는 [관리되지 않는 형식](../builtin-types/unmanaged-types.md)이어야 하며 `E`는 음수가 아닌 [int](../builtin-types/integral-numeric-types.md) 값으로 계산되어야 합니다.

## <a name="security"></a>보안

`stackalloc`를 사용하면 CLR(공용 언어 런타임)에서 버퍼 오버런 검색 기능이 자동으로 사용됩니다. 버퍼 오버런이 검색되면 악성 코드가 실행될 가능성을 최소화하기 위해 최대한 빨리 프로세스가 종료됩니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [스택 할당](~/_csharplang/spec/unsafe-code.md#stack-allocation) 섹션과 중첩 컨텍스트[ 기능 제안 노트의 `stackalloc` 허용](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 연산자 및 식](index.md)
- [포인터 관련 연산자](pointer-related-operators.md)
- [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [메모리 및 범위 관련 형식](../../../standard/memory-and-spans/index.md)
- [stackalloc 관련 실행 사항 및 금지 사항](https://vcsjones.dev/2020/02/24/stackalloc/)
