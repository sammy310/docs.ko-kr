---
title: 비관리형 형식 - C# 참조
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512071"
---
# <a name="unmanaged-types-c-reference"></a>비관리형 형식(C# 참조)

**비관리형 형식**은 참조 형식이거나 생성된 형식(하나 이상의 형식 인수를 포함하는 형식)이 아닌 형식이며, 모든 중첩 수준에서 참조 형식이나 생성된 형식 필드를 포함하지 않습니다. 즉 비관리형 형식은 다음 중 하나입니다.

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` 또는 `bool`
- 임의의 [열거형](../keywords/enum.md) 형식
- 임의의 [포인터](../../programming-guide/unsafe-code-pointers/pointer-types.md) 형식
- 생성된 형식이 아니고 비관리형 형식의 필드만 포함하는 임의의 사용자 정의 [구조체](../keywords/struct.md) 형식

C# 7.3부터 [`unmanaged` 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)을 사용하여 형식 매개 변수가 비포인터 비관리형 형식임을 지정할 수 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [포인터 형식](~/_csharplang/spec/unsafe-code.md#pointer-types) 섹션을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [메모리 및 범위 관련 형식](../../../standard/memory-and-spans/index.md)
- [sizeof 연산자](../operators/sizeof.md)
- [stackalloc 연산자](../operators/stackalloc.md)
