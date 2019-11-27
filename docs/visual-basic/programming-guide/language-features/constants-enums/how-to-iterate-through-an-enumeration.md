---
title: '방법: 열거형 반복'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 6e8fd6760565a73d9d3b3d1d02fc872992eea354
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354016"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>방법: Visual Basic에서 열거형 반복
열거형은 관련된 상수 집합으로 작업하고 이름과 상수 값을 연결하는 편리한 방법을 제공합니다. 열거형을 반복 하려면 <xref:System.Enum.GetValues%2A> 메서드를 사용 하 여 배열로 이동할 수 있습니다. <xref:System.Enum.GetNames%2A> 또는 <xref:System.Enum.GetValues%2A> 메서드를 사용 하 여 문자열 또는 숫자 값을 추출 하는 `For...Each` 문을 사용 하 여 열거형을 반복할 수도 있습니다.  
  
### <a name="to-iterate-through-an-enumeration"></a>열거형을 반복 하려면  
  
- 배열을 선언 하 고 다른 변수와 마찬가지로 배열을 전달 하기 전에 <xref:System.Enum.GetValues%2A> 메서드를 사용 하 여 열거형을 변환 합니다. 다음 예제에서는 열거형을 반복할 때 열거형 <xref:Microsoft.VisualBasic.FirstDayOfWeek>의 각 멤버를 표시 합니다.  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>참고자료

- [열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [열거형을 사용하는 경우](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [방법: 열거형 값과 연결된 문자열 확인](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [방법: 열거형 멤버 참조](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
