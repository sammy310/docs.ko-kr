---
title: 제네릭 프로시저
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: 16a629e07cf711778b3d8d1863958ec7a6300649
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350079"
---
# <a name="generic-procedures-in-visual-basic"></a>Generic Procedures in Visual Basic
제네릭 *메서드*라고도 하는 *제네릭 프로시저*는 하나 이상의 형식 매개 변수를 사용 하 여 정의 된 프로시저입니다. 이를 통해 호출 코드는 프로시저를 호출할 때마다 데이터 형식을 요구 사항에 맞게 조정할 수 있습니다.  
  
 프로시저는 제네릭 클래스 또는 제네릭 구조체 내에서 정의 되는 것 만으로는 제네릭이 아닙니다. 제네릭 하려면 프로시저에서 사용할 수 있는 일반 매개 변수 외에도 하나 이상의 형식 매개 변수를 사용 해야 합니다. 제네릭 클래스 또는 구조체는 제네릭이 아닌 프로시저를 포함할 수 있으며 제네릭이 아닌 클래스, 구조체 또는 모듈은 제네릭 프로시저를 포함할 수 있습니다.  
  
 제네릭 프로시저의 형식 매개 변수는 해당 형식 매개 변수를 반환 형식 (있는 경우) 및 해당 프로시저 코드에 사용할 수 있습니다.  
  
## <a name="type-inference"></a>형식 유추  
 모든 형식 인수를 제공 하지 않고 제네릭 프로시저를 호출할 수 있습니다. 이러한 방식으로 호출 하는 경우 컴파일러는 적절 한 데이터 형식을 확인 하 여 프로시저의 형식 인수에 전달 합니다. 이를 *형식 유추*라고 합니다. 다음 코드는 `t`형식 매개 변수에 `String` 형식을 전달 해야 한다는 것을 컴파일러에서 유추 하는 호출을 보여 줍니다.  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 컴파일러가 호출 컨텍스트에서 형식 인수를 유추할 수 없는 경우 오류를 보고 합니다. 이러한 오류의 가능한 원인 중 하나는 배열 순위가 일치 하지 않기 때문입니다. 예를 들어 일반 매개 변수를 형식 매개 변수의 배열로 정의 한다고 가정 합니다. 다른 순위 (차원 수)의 배열을 제공 하는 제네릭 프로시저를 호출 하면 형식 유추가 실패 합니다. 다음 코드에서는 2 차원 배열이 1 차원 배열을 필요로 하는 프로시저로 전달 되는 호출을 보여 줍니다.  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 형식 유추는 모든 형식 인수를 생략 하는 경우에만 호출할 수 있습니다. 하나의 형식 인수를 제공 하는 경우 모두 제공 해야 합니다.  
  
 형식 유추는 제네릭 프로시저에만 지원 됩니다. 제네릭 클래스, 구조체, 인터페이스 또는 대리자에 대해서는 형식 유추를 호출할 수 없습니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 배열의 특정 요소를 찾기 위한 일반적인 `Function` 프로시저를 정의 합니다. 하나의 형식 매개 변수를 정의 하 고이를 사용 하 여 매개 변수 목록에서 두 개의 매개 변수를 생성 합니다.  
  
### <a name="code"></a>코드  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a>설명  
 앞의 예제에서는 `searchArray`의 각 요소에 대해 `searchValue`를 비교 하는 기능이 필요 합니다. 이 기능을 보장 하기 위해 `T` 형식 매개 변수를 제한 하 여 <xref:System.IComparable%601> 인터페이스를 구현 합니다. `T`에 제공 된 형식 인수가 `=` 연산자를 지원함을 보장 하지 않기 때문에이 코드에서는 `=` 연산자 대신 <xref:System.IComparable%601.CompareTo%2A> 메서드를 사용 합니다.  
  
 다음 코드를 사용 하 여 `findElement` 프로시저를 테스트할 수 있습니다.  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 위의 `MsgBox` 호출은 각각 "0", "1" 및 "-1"을 표시 합니다.  
  
## <a name="see-also"></a>참고 항목

- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [방법: 제네릭 클래스 사용](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [절차](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [프로시저 매개 변수 및 인수](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [형식 목록](../../../../visual-basic/language-reference/statements/type-list.md)
- [매개 변수 목록](../../../../visual-basic/language-reference/statements/parameter-list.md)
