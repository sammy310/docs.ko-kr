---
title: '방법: 열거형 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 042aea045313bcaf3832274acf1000f87a084b72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354051"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>방법: 열거형 선언(Visual Basic)
클래스 또는 모듈의 선언 섹션에 `Enum` 문을 사용 하 여 열거형을 만듭니다. 메서드 내에서 열거형을 선언할 수 없습니다. 적절 한 액세스 수준을 지정 하려면 `Private`, `Protected`, `Friend`또는 `Public`를 사용 합니다.  
  
 `Enum` 형식에는 각각 상수를 나타내는 이름, 내부 형식 및 필드 집합이 있습니다. 이름은 올바른 Visual Basic .NET 한정자 여야 합니다. 기본 형식은 정수 형식 (`Byte`, `Short`, `Long` 또는 `Integer`중 하나 여야 합니다. 기본값은 `Integer`입니다. 열거형은 항상 강력한 형식이 며 정수 숫자 형식으로는 사용할 수 없습니다.  
  
 열거형에는 부동 소수점 값을 사용할 수 없습니다. `Option Strict On`를 사용 하 여 열거형에 부동 소수점 값이 할당 된 경우 컴파일러 오류가 발생 합니다. `Option Strict` `Off`되 면 값이 자동으로 `Enum` 형식으로 변환 됩니다.  
  
 이름 및 이름 정규화를 사용 하지 않는 `Imports` 문을 사용 하는 방법에 대 한 자세한 내용은 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)을 참조 하세요.  
  
### <a name="to-declare-an-enumeration"></a>열거형을 선언 하려면  
  
1. 다음 예제와 같이 코드 액세스 수준, `Enum` 키워드 및 올바른 이름을 포함 하는 선언을 작성 합니다. 각는 서로 다른 `Enum`를 선언 합니다.  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. 열거형에서 상수를 정의 합니다. 기본적으로 열거형의 첫 번째 상수는 `0`로 초기화 되 고 후속 상수는 이전 상수 보다 1의 값으로 초기화 됩니다. 예를 들어, `Days`열거형에는 값 `0`와 함께 `Sunday` 라는 상수, 값 `1`를 사용 하는 `Monday` 상수, `Tuesday` 값을 사용 하는 `2`이라는 상수가 포함 되어 있습니다.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. 대입문을 사용 하 여 열거형의 상수에 값을 명시적으로 할당할 수 있습니다. 음수를 포함 하 여 임의의 정수 값을 할당할 수 있습니다. 예를 들어 값이 0 보다 작은 상수를 사용 하 여 오류 조건을 나타낼 수 있습니다. 다음 열거형에서 상수 `Invalid`에는 `–1`값이 명시적으로 할당 되 고 상수 `Sunday`에는 `0`값이 할당 됩니다. 열거형의 첫 번째 상수 이므로 `Saturday` `0`값으로도 초기화 됩니다. `Monday` 값이 `1` (`Sunday`값 보다 하나 이상) 인 경우 `Tuesday` 값은 `2`입니다.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>열거형을 명시적 형식으로 선언 하려면  
  
- 다음 예제와 같이 `As` 절을 사용 하 여 열거형의 유형을 지정 합니다.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>참고 항목

- [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [방법: 열거형 멤버 참조](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [방법: Visual Basic에서 열거형 반복](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [방법: 열거형 값과 연결된 문자열 확인](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [열거형을 사용하는 경우](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [상수 및 리터럴 데이터 형식](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)
