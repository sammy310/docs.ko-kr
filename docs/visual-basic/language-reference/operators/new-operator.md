---
title: New 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 630b0c48def77449f426b287a26f95af7cfb930e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837732"
---
# <a name="new-operator-visual-basic"></a>New 연산자(Visual Basic)
소개는 `New` 새 개체 인스턴스를 만들려면 절 형식 매개 변수에 생성자 제약 조건이 지정 또는 식별을 `Sub` 클래스 생성자로 프로시저입니다.  
  
## <a name="remarks"></a>설명  
 선언 또는 대입문을 `New` 절에 정의 된 클래스의 인스턴스를 만들 수는 지정 해야 합니다. 이 클래스는 호출 코드에 액세스할 수 있는 하나 이상의 생성자를 노출 해야 함을 의미 합니다.  
  
 사용할 수는 `New` 선언문 또는 대입문 절. 문이 실행 될 때 제공한 인수를 전달 하며, 지정된 된 클래스의 적절 한 생성자를 호출 합니다. 다음 예제에서는 인스턴스를 만들어이 `Customer` 클래스는 두 명의 생성자는 매개 변수를 사용 하는 및 문자열 매개 변수를 사용 하는 것입니다.  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 배열 클래스 이므로 `New` 다음 예와에서 같이 새 배열 인스턴스를 만들 수 있습니다.  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 CLR (공용 언어 런타임) throw는 <xref:System.OutOfMemoryException> 새 인스턴스를 만드는 메모리가 부족 한 경우 오류가 발생 합니다.  
  
> [!NOTE]
>  `New` 키워드는 또한 제공된 된 형식이 액세스할 수 있는 매개 변수가 없는 생성자를 노출 하도록 지정 하려면 형식 매개 변수 목록에서 사용 됩니다. 형식 매개 변수 및 제약 조건에 대 한 자세한 내용은 참조 하세요. [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)합니다.  
  
 생성자를 클래스에 대 한 프로시저를 만들려면의 이름을 설정를 `Sub` 하는 절차는 `New` 키워드입니다. 자세한 내용은 참조 하세요. [개체 수명: 개체가 만들어지고 제거 하는 방법을](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)합니다.  
  
 `New` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고자료

- <xref:System.OutOfMemoryException>
- [C++ 키워드](../../../visual-basic/language-reference/keywords/index.md)
- [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)
- [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [개체 수명: 개체가 만들어지고 제거 하는 방법](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
