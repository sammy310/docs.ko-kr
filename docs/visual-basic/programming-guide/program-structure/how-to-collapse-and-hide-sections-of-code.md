---
title: '방법: 코드 섹션 축소 및 숨기기'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: e7aacdc3f41199127b00d276b382ec4a5f258da0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347404"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>방법: 코드 섹션 축소 및 숨기기(Visual Basic)

`#Region` 지시어를 사용 하면 Visual Basic 파일에서 코드 섹션을 축소 하 고 숨길 수 있습니다. `#Region` 지시문을 사용 하면 Visual Studio 코드 편집기를 사용할 때 확장 하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다. 코드를 선택적으로 숨기는 기능을 통해 파일을 보다 쉽게 관리 하 고 읽을 수 있습니다. 자세한 내용은 [개요](/visualstudio/ide/outlining)를 참조하세요.

`#Region` 지시문은 `#If...#End If`와 같은 코드 블록 의미 체계를 지원 합니다. 즉, 한 블록에서 시작 하 여 다른 블록에서 끝날 수 없습니다. start 및 end는 동일한 블록에 있어야 합니다. `#Region` 지시문은 함수 내에서 지원 되지 않습니다.

## <a name="to-collapse-and-hide-a-section-of-code"></a>코드 섹션을 축소 하 고 숨기려면

다음 예제와 같이 `#Region` 문과 `#End Region` 문 사이에 코드 섹션을 추가 합니다.

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

`#Region` 블록은 코드 파일에서 여러 번 사용할 수 있습니다. 따라서 사용자는 사용자가 직접 축소할 수 있는 자체 프로시저 및 클래스 블록을 정의할 수 있습니다. `#Region` 블록은 다른 `#Region` 블록 내에 중첩 될 수도 있습니다.

> [!NOTE]
> 코드를 숨기면 문이 컴파일되지 않으며 `#If...#End If` 문에 영향을 주지 않습니다.

## <a name="see-also"></a>참고 항목

- [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [#Region 지시문](../../../visual-basic/language-reference/directives/region-directive.md)
- [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [개요](/visualstudio/ide/outlining)
