---
title: Key
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 92c8809779d6cab524f67ee47f355b72ab152403
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351514"
---
# <a name="key-visual-basic"></a>Key(Visual Basic)
`Key` 키워드를 사용 하 여 익명 형식의 속성에 대 한 동작을 지정할 수 있습니다. 키 속성으로 지정 된 속성만 익명 형식 인스턴스 간의 같음 테스트 또는 해시 코드 값 계산과 관련 됩니다. 키 속성의 값은 변경할 수 없습니다.  
  
 초기화 목록에서 해당 선언 앞에 `Key` 키워드를 배치 하 여 익명 형식의 속성을 키 속성으로 지정 합니다. 다음 예제에서 `Airline` 및 `FlightNo`는 키 속성 이지만 `Gate`는 그렇지 않습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 새 익명 형식이 만들어지면 <xref:System.Object>에서 직접 상속 됩니다. 컴파일러는 <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>및 <xref:System.Object.ToString%2A>의 상속 된 세 멤버를 재정의 합니다. <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A>에 대해 생성 되는 재정의 코드는 키 속성을 기반으로 합니다. 형식에 키 속성이 없으면 <xref:System.Object.GetHashCode%2A> 및 <xref:System.Object.Equals%2A> 재정의 되지 않습니다.  
  
## <a name="equality"></a>같음  
 두 익명 형식 인스턴스는 동일한 형식의 인스턴스인 경우와 해당 키 속성의 값이 동일한 경우에 동일 합니다. 다음 예제에서 `flight2`은 동일한 익명 형식의 인스턴스이며 해당 키 속성에 대해 일치 하는 값을 가지 므로 이전 예제에서 `flight1`와 같습니다. 그러나 키 속성의 값이 서로 다르므로 `flight3`는 `flight1`와 같지 않습니다 `FlightNo`. 인스턴스 `flight4`는 키 속성으로 다른 속성을 지정 하기 때문에 `flight1`와 동일한 형식이 아닙니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 두 인스턴스가 키가 아닌 속성 (이름, 형식, 순서 및 값)만 사용 하 여 선언 된 경우 두 인스턴스는 같지 않습니다. 키 속성이 없는 인스턴스는 자체와 동일 합니다.  
  
 두 익명 형식 인스턴스가 동일한 익명 형식의 인스턴스인 조건에 대 한 자세한 내용은 [무명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조 하세요.  
  
## <a name="hash-code-calculation"></a>해시 코드 계산  
 <xref:System.Object.Equals%2A>와 마찬가지로 익명 형식에 대해 <xref:System.Object.GetHashCode%2A>에 정의 된 해시 함수는 형식의 키 속성을 기반으로 합니다. 다음 예에서는 키 속성과 해시 코드 값 간의 상호 작용을 보여 줍니다.  
  
 키가 아닌 속성에 일치 하는 값이 없는 경우에도 모든 키 속성에 대해 동일한 값을 가진 무명 형식의 인스턴스는 동일한 해시 코드 값을 갖습니다. 다음 문은 `True`을 반환 합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 하나 이상의 키 속성에 대 한 값이 서로 다른 익명 형식의 인스턴스는 해시 코드 값이 서로 다릅니다. 다음 문은 `False`을 반환 합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 서로 다른 속성을 키 속성으로 지정 하는 익명 형식의 인스턴스는 동일한 형식의 인스턴스가 아닙니다. 모든 속성의 이름과 값이 동일한 경우에도 해시 코드 값은 서로 다릅니다. 다음 문은 `False`을 반환 합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a>읽기 전용 값  
 키 속성의 값은 변경할 수 없습니다. 예를 들어 앞의 예제에서 `flight1` `Airline` 및 `FlightNo` 필드는 읽기 전용 이지만 `Gate`를 변경할 수 있습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a>참고 항목

- [익명 형식 정의](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
