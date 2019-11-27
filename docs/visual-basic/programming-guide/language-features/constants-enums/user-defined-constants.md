---
title: 사용자 정의 상수
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 194a420b3749ca5c858a65c07b8c164287c1582a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354014"
---
# <a name="user-defined-constants-visual-basic"></a>사용자 정의 상수(Visual Basic)
상수는 변경 되지 않는 숫자 또는 문자열을 대신 사용 하는 의미 있는 이름입니다. 상수는 애플리케이션 실행 중 변함없이 유지되는 값을 저장합니다. 작업 하는 컨트롤이 나 구성 요소에 의해 정의 된 상수를 사용 하거나 직접 만들 수 있습니다. 직접 만든 상수는 *사용자 정의*로 설명 됩니다.  
  
 변수 이름을 만들기 위해 사용 하는 것과 동일한 지침을 사용 하 여 `Const` 문으로 상수를 선언 합니다. `Option Strict` `On`경우 상수 형식을 명시적으로 선언 해야 합니다.  
  
## <a name="const-statement-usage"></a>Const 문 사용  
 `Const` 문은 수치 또는 날짜/시간 수량을 나타낼 수 있습니다.  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 또한 `String` 상수를 정의할 수 있습니다.  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 등호 (`=`) 오른쪽에 있는 식은 종종 숫자 또는 리터럴 문자열이 긴 하지만 숫자나 문자열이 발생 하는 식일 수도 있습니다 (식에서 함수에 대 한 호출을 포함할 수는 없음). 이전에 정의 된 상수를 기준으로 상수를 정의할 수도 있습니다.  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a>사용자 정의 상수의 범위  
 `Const` 문의 범위는 동일한 위치에 선언 된 변수의 범위와 같습니다. 다음 방법 중 하나를 지정 하 여 범위를 지정할 수 있습니다.  
  
- 프로시저 내에만 존재 하는 상수를 만들려면 해당 프로시저 내에서 선언 합니다.  
  
- 클래스 내의 모든 프로시저에서 사용할 수 있지만 해당 모듈 외부의 코드에는 사용할 수 없는 상수를 만들려면 클래스의 선언 섹션에서 선언 합니다.  
  
- 어셈블리의 모든 멤버에 사용할 수 있지만 어셈블리의 외부 클라이언트에는 사용할 수 없는 상수를 만들려면 클래스의 선언 섹션에서 `Friend` 키워드를 사용 하 여 선언 합니다.  
  
- 응용 프로그램 전체에서 사용할 수 있는 상수를 만들려면 클래스의 선언 섹션에서 `Public` 키워드를 사용 하 여 해당 상수를 선언 합니다.  
  
 자세한 내용은 [방법: 상수 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)을 참조 하세요.  
  
### <a name="avoiding-circular-references"></a>순환 참조 방지  
 상수 *는 다른*상수를 기준으로 정의 될 수 있으므로 실수로 두 개 이상의 상수 사이에 순환 또는 순환 참조를 만들 수 있습니다. 다음 예제와 같이 둘 이상의 public 상수를 사용 하는 경우 각 상수는 서로를 기준으로 정의 됩니다.  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 순환이 발생 하면 Visual Basic는 컴파일러 오류를 생성 합니다.  
  
## <a name="see-also"></a>참고자료

- [Const 문](../../../../visual-basic/language-reference/statements/const-statement.md)
- [상수 및 리터럴 데이터 형식](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [상수 및 열거형](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
