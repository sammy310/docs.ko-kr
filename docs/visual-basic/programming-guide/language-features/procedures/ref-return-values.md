---
title: 참조 반환 값
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: f2a92c584dbb12a322e28435d797fa4d7c2f6dbb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186932"
---
# <a name="support-for-reference-return-values-visual-basic"></a>참조 반환 값 지원(Visual Basic)

C# 7.0부터 C# 언어는 *참조 반환 값을*지원합니다. 참조 반환 값을 이해하는 한 가지 방법은 메서드에 대한 참조로 전달되는 인수의 반대입니다. 참조로 전달된 인수가 수정되면 변경 내용이 호출자의 변수 값에 반영됩니다. 메서드가 호출자에게 참조 반환 값을 제공하는 경우 호출자의 참조 반환 값에 대한 수정 사항은 호출된 메서드의 데이터에 반영됩니다.

Visual Basic은 참조 반환 값을 사용하여 메서드를 작성할 수 없지만 참조 반환 값을 사용할 수 있습니다. 즉, 참조 반환 값을 가진 메서드를 호출 하 고 해당 반환 값을 수정할 수 있습니다 및 참조 반환 값에 대 한 변경 내용은 호출 된 메서드의 데이터에 반영 됩니다.

## <a name="modifying-the-ref-return-value-directly"></a>참조 반환 값을 직접 수정

항상 성공하고 매개 변수가 없는 `ByRef` 메서드의 경우 참조 반환 값을 직접 수정할 수 있습니다. 참조 반환 값을 반환 하는 식에 새 값을 할당 하 여이 작업을 수행 합니다.

다음 C# 예제에서는 `NumericValue.IncrementValue` 내부 값을 증분하고 참조 반환 값으로 반환하는 메서드를 정의합니다.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

그런 다음 다음 Visual Basic 예제에서 호출자에 의해 참조 반환 값이 수정됩니다. 메서드 호출이 `NumericValue.IncrementValue` 있는 줄은 메서드에 값을 할당하지 않습니다. 대신 메서드에서 반환 하는 참조 반환 값에 값을 할당 합니다.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>도우미 방법 사용

다른 경우에는 메서드 호출의 참조 반환 값을 직접 수정하는 것이 항상 바람직하지 않을 수 있습니다. 예를 들어 문자열을 반환하는 검색 메서드가 항상 일치하는 문자열을 찾지 못할 수 있습니다. 이 경우 검색이 성공한 경우에만 참조 반환 값을 수정하려고 합니다.

다음 C# 예제에서는 이 시나리오를 보여 줍니다. C#으로 `Sentence` 작성된 클래스에는 지정된 `FindNext` 하위 문자열로 시작하는 문장에서 다음 단어를 찾는 메서드가 포함되어 있습니다. 문자열은 참조 반환 값으로 반환되며, 메서드에 참조로 전달된 `Boolean` 변수는 검색에 성공했는지 여부를 나타냅니다. 참조 반환 값은 반환된 값을 읽는 것 외에도 호출자는 이를 수정할 수 있으며 수정 사항이 `Sentence` 클래스에 내부적으로 포함된 데이터에 반영됨을 나타냅니다.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

이 경우 참조 반환 값을 직접 수정하는 것은 메서드 호출이 일치를 찾지 못하고 문장의 첫 번째 단어를 반환하지 않을 수 있기 때문에 신뢰할 수 없습니다. 이 경우 호출자는 실수로 문장의 첫 번째 단어를 수정합니다. 이 문제는 호출자가 `null` (또는 `Nothing` Visual Basic)에서 반환하여 방지할 수 있습니다. 그러나 이 경우 값이 있는 `Nothing` 문자열을 수정하려고 <xref:System.NullReferenceException>하면 . 호출자 반환에 <xref:System.String.Empty?displayProperty=nameWithType>의해 방지될 수도 있지만 이를 위해 호출자는 값이 <xref:System.String.Empty?displayProperty=nameWithType>있는 문자열 변수를 정의해야 합니다. 호출자는 해당 문자열을 수정할 수 있지만 수정된 문자열은 클래스에 저장된 문장의 단어와 `Sentence` 아무런 관계가 없으므로 수정 자체는 아무런 용도로 사용되지 않습니다.

이 시나리오를 처리하는 가장 좋은 방법은 도우미 메서드를 참조하여 참조 반환 값을 전달하는 것입니다. 그런 다음 도우미 메서드에는 메서드 호출이 성공했는지 여부를 확인하는 논리가 포함되어 있으며, 성공한 경우 참조 반환 값을 수정합니다. 다음 예제에서는 가능한 구현을 제공합니다.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>참고 항목

- [값 및 참조로 인수 전달](passing-arguments-by-value-and-by-reference.md)
- [Visual Basic의 프로시저](index.md)
