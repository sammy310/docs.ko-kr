---
title: '방법: (Visual Basic) 코드에서 문 분리 및 결합'
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: 680084c39b90d4f664f48559fa21388ce192d999
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955625"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>방법: (Visual Basic) 코드에서 문 분리 및 결합
코드를 작성할 때 코드 편집기에서 가로 스크롤을 볼 수 있는 긴 문을 시간에 만들 수 있습니다. 방식에 영향을 주지 않지만 코드 실행, 하기 어렵습니다에 누구나 모니터에 표시 된 대로 코드를 읽는 합니다. 이러한 경우 긴 문은 여러 줄으로 분리를 고려해 야 합니다.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>단일 문에 여러 줄으로 중단  
  
- 밑줄 줄 연속 문자를 사용 하 여 (`_`), 줄을 지점입니다. 밑줄 바로 앞에는 공백이 오고 바로 뒤에는 줄 종결자(캐리지 리턴)가 와야 합니다.  
  
    > [!NOTE]
    >  경우에 따라 줄 연속 문자를 생략 하면 Visual Basic 컴파일러는 암시적으로 문을 계속 코드의 다음 줄에 있습니다. "암시적 줄 연속 문자" 참조 목록은 구문 요소는 줄 연속 문자를 생략할 수 있습니다 [문을](../../../visual-basic/programming-guide/language-features/statements.md)합니다.  
  
     다음 예제에서는 문의 마지막 줄을 제외한 모든 종료 줄 연속 문자를 사용 하 여 네 줄으로 분리 합니다.  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     이 시퀀스를 사용 하면 온라인 및 때 인쇄 코드를 쉽게 읽을 수 있습니다.  
  
     줄 연속 문자에는 줄에서 마지막 문자 여야 합니다. 같은 줄에 다른 요소와 따를 수 없습니다.  
  
     줄 연속 문자를 사용할 수 있는 수에 대 한 몇 가지 제한 사항이 존재 예를 들어 인수 이름 중 사용할 수 없습니다. 줄 연속 문자를 사용 하 여 인수 목록이 분리할 수 있지만 각 인수 이름은 그대로 유지 해야 합니다.  
  
     주석 줄 연속 문자를 사용 하 여 계속할 수 없습니다. 컴파일러 특별 한 의미에 대 한 설명의 문자를 검사 하지 않습니다. 여러 줄 주석의 경우 반복 주석 기호 (`'`) 각 줄에 있습니다.  
  
 하지만 각 문을 별도 줄에 배치 하는 것이 좋지만, Visual Basic 할 수도 있습니다 같은 줄에 여러 문 배치 합니다.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>같은 줄에 여러 문 배치  
  
- 문이 콜론으로 구분 (`:`) 다음 예제와 같이 합니다.  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>참고자료

- [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [문(C++)](../../../visual-basic/programming-guide/language-features/statements.md)
