---
description: '자세한 정보: 방법: 열거형 값과 연결 된 문자열 확인 (Visual Basic)'
title: '방법: 열거형 값과 연결된 문자열 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 391cb097fa8163f7131cc30f85f8a4f85ba826a4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471606"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a>방법: 열거형 값과 연결된 문자열 확인(Visual Basic)

<xref:System.Enum.GetValues%2A>및 메서드를 사용 하 여 <xref:System.Enum.GetNames%2A> 열거형 멤버와 연결 된 문자열 및 값을 확인할 수 있습니다.  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a>열거형과 연결 된 문자열을 확인 하려면  
  
- 메서드를 사용 <xref:System.Enum.GetNames%2A> 하 여 열거형 멤버와 연결 된 문자열을 검색 합니다. 이 예제에서는 열거형를 선언한 `flavorEnum` 다음 메서드를 사용 하 여 <xref:System.Enum.GetNames%2A> 각 멤버와 관련 된 문자열을 표시 합니다.  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a>추가 정보

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [방법: 열거형 선언](how-to-declare-enumerations.md)
- [방법: 열거형 멤버 참조](how-to-refer-to-an-enumeration-member.md)
- [열거형 및 이름 한정](enumerations-and-name-qualification.md)
- [방법: Visual Basic에서 열거형 반복](how-to-iterate-through-an-enumeration.md)
- [열거형을 사용하는 경우](when-to-use-an-enumeration.md)
- [Enum 문](../../../language-reference/statements/enum-statement.md)
