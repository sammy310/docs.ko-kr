---
title: '방법: 레이블 문 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 69ec8c7625410f140c59ba8dd492dca76857eb96
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828643"
---
# <a name="how-to-label-statements-visual-basic"></a>방법: 레이블 문 (Visual Basic)
문 블록은 콜론으로 구분 하는 코드 줄으로 이루어져 있습니다. 코드를 식별 하는 문자열 또는 정수 앞에 줄 수 있다고 *레이블이 지정 된*합니다. 문 레이블은 사용에 대 한 문을 사용 하 여 같은 식별 하는 코드 줄을 표시 하 되 `On Error Goto`합니다.  
  
 레이블은 유효한 Visual Basic 식별자 중 하나를 수 있습니다-프로그래밍 요소를 식별 하는 것과 같은-또는 정수 리터럴입니다. 레이블을 소스 코드 줄의 시작 부분에 표시 되 고 같은 줄에서 문에 의해 뒤 여부에 관계 없이 콜론으로와 야 합니다.  
  
 컴파일러는 줄의 시작 부분에 이미 정의 된 식별자 일치 하는지 여부를 확인 하 여 레이블을 식별 합니다. 표시 되지 않는 경우 컴파일러는 레이블 것으로 가정 합니다.  
  
 레이블을 자체 선언 공간 있고 다른 식별자를 방해 하지 않습니다. 레이블의 범위는 메서드의 본문입니다. 레이블 선언 모호한 경우에 우선합니다.  
  
> [!NOTE]
>  레이블은 메서드 내에서 실행 가능 문을 에서만 사용할 수 있습니다.  
  
### <a name="to-label-a-line-of-code"></a>코드 줄 레이블을 지정 하려면  
  
-   소스 코드 줄의 시작 부분에 콜론 뒤에 식별자를 배치 합니다.  
  
     예를 들어, 다음 코드 줄은 레이블이 지정 된 `Jump` 고 `120`, 각각.  
  
     [!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]  
  
## <a name="see-also"></a>참고자료

- [문(C++)](../../../visual-basic/programming-guide/language-features/statements.md)
- [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
