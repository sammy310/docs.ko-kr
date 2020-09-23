---
title: '방법: 열거형 반복'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 21c170d4708b90987a3f1e9c18969b8803fcdbe0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058718"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>방법: Visual Basic에서 열거형 반복

열거형은 관련된 상수 집합으로 작업하고 이름과 상수 값을 연결하는 편리한 방법을 제공합니다. 열거형을 반복 하려면 메서드를 사용 하 여 배열로 이동할 수 있습니다 <xref:System.Enum.GetValues%2A> . `For...Each`또는 메서드를 사용 하 여 <xref:System.Enum.GetNames%2A> <xref:System.Enum.GetValues%2A> 문자열 또는 숫자 값을 추출 하는 문을 사용 하 여 열거형을 반복할 수도 있습니다.  
  
### <a name="to-iterate-through-an-enumeration"></a>열거형을 반복 하려면  
  
- 배열을 선언 하 고 <xref:System.Enum.GetValues%2A> 다른 변수와 마찬가지로 배열을 전달 하기 전에 메서드를 사용 하 여 열거형을 변환 합니다. 다음 예제에서는 열거형을 반복 하면서 열거형의 각 멤버를 표시 합니다 <xref:Microsoft.VisualBasic.FirstDayOfWeek> .  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>참조

- [열거형 개요](enumerations-overview.md)
- [방법: 열거형 선언](how-to-declare-enumerations.md)
- [열거형을 사용하는 경우](when-to-use-an-enumeration.md)
- [방법: 열거형 값과 연결된 문자열 확인](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [방법: 열거형 멤버 참조](how-to-refer-to-an-enumeration-member.md)
- [열거형 및 이름 한정](enumerations-and-name-qualification.md)
- [배열](../arrays/index.md)
