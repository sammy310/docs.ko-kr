---
title: '방법: 람다 식 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: bb0bdb3c10a7df2ca954fbdb9382a25bf805068d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349750"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>방법: 람다 식 만들기(Visual Basic)
*람다 식은* 이름이 없는 함수 또는 서브루틴입니다. 람다 식은 대리자 형식이 유효한 모든 위치에서 사용할 수 있습니다.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>한 줄로 된 람다 식 함수를 만들려면  
  
1. 대리자 형식을 사용할 수 있는 경우 다음 예제와 같이 `Function`키워드를 입력 합니다.  
  
     `Dim add1 =`  `Function`  
  
2. 괄호 안에 `Function`바로 뒤에 함수의 매개 변수를 입력 합니다. `Function`후에는 이름을 지정 하지 않습니다.  
  
     `Dim add1 = Function`  `(num As Integer)`  
  
3. 매개 변수 목록 다음에 함수 본문으로 단일 식을 입력 합니다. 식이 계산 되는 값은 함수에서 반환 하는 값입니다. 반환 형식을 지정 하는 데 `As` 절을 사용 하지 않습니다.  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     정수 인수를 전달 하 여 람다 식을 호출 합니다.  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. 또는 다음 예제를 통해 동일한 결과를 얻을 수 있습니다.  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>한 줄로 된 람다 식 서브루틴을 만들려면  
  
1. 대리자 형식을 사용할 수 있는 경우 다음 예제와 같이 `Sub`키워드를 입력 합니다.  
  
     `Dim add1 =`  `Sub`  
  
2. 괄호 안에 `Sub`바로 뒤에 서브루틴의 매개 변수를 입력 합니다. `Sub`후에는 이름을 지정 하지 않습니다.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. 매개 변수 목록 다음에 단일 문을 서브루틴의 본문으로 입력 합니다.  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     문자열 인수를 전달 하 여 람다 식을 호출 합니다.  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>여러 줄 람다 식 함수를 만들려면  
  
1. 대리자 형식을 사용할 수 있는 경우 다음 예제와 같이 `Function`키워드를 입력 합니다.  
  
     `Dim add1 =`  `Function`  
  
2. 괄호 안에 `Function`바로 뒤에 함수의 매개 변수를 입력 합니다. `Function`후에는 이름을 지정 하지 않습니다.  
  
     `Dim add1 = Function`  `(index As Integer)`  
  
3. Enter 키를 누릅니다. `End Function` 문이 자동으로 추가 됩니다.  
  
4. 함수 본문 내에서 다음 코드를 추가 하 여 식을 만들고 값을 반환 합니다. 반환 형식을 지정 하는 데 `As` 절을 사용 하지 않습니다.  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     정수 인수를 전달 하 여 람다 식을 호출 합니다.  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>여러 줄 람다 식 서브루틴을 만들려면  
  
1. 대리자 형식을 사용할 수 있는 경우 다음 예제와 같이 `Sub`키워드를 입력 합니다.  
  
     `Dim add1 =`  `Sub`  
  
2. 괄호 안에 `Sub`바로 뒤에 서브루틴의 매개 변수를 입력 합니다. `Sub`후에는 이름을 지정 하지 않습니다.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. Enter 키를 누릅니다. `End Sub` 문이 자동으로 추가 됩니다.  
  
4. 함수 본문 내에서 서브루틴이 호출 될 때 실행할 다음 코드를 추가 합니다.  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     문자열 인수를 전달 하 여 람다 식을 호출 합니다.  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a>예제  
 람다 식의 일반적인 용도는 `Delegate`형식이 인 매개 변수에 대 한 인수로 전달 될 수 있는 함수를 정의 하는 것입니다. 다음 예제에서 <xref:System.Diagnostics.Process.GetProcesses%2A> 메서드는 로컬 컴퓨터에서 실행 되는 프로세스의 배열을 반환 합니다. <xref:System.Linq.Enumerable> 클래스의 <xref:System.Linq.Enumerable.Where%2A> 메서드는 `Boolean` 대리자를 인수로 사용 해야 합니다. 예제의 람다 식이이 목적에 사용 됩니다. 스레드를 하나만 포함 하는 각 프로세스에 대해 `True`를 반환 하 고 `filteredList`에서 선택 합니다.  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 이전 예제는 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 구문으로 작성 된 다음 코드와 동일 합니다.  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Linq.Enumerable>
- [람다 식](./lambda-expressions.md)
- [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [방법: Visual Basic에서 프로시저에 다른 프로시저 전달](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Delegate 문](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
