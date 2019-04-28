---
title: '방법: (Visual Basic) 코드 섹션 축소 및 숨기기'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: bf2a7188456097ac227039e4d902a14eb182664c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758277"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>방법: (Visual Basic) 코드 섹션 축소 및 숨기기
`#Region` 지시문을 사용 하면 Visual Basic 파일에서 코드 섹션 축소 및 숨기기 수 있습니다. `#Region` 지시문을 사용 하면 Visual Studio 코드 편집기를 사용 하는 경우 축소 또는 확장할 수 있는 코드 블록을 지정할 수 있습니다. 코드를 선택적으로 숨길 수 있습니다 파일을 보다 관리 가능 하 고 쉽게 읽을 수 있습니다. 자세한 내용은 [개요](/visualstudio/ide/outlining)를 참조하세요.  
  
 `#Region` 지시문이 같은 코드 블록 의미 체계를 지원 `#If...#End If`합니다. 즉, 하나의 블록 시작 없습니다 하며 다른; 종료 시작 및 끝 동일한 블록에 있어야 합니다. `#Region` 지시문 함수 내에서 지원 되지 않습니다.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>축소 하 고 코드 부분을 숨기려면  
  
- 부분 사이 코드를 배치 합니다 `#Region` 및 `#End Region` 문을 다음 예제와 같이:  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     `#Region` 사용자 고유의 블록을 절차와를 차례로 축소할 수 있는 클래스를 정의할 수 있습니다 따라서; 블록이 코드 파일에서 여러 번 사용 될 수 있습니다. `#Region` 블록 내의 다른 중첩 될 수도 있습니다 `#Region` 블록입니다.  
  
    > [!NOTE]
    >  코드에서 컴파일되는 하지 않는 숨기고 영향을 주지 않습니다 `#If...#End If` 문입니다.  
  
## <a name="see-also"></a>참고자료

- [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [#Region 지시문](../../../visual-basic/language-reference/directives/region-directive.md)
- [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [개요](/visualstudio/ide/outlining)
