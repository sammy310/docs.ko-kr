---
title: 완화된 대리자 변환
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: b914d0479f160199744a8f9923c0bebc87321329
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086077"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>완화된 대리자 변환(Visual Basic)

완화 된 대리자 변환을 사용 하면 시그니처가 동일 하지 않더라도 sub 및 함수를 대리자나 처리기에 할당할 수 있습니다. 따라서 대리자에 대 한 바인딩은 이미 메서드 호출에 대해 허용 되는 바인딩과 일치 합니다.  
  
## <a name="parameters-and-return-type"></a>매개 변수 및 반환 형식  

 정확히 일치 하는 시그니처 대신, 완화 된 변환을 수행 하려면가로 설정 된 경우 다음 조건이 충족 되어야 합니다 `Option Strict` `On` .  
  
- 각 대리자 매개 변수의 데이터 형식에서 할당 된 함수 또는의 해당 매개 변수에 대 한 데이터 형식으로 확대 변환이 있어야 합니다 `Sub` . 다음 예제에서 대리자에 `Del1` 는 하나의 매개 변수 ()가 있습니다 `Integer` . `m`할당 된 람다 식의 매개 변수에는 `Integer` 또는와 같은 확대 변환이 있는 데이터 형식이 있어야 합니다 `Long` `Double` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     축소 변환은가로 설정 된 경우에만 허용 됩니다 `Option Strict` `Off` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- 확대 변환은 할당 된 함수의 반환 형식이 나 `Sub` 대리자의 반환 형식에서 반대 방향으로 존재 해야 합니다. 다음 예제에서의 반환 형식이 이므로 할당 된 각 람다 식의 본문은로 확대 되는 데이터 형식으로 계산 되어야 합니다 `Integer` `del1` `Integer` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 `Option Strict`가로 설정 되어 있으면 `Off` 확대 제한이 양방향으로 제거 됩니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a>매개 변수 사양을 생략 합니다.  

 완화 된 대리자를 사용 하 여 할당 된 메서드에서 매개 변수 사양을 완전히 생략할 수도 있습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 일부 매개 변수를 지정 하 고 다른 매개 변수는 생략할 수 없습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 매개 변수를 생략 하는 기능은 몇 가지 복잡 한 매개 변수가 관련 된 이벤트 처리기를 정의 하는 경우와 같은 상황에서 유용 합니다. 일부 이벤트 처리기에 대 한 인수는 사용 되지 않습니다. 대신 처리기는 이벤트가 등록 된 컨트롤의 상태에 직접 액세스 하 여 인수를 무시 합니다. 완화 된 대리자를 사용 하면 모호성 결과가 없을 때 이러한 선언에서 인수를 생략할 수 있습니다. 다음 예제에서는 완전히 지정 된 메서드를 `OnClick` 로 다시 작성할 수 있습니다 `RelaxedOnClick` .  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>AddressOf 예제  

 람다 식은 이전 예제에서 형식 관계를 쉽게 볼 수 있도록 하는 데 사용 됩니다. 그러나, 또는를 사용 하는 대리자 할당에는 동일한 relaxation 허용 됩니다 `AddressOf` `Handles` `AddHandler` .  
  
 다음 예제에서는,, `f1` 및 함수 `f2` 를 `f3` `f4` 모두에 할당할 수 있습니다 `Del1` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 다음 예는 `Option Strict` 가로 설정 된 경우에만 유효 `Off` 합니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a>함수 반환 삭제  

 완화 된 대리자 변환을 사용 하면 함수를 대리자에 할당 하 여 `Sub` 함수의 반환 값을 효과적으로 무시할 수 있습니다. 그러나를 함수 대리자에 할당할 수는 없습니다 `Sub` . 다음 예제에서는 함수 주소가 `doubler` delegate에 할당 됩니다 `Sub` `Del3` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a>참조

- [람다 식](../procedures/lambda-expressions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
- [대리자](index.md)
- [방법: Visual Basic에서 프로시저에 다른 프로시저 전달](how-to-pass-procedures-to-another-procedure.md)
- [지역 형식 유추](../variables/local-type-inference.md)
- [Option Strict 문](../../../language-reference/statements/option-strict-statement.md)
