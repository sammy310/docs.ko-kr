---
title: IsTrue 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349506"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue 연산자(Visual Basic)
식이 `True`되는지 여부를 확인 합니다.  
  
 `IsTrue`는 코드에서 명시적으로 호출할 수 없지만 Visual Basic 컴파일러는이를 사용 하 여 `OrElse` 절에서 코드를 생성할 수 있습니다. 클래스 또는 구조체를 정의 하 고 `OrElse` 절에서 해당 형식의 변수를 사용 하는 경우 해당 클래스 또는 구조체에서 `IsTrue`를 정의 해야 합니다.  
  
 컴파일러는 `IsTrue` 및 `IsFalse` 연산자를 일치 하는 *쌍*으로 간주 합니다. 즉, 이러한 항목 중 하나를 정의 하는 경우 다른 항목을 정의 해야 합니다.  
  
## <a name="compiler-use-of-istrue"></a>IsTrue의 컴파일러 사용  
 클래스 또는 구조체를 정의 하는 경우 `For`, `If`, `Else If`또는 `While` 문이나 `When` 절에서 해당 형식의 변수를 사용할 수 있습니다. 이 작업을 수행 하는 경우 컴파일러는 조건을 테스트할 수 있도록 형식을 `Boolean` 값으로 변환 하는 연산자가 필요 합니다. 다음 순서에 따라 적합 한 연산자를 검색 합니다.  
  
1. 클래스 또는 구조체의 확대 변환 연산자를 `Boolean`합니다.  
  
2. 클래스 또는 구조체의 확대 변환 연산자를 `Boolean?`합니다.  
  
3. 클래스 또는 구조체의 `IsTrue` 연산자입니다.  
  
4. `Boolean`에서 `Boolean?`로의 변환이 포함 되지 않는 `Boolean?`로의 축소 변환입니다.  
  
5. 클래스 또는 구조체에서 `Boolean`하는 축소 변환 연산자입니다.  
  
 `Boolean` 또는 `IsTrue` 연산자에 대 한 변환을 정의 하지 않은 경우 컴파일러는 오류를 표시 합니다.  
  
> [!NOTE]
> `IsTrue` 연산자는 *오버 로드*될 수 있습니다. 즉, 클래스 또는 구조체의 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 재정의할 수 있습니다. 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `IsFalse` 및 `IsTrue` 연산자에 대 한 정의를 포함 하는 구조체의 개요를 정의 합니다.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>참고 항목

- [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [OrElse 연산자](../../../visual-basic/language-reference/operators/orelse-operator.md)
