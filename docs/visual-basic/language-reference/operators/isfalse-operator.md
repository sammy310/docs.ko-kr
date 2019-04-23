---
title: IsFalse 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 9f25c406038486224c2c4708c86ef86889c44c15
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818490"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse 연산자(Visual Basic)
식이 인지 결정 `False`합니다.  
  
 호출할 수 없습니다 `IsFalse` 명시적으로 코드 에서만 Visual Basic 컴파일러는 데 사용할 수에서 코드를 생성할 `AndAlso` 절. 클래스 또는 구조체 정의 다음에 있는 해당 유형의 변수를 사용 하는 경우는 `AndAlso` 정의 해야 절 `IsFalse` 해당 클래스 또는 구조체에서 합니다.  
  
 컴파일러에서 고려 하는 `IsFalse` 및 `IsTrue` 연산자는 *일치 하는 쌍*합니다. 이 그 중 하나를 정의 하는 경우 정의 해야 합니다도 다른 것을 의미 합니다.  
  
> [!NOTE]
>  합니다 `IsFalse` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드 예제에 대 한 정의 포함 하는 구조체의 윤곽선을 정의 합니다 `IsFalse` 고 `IsTrue` 연산자입니다.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>참고자료

- [IsTrue 연산자](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md)
