---
title: Nothing(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 97c651dbcc657fbab0706c9a959bd0031c0fe343
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826095"
---
# <a name="nothing-visual-basic"></a>Nothing(Visual Basic)
모든 데이터 형식의 기본 값을 나타냅니다. 기본값은 참조 형식에 대해는 `null` 참조 합니다. 값 형식에 대 한 기본값의 값 형식은 nullable 인지에 따라 달라 집니다.  
  
> [!NOTE]
>  Nullable이 아닌 값 형식에 대 한 `Nothing` Visual basic에서에서 다른 `null` 에서 C#합니다. Visual basic에서는 null이 아닌 값 형식의 변수를 설정한 경우 `Nothing`, 변수의 선언 된 형식에 대 한 기본 값으로 설정 됩니다. C#nullable이 아닌 값 형식의 변수를 할당 하는 경우 `null`, 컴파일 시간 오류가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 `Nothing` 데이터 형식의 기본 값을 나타냅니다. 기본 값을 값 형식 또는 참조 형식의 변수 인지에 따라 달라 집니다.  
  
 변수를 *값 형식* 직접 해당 값을 포함 합니다. 값 형식은 숫자 데이터 형식을 모두 포함 `Boolean`, `Char`, `Date`, 모든 구조 및 모든 열거 합니다. 변수를 *참조 형식* 메모리에 개체의 인스턴스에 대 한 참조를 저장 합니다. 참조 형식 클래스, 배열, 대리자 및 문자열을 포함 합니다. 자세한 내용은 [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)을 참조하세요.  
  
 변수 값의 경우 입력, 동작 `Nothing` null 허용 데이터 형식 변수 인지에 따라 달라 집니다. Nullable 값 형식을 나타낼 추가 `?` 한정자를 형식 이름입니다. 할당 `Nothing` nullable 변수를 값으로 설정 `null`합니다. 자세한 내용 및 예제를 참조 하세요 [Nullable 값 형식](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)합니다.  
  
 Null을 허용 하는 값 형식 변수에 있으면 할당 `Nothing` 를 설정 하기 기본값으로 선언 된 형식에 대 한 합니다. 변수 멤버를 포함 하는 형식임을 하는 경우 모두 기본값으로 설정 됩니다. 다음 예에서는 스칼라 형식에 대 한이 설명 합니다.  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 할당 변수는 참조 형식의 경우 `Nothing` 변수를 설정는 `null` 변수 형식의 참조입니다. 로 설정 된 변수는 `null` 참조 개체와 연결 되어 있지 않습니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 변수는 참조 (또는 null 허용 값 입력) 하는지 여부를 확인 하는 경우 `null`를 사용 하지 마세요 `= Nothing` 또는 `<> Nothing`합니다. 항상 사용 하 여 `Is Nothing` 또는 `IsNot Nothing`합니다.  
  
 Visual Basic에서 문자열의 경우 빈 문자열 같음 `Nothing`합니다. 따라서 `"" = Nothing` 그렇습니다.  
  
 다음 예제에서는 사용 하는 비교는 `Is` 고 `IsNot` 연산자입니다.  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 사용 하지 않고 변수를 선언 하는 경우는 `As` 절으로 설정 하 고 `Nothing`, 변수의 형식이 `Object`합니다. 이러한 예로 `Dim something = Nothing`합니다. 컴파일 타임 오류가 발생 하는 예제의 경우 `Option Strict` 에 및 `Option Infer` 꺼져 있습니다.  
  
 할당 하는 경우 `Nothing` 를 개체 변수에 더 이상 참조 개체 인스턴스를 합니다. 변수의 이전 인스턴스로 참조를 한 경우 설정 `Nothing` 자체 인스턴스를 종료 하지 않습니다. 인스턴스가 종료 됩니다 하 고 남은 참조가 없는 활성화는 가비지 수집기 (GC) 검색 한 후에 연결 된 메모리 및 시스템 리소스를 해제 됩니다.  
  
 `Nothing` 다른는 <xref:System.DBNull> 는 초기화 되지 않은 variant 또는 존재 하지 않는 데이터베이스 열을 나타내는 개체입니다.  
  
## <a name="see-also"></a>참고자료

- [Dim 문](../../visual-basic/language-reference/statements/dim-statement.md)
- [개체 수명: 개체가 만들어지고 제거 하는 방법](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Visual Basic의 수명](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Is 연산자](../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot 연산자](../../visual-basic/language-reference/operators/isnot-operator.md)
- [Nullable 값 형식](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
