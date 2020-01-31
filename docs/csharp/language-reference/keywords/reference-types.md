---
title: 참조 형식 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: b2d6cc94c11ca6305a75e9ee489af53ad957201e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744521"
---
# <a name="reference-types-c-reference"></a>참조 형식(C# 참조)

C# 형식은 참조 형식과 값 형식 두 가지가 있습니다. 참조 형식의 변수에는 데이터(개체)에 대한 참조가 저장되며, 값 형식의 변수에는 해당 데이터가 직접 포함됩니다. 참조 형식에서는 두 가지 변수가 같은 개체를 참조할 수 있으므로 한 변수에 대한 작업이 다른 변수에서 참조하는 개체에 영향을 미칠 수 있습니다. 값 형식에서는 각 변수에 데이터의 자체 사본이 들어 있으며 한 변수의 작업이 다른 변수에 영향을 미칠 수 없습니다(in, ref 및 out 매개 변수 제외, [in](in-parameter-modifier.md), [ref](ref.md) 및 [out](out-parameter-modifier.md) 매개 변수 한정자 참조).

 다음 키워드는 참조 형식을 선언하는 데 사용됩니다.

- [class](class.md)

- [interface](interface.md)

- [delegate](../builtin-types/reference-types.md)

 C#는 다음과 같은 기본 참조 형식도 제공합니다.

- [dynamic](../builtin-types/reference-types.md)

- [object](../builtin-types/reference-types.md)

- [string](../builtin-types/reference-types.md)

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 키워드](index.md)
- [포인터 형식](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [값 형식](../builtin-types/value-types.md)
