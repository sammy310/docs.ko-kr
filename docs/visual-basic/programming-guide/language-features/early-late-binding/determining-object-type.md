---
description: '자세한 정보: 개체 형식 확인 (Visual Basic)'
title: 개체 형식 확인
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 0cf64b6dde74b98edaf055537533cb648ed3381a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434409"
---
# <a name="determining-object-type-visual-basic"></a>개체 형식 확인(Visual Basic)

제네릭 개체 변수 (즉,로 선언 하는 변수 `Object` )는 모든 클래스의 개체를 보유할 수 있습니다. 형식의 변수를 사용 하는 경우 `Object` 개체의 클래스에 따라 다른 작업을 수행 해야 할 수 있습니다. 예를 들어 일부 개체는 특정 속성이 나 메서드를 지원 하지 않을 수 있습니다. Visual Basic은 개체 변수에 저장 되는 개체의 형식, 함수 및 연산자를 결정 하는 두 가지 방법을 제공 `TypeName` `TypeOf...Is` 합니다.  
  
## <a name="typename-and-typeofis"></a>TypeName 및 TypeOf ... 되었습니다  

 `TypeName`함수는 문자열을 반환 하며 다음 코드 조각과 같이 개체의 클래스 이름을 저장 하거나 표시 해야 하는 경우에 가장 적합 합니다.  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 연산자는를 `TypeOf...Is` 사용 하 여 문자열을 비교 하는 것 보다 훨씬 빠르기 때문에 개체 형식을 테스트 하는 데 가장 적합 합니다 `TypeName` . 다음 코드 조각에서는 `TypeOf...Is` 문 내에서를 사용 합니다 `If...Then...Else` .  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 주의 해야 합니다. `TypeOf...Is`연산자는 `True` 개체가 특정 형식 이거나 특정 형식에서 파생 된 경우를 반환 합니다. Visual Basic와 관련 하 여 수행 하는 거의 모든 작업에는 개체 (예: 문자열 및 정수)로 일반적으로 고려 되지 않는 일부 요소를 포함 하는 개체가 포함 됩니다. 이러한 개체는에서 파생 되며에서 메서드를 상속 <xref:System.Object> 합니다. 를 전달 `Integer` 하 고를 사용 하 여를 계산 하 `Object` 는 경우 연산자는을 `TypeOf...Is` 반환 `True` 합니다. 다음 예제에서는 매개 변수가 및 임을 보고 합니다 `InParam` `Object` `Integer` .  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 다음 예제에서는 및를 모두 사용 하 여 `TypeOf...Is` `TypeName` 인수에 전달 된 개체의 형식을 확인 합니다 `Ctrl` . `TestObject`프로시저는 `ShowType` 세 가지 다른 종류의 컨트롤을 사용 하 여를 호출 합니다.  
  
#### <a name="to-run-the-example"></a>예제를 실행하려면  
  
1. 새 Windows 응용 프로그램 프로젝트를 만들고 컨트롤 <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.CheckBox> 컨트롤 및 <xref:System.Windows.Forms.RadioButton> 컨트롤을 폼에 추가 합니다.  
  
2. 폼의 단추에서 프로시저를 호출 `TestObject` 합니다.  
  
3. 폼에 다음 코드를 추가 합니다.  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>추가 정보

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [문자열 이름을 사용하여 속성 또는 메서드 호출](calling-a-property-or-method-using-a-string-name.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [If...Then...Else 문](../../../language-reference/statements/if-then-else-statement.md)
- [문자열 데이터 형식](../../../language-reference/data-types/string-data-type.md)
- [Integer 데이터 형식](../../../language-reference/data-types/integer-data-type.md)
