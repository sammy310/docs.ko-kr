---
title: 열거형을 사용하는 경우
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 5daae8d487ddfe079a54e305e59e32e8ded8f65e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353954"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>열거형을 사용하는 경우(Visual Basic)
열거형은 관련 된 상수 집합을 사용 하는 쉬운 방법을 제공 합니다. 열거형 또는 `Enum`는 값 집합에 대 한 기호화 된 이름입니다. 열거형은 데이터 형식으로 처리 되며 변수 및 속성에 사용할 상수 집합을 만드는 데 사용할 수 있습니다.  
  
## <a name="when-to-use-an-enumeration"></a>열거형을 사용하는 경우  
 프로시저에서 제한 된 변수 집합을 허용 하는 경우에는 열거형을 사용 하는 것이 좋습니다. 열거를 사용 하면 특히 의미 있는 이름을 사용 하는 경우 더 명확 하 고 읽기 쉬운 코드를 만들 수 있습니다.  
  
 열거형 사용의 이점은 다음과 같습니다.  
  
- 바꾸려면 또는 잘못 된 숫자로 인 한 오류를 줄입니다.  
  
- 를 사용 하면 나중에 값을 쉽게 변경할 수 있습니다.  
  
- 코드를 더 쉽게 읽을 수 있습니다. 즉, 오류가 증가 하는 가능성이 줄어듭니다.  
  
- 이전 버전과의 호환성을 보장 합니다. 열거를 사용 하면 나중에 누군가가 멤버 이름에 해당 하는 값을 변경 하는 경우 코드가 실패할 가능성이 낮아집니다.  
  
## <a name="naming-enumerations"></a>열거형 이름 지정  
 열거형 멤버에 대 한 명명 규칙을 사용 합니다. Visual Basic 열거형 멤버 이름이 발견 되 면 참조 된 다른 형식 라이브러리에 같은 이름이 포함 되어 있으면 예외가 throw 될 수 있습니다. 응용 프로그램 또는 구성 요소의 값을 식별 하는 고유한 접두사를 사용 합니다.  
  
 열거형의 멤버를 참조 하는 경우 열거형 이름으로 멤버 이름을 한정 하거나 `Imports` 문을 사용 해야 합니다. 자세한 내용은 [열거 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)을 참조 하세요.  
  
## <a name="predefined-enumerations"></a>미리 정의 된 열거형  
 Visual Basic은 코드를 용이 하 게 하기 위해 `FirstDayOfWeek` 및 `MsgBoxResult`와 같은 미리 정의 된 많은 열거형을 제공 합니다. 이러한 목록은 [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [방법: 열거형 멤버 참조](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [방법: Visual Basic에서 열거형 반복](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [방법: 열거형 값과 연결된 문자열 확인](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Enum 문](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)
