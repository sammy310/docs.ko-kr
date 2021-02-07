---
description: '자세한 정보: IsTrue 연산자 (Visual Basic)'
title: IsTrue 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 50b618c888ce988da5241041fb2f728e0a581c70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665655"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue 연산자(Visual Basic)

식이 인지 여부를 확인 `True` 합니다.  
  
 `IsTrue`코드에서 명시적으로 호출할 수는 없지만 Visual Basic 컴파일러는이를 사용 하 여 절에서 코드를 생성할 수 있습니다 `OrElse` . 클래스 또는 구조체를 정의한 다음 해당 형식의 변수를 절에서 사용 하는 경우 `OrElse` `IsTrue` 해당 클래스 또는 구조체에 대해를 정의 해야 합니다.  
  
 컴파일러는 `IsTrue` 및 연산자를 `IsFalse` 일치 하는 *쌍* 으로 간주 합니다. 즉, 이러한 항목 중 하나를 정의 하는 경우 다른 항목을 정의 해야 합니다.  
  
## <a name="compiler-use-of-istrue"></a>IsTrue의 컴파일러 사용  

 클래스 또는 구조체를 정의한 경우 `For` ,, `If` `Else If` 또는 `While` 문이나 `When` 절에서 해당 형식의 변수를 사용할 수 있습니다. 이 작업을 수행 하는 경우 컴파일러는 `Boolean` 조건을 테스트할 수 있도록 형식을 값으로 변환 하는 연산자가 필요 합니다. 다음 순서에 따라 적합 한 연산자를 검색 합니다.  
  
1. 클래스 또는 구조체에서로의 확대 변환 연산자 `Boolean` 입니다.  
  
2. 클래스 또는 구조체에서로의 확대 변환 연산자 `Boolean?` 입니다.  
  
3. `IsTrue`클래스 또는 구조체의 연산자입니다.  
  
4. 로의 축소 변환은 `Boolean?` 에서로의 변환이 포함 되지 않습니다 `Boolean` `Boolean?` .  
  
5. 클래스 또는 구조체에서로의 축소 변환 연산자 `Boolean` 입니다.  
  
 또는 연산자로의 변환이 정의 되지 않은 경우 `Boolean` `IsTrue` 컴파일러는 오류를 표시 합니다.  
  
> [!NOTE]
> `IsTrue`연산자를 *오버 로드할* 수 있습니다. 즉, 해당 피연산자의 형식이 해당 클래스 또는 구조체의 형식인 경우 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다. 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  

 다음 코드 예제에서는 및 연산자에 대 한 정의를 포함 하는 구조체의 개요를 정의 합니다 `IsFalse` `IsTrue` .  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>참고 항목

- [IsFalse 연산자](isfalse-operator.md)
- [방법: 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [OrElse 연산자](orelse-operator.md)
