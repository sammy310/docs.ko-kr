---
description: override 한정자 - C# 참조
title: override 한정자 - C# 참조
ms.date: 10/22/2020
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 618200183348e68a4600adb9592a635f61f6a875
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434875"
---
# <a name="override-c-reference"></a>override(C# 참조)

`override` 한정자는 상속된 메서드, 속성, 인덱서 또는 이벤트의 추상 또는 가상 구현을 확장하거나 수정하는 데 필요합니다.

다음 예제에서 `Square` 클래스는 `GetArea`가 추상 `Shape` 클래스에서 상속되기 때문에 `GetArea`의 재정의된 구현을 제공해야 합니다.

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

`override` 메서드는 기본 클래스에서 상속된 멤버의 새 구현을 제공합니다. `override` 선언에서 재정의된 메서드를 재정의된 기본 메서드라고 합니다. `override` 메서드에는 재정의된 기본 메서드와 동일한 시그니처가 있어야 합니다. C# 9.0부터 `override` 메서드는 공변 반환 형식을 지원합니다. 특히 `override` 메서드의 반환 형식은 해당하는 기본 메서드의 반환 형식에서 파생될 수 있습니다. C# 8.0 이전 버전에서는 `override` 메서드의 반환 형식과 재정의된 기본 메서드가 동일해야 합니다.

비가상 또는 정적 메서드는 재정의할 수 없습니다. 재정의된 기본 메서드는 `virtual`, `abstract` 또는 `override`여야 합니다.

`override` 선언에서는 `virtual` 메서드의 액세스 가능성을 변경할 수 없습니다. `override` 메서드 및 `virtual` 메서드 둘 다에 동일한 [액세스 수준 한정자](access-modifiers.md)가 있어야 합니다.

`new`, `static` 또는 `virtual` 한정자를 사용하여 `override` 메서드를 수정할 수 없습니다.

재정의 속성 선언은 상속된 속성과 동일한 액세스 한정자, 형식 및 이름을 지정해야 합니다. C# 9.0부터 읽기 전용 재정의 속성은 공변 반환 형식을 지원합니다. 재정의된 속성은 `virtual`, `abstract` 또는 `override`여야 합니다.

`override` 키워드 사용 방법에 대한 자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) 및 [Override 및 New 키워드를 사용해야 하는 경우](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)를 참조하세요. 상속에 대한 자세한 내용은 [상속](../../programming-guide/classes-and-structs/inheritance.md)을 참조하세요.

## <a name="example"></a>예제

이 예제에서는 `Employee`라는 기본 클래스와 `SalesEmployee`라는 파생 클래스를 정의합니다. `SalesEmployee` 클래스에는 추가 필드 `salesbonus`가 포함되어 있고, 이를 고려하기 위해 `CalculatePay` 메서드를 재정의합니다.

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [재정의 메서드](~/_csharplang/spec/classes.md#override-methods) 섹션을 참조하세요.

공변 반환 형식에 대한 자세한 내용은 [기능 제안 노트](~/_csharplang/proposals/csharp-9.0/covariant-returns.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [상속](../../programming-guide/classes-and-structs/inheritance.md)
- [C# 키워드](index.md)
- [한정자](index.md)
- [abstract](abstract.md)
- [virtual](virtual.md)
- [new(한정자)](new-modifier.md)
- [다형성](../../programming-guide/classes-and-structs/polymorphism.md)
