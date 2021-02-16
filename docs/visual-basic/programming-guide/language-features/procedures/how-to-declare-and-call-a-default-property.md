---
description: '자세한 정보: 방법: 기본 속성 선언 및 호출 Visual Basic'
title: '방법: 기본 속성 선언 및 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 2a0e82fe89bb89613996f613930ace1aa6e41b7f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472451"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>방법: Visual Basic에서 기본 속성 선언 및 호출

*기본 속성* 은 코드에서 지정 하지 않고 액세스할 수 있는 클래스 또는 구조체 속성입니다. 호출 코드에서 클래스 또는 구조체의 이름을 지정할 수 있지만 속성이 아닌 경우, 컨텍스트는 속성에 대 한 액세스를 허용 하 고, Visual Basic는 해당 클래스 또는 구조체의 기본 속성 (있는 경우)에 대 한 액세스를 확인 합니다.  
  
 클래스 또는 구조체에는 최대 하나의 기본 속성만 있을 수 있습니다. 그러나 기본 속성을 오버 로드 하 고 둘 이상의 버전을 가질 수 있습니다.  
  
 자세한 내용은 [기본값](../../../language-reference/modifiers/default.md)을 참조 하세요.  
  
### <a name="to-declare-a-default-property"></a>기본 속성을 선언 하려면  
  
1. 일반적인 방법으로 속성을 선언 합니다. 또는 키워드를 지정 하지 마십시오 `Shared` `Private` .  
  
2. `Default`속성 선언에 키워드를 포함 합니다.  
  
3. 속성에 대 한 매개 변수를 하나 이상 지정 하십시오. 하나 이상의 인수를 사용 하지 않는 기본 속성을 정의할 수 없습니다.  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a>기본 속성을 호출 하려면  
  
1. 포함 하는 클래스 또는 구조체 형식의 변수를 선언 합니다.  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. 일반적으로 속성 이름을 포함 하는 식에는 변수 이름만 사용 합니다.  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. 변수 이름 뒤에 인수 목록이 괄호로 묶여 있습니다. 기본 속성은 하나 이상의 인수를 사용 해야 합니다.  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. 기본 속성 값을 검색 하려면 인수 목록과 함께 변수 이름을 식에 사용 하거나 대입문에 등호 () 기호를 사용 합니다 `=` .  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. 기본 속성 값을 설정 하려면 인수 목록과 함께 변수 이름을 대입문의 왼쪽에 사용 합니다.  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. 다른 속성에 액세스 하는 것 처럼 항상 기본 속성 이름을 변수 이름과 함께 지정할 수 있습니다.  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a>예  

 다음 예제에서는 클래스에 대 한 기본 속성을 선언 합니다.  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a>예  

 다음 예제에서는 클래스에서 기본 속성을 호출 하는 방법을 보여 줍니다 `myProperty` `class1` . 세 개의 대입문은에 값 `myProperty` 을 저장 하 고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 호출은 값을 읽습니다.  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 기본 속성의 가장 일반적인 용도는 <xref:Microsoft.VisualBasic.Collection.Item%2A> 다양 한 컬렉션 클래스의 속성입니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  

 기본 속성은 소스 코드 문자를 조금 줄일 수 있지만 코드를 읽기 어렵게 만들 수 있습니다. 호출 코드가 클래스 또는 구조체를 사용 하는 데 익숙하지 않은 경우 클래스 또는 구조체 이름에 대 한 참조를 만들 때 참조가 클래스나 구조체 자체에 액세스 하는지 아니면 기본 속성에 액세스 하는지 여부를 확신할 수 없습니다. 이로 인해 컴파일러 오류 또는 미묘한 런타임 논리 오류가 발생할 수 있습니다.  
  
 항상 [Option Strict 문을](../../../language-reference/statements/option-strict-statement.md) 사용 하 여 컴파일러 유형 검사를로 설정 하 여 기본 속성 오류의 가능성을 약간 줄일 수 있습니다 `On` .  
  
 코드에서 미리 정의 된 클래스 또는 구조체를 사용 하려는 경우 기본 속성이 있는지 여부를 확인 하 고, 해당 하는 경우 이름을 지정 해야 합니다.  
  
 이러한 단점 때문에 기본 속성을 정의 하지 않는 것이 좋습니다. 코드 가독성을 위해 기본 속성도 항상 모든 속성을 명시적으로 참조 하는 것도 고려해 야 합니다.  
  
## <a name="see-also"></a>추가 정보

- [속성 프로시저](./property-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [기본값](../../../language-reference/modifiers/default.md)
- [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)
- [방법: 속성 만들기](./how-to-create-a-property.md)
- [방법: 액세스 수준이 혼합된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)
- [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)
- [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)
- [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)
