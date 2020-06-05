---
title: '방법: 열거형 멤버 참조'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: 66c527bd4ba4721065de8fca8534fe652d0139be
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414416"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a>방법: 열거형 멤버 참조(Visual Basic)
열거형은 관련 상수 집합을 사용 하는 편리한 방법을 제공 하 고 상수 값을 이름에 연결 하는 편리한 방법을 제공 합니다. 예를 들어 요일과 연결된 정수 상수에 대한 열거형을 선언한 다음, 코드에 정수 값 대신 요일 이름을 사용할 수 있습니다.  
  
 문에 정규화 된 이름을 사용 하지 않을 수 있습니다 `Imports` . 자세한 내용은 [열거 및 이름 한정](enumerations-and-name-qualification.md)을 참조 하세요.  
  
### <a name="to-refer-to-an-enumeration-member"></a>열거형 멤버를 참조 하려면  
  
- 열거형을 사용 하 여 멤버 이름을 한정 합니다. 예를 들어 다음 예제에서는 `Saturday` 열거형의 멤버를 `FirstDayOfWeek` 변수에 할당 `DayValue` 합니다.  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a>참고 항목

- [방법: 열거형 선언](how-to-declare-enumerations.md)
- [열거형 및 이름 한정](enumerations-and-name-qualification.md)
- [방법: Visual Basic에서 열거형 반복](how-to-iterate-through-an-enumeration.md)
- [방법: 열거형 값과 연결된 문자열 확인](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [열거형을 사용하는 경우](when-to-use-an-enumeration.md)
