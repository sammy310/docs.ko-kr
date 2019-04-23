---
title: 코드의 특수 문자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
ms.openlocfilehash: 65fcd10521742e287c7934080b3352a06668df7a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835559"
---
# <a name="special-characters-in-code-visual-basic"></a>코드의 특수 문자(Visual Basic)
경우에 따라 영문자 또는 숫자 하지 않은 문자 즉, 코드에서 특수 문자를 사용 해야 합니다. 문장 부호 및 특수 문자는 Visual Basic 문자 집합의 프로그램 텍스트 컴파일러 또는 컴파일된 프로그램이 수행 하는 작업을 정의 하는 데 구성에서 사용이 다양 한 경우 이러한 특수 문자는 수행할 작업을 지정하지 않습니다.  
  
## <a name="parentheses"></a>괄호  
 와 같은 프로시저를 정의 하는 경우 괄호를 사용 하는 `Sub` 또는 `Function`합니다. 모든 프로시저 인수 목록을 괄호로 묶어야 합니다. 또한 괄호를 사용 하면 논리 그룹으로 변수 또는 인수를 배치 하는 데 특히 복잡 한 식의 연산자 우선 순위는 기본 순서 재정의를 합니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 값을 이전 코드의 실행 `d` 8.225의 값은 `e` 3입니다. 에 대 한 계산 `d` 의 기본 우선 순위를 사용 하 여 `/` 위에 `+` 와 같습니다 `d = b + (c / a)`합니다. 계산에 괄호 `e` 기본 우선 순위를 무시 합니다.  
  
## <a name="separators"></a>Separators  
 구분 기호 그 이름이 의미 하는 무엇을 수행 합니다: 여러 코드 섹션입니다. Visual Basic에서 구분 기호 문자는 콜론 (`:`). 별도 줄이 아니라 한 줄에 여러 개의 문을 포함 하려는 경우 구분 기호를 사용 합니다. 이 공간을 저장 하 고 코드의 가독성을 향상 시킵니다. 다음 예제에는 콜론으로 구분 된 세 가지 문을 보여 줍니다.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 자세한 내용은 [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)합니다.  
  
 콜론 (`:`) 문자는 또한 문 레이블은 식별 하는 데 사용 됩니다. 자세한 내용은 [방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)합니다.  
  
## <a name="concatenation"></a>연결 연산  
 사용 하 여는 `&` 에 대 한 연산자 *연결*, 또는 문자열을 함께 연결 합니다. 혼동 하지 마십시오는 `+` 숫자 값을 함께 추가 하는 연산자입니다. 사용 하는 경우는 `+` 연산자를 숫자 값에서 작동 하는 경우 잘못 된 결과 얻을 수 있습니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 값을 이전 코드의 실행 `resultA` 21.01의 값은 `resultB` "10.0111로 실행" 됩니다.  
  
## <a name="member-access-operators"></a>멤버 액세스 연산자  
 점 형식의 멤버에 액세스 하려면 사용 (`.`) 또는 느낌표 (`!`) 형식 이름과 멤버 이름 간에 연산자입니다.  
  
### <a name="dot--operator"></a>점 (입니다.) 연산자  
 사용 된 `.` 클래스, 구조체, 인터페이스 또는 열거형 멤버 액세스 연산자로 연산자입니다. 필드, 속성, 이벤트 또는 메서드 멤버 수 있습니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>느낌표 (!) 연산자  
 사용 된 `!` 사전 액세스 연산자를 클래스 또는 인터페이스 에서만 연산자. 클래스 또는 인터페이스에는 단일을 허용 하는 기본 속성이 있어야 `String` 인수입니다. 바로 다음에 오는 식별자는 `!` 연산자의 기본 속성을 문자열로 전달 된 인수 값이 됩니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 3 개의 출력 줄 `MsgBox` 값의 모든 디스플레이 `32856`합니다. 속성에 대 한 일반적인 액세스를 사용 하는 첫 번째 줄 `index`, 두 번째 사실을 활용 하는 `index` 클래스의 기본 속성은 `hasDefault`, 세 번째 클래스에 대 한 사전 액세스를 사용 하 여 합니다.  
  
 두 번째 피연산자는 `!` 연산자는 큰따옴표로 묶지 유효한 Visual Basic 식별자 여야 합니다 (`" "`). 즉, 문자열 리터럴 또는 문자열 변수를 사용할 수 없습니다. 다음 줄의 마지막으로 변경 합니다 `MsgBox` 호출 때문에 오류가 발생 `"X"` 은 괄호로 묶인된 문자열 리터럴.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  기본 컬렉션에 대 한 참조를 명시적 이어야 합니다. 특히, 사용할 수 없습니다는 `!` 바인딩된 변수로 연산자입니다.  
  
 합니다 `!` 문자로도 사용 됩니다는 `Single` 문자를 입력 합니다.  
  
## <a name="see-also"></a>참고자료

- [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
