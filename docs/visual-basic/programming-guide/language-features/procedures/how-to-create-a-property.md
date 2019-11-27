---
title: '방법: 속성 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: ee5a9f687765ce064eb3c3f84218ed36eb916d9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349705"
---
# <a name="how-to-create-a-property-visual-basic"></a>방법: 속성 만들기(Visual Basic)
`Property` 문과 `End Property` 문 사이에 속성 정의를 묶습니다. 이 정의 내에서 `Get` 프로시저, `Set` 프로시저 또는 둘 다를 정의 합니다. 모든 속성의 코드는 이러한 프로시저 내에 있습니다.  
  
 `Get` 프로시저는 속성의 값을 검색 하 고 `Set` 프로시저는 값을 저장 합니다. 속성에 읽기/쓰기 액세스 권한을 지정 하려면 두 프로시저를 모두 정의 해야 합니다. 읽기 전용 속성의 경우 `Get`만 정의 하 고 쓰기 전용 속성의 경우에는 `Set`만 정의 합니다.  
  
### <a name="to-create-a-property"></a>속성을 만들려면  
  
1. 속성이 나 프로시저 외부에서 [속성 문과](../../../../visual-basic/language-reference/statements/property-statement.md)`End Property` 문을 차례로 사용 합니다.  
  
2. 속성이 매개 변수를 사용 하는 경우 `Property` 키워드를 프로시저 이름과 함께 괄호 안에 매개 변수 목록으로 추가 합니다.  
  
3. `As` 절을 사용 하 여 괄호를 따라 속성 값의 데이터 형식을 지정 합니다. 쓰기 전용 속성의 경우에도 데이터 형식을 지정 해야 합니다.  
  
4. `Get` 및 `Set` 절차를 적절 하 게 추가 합니다. 다음 지침을 참조 하세요.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>속성 값을 검색 하는 Get 프로시저를 만들려면  
  
1. `Property` 문과 `End Property` 문 사이에 [Get 문과](../../../../visual-basic/language-reference/statements/get-statement.md)`End Get` 문을 차례로 작성 합니다. `Get` 프로시저에 대 한 매개 변수를 정의할 필요가 없습니다.  
  
2. `Get` 문과 `End Get` 문 사이에 속성 값을 검색 하는 코드 문을 추가 합니다. 이 코드에는 속성 값을 생성 하 고 반환 하는 것 외에 다른 계산과 데이터 조작을 포함할 수 있습니다.  
  
3. `Return` 문을 사용 하 여 속성의 값을 호출 코드에 반환 합니다.  
  
 읽기/쓰기 속성 및 읽기 전용 속성에 대 한 `Get` 프로시저를 작성 해야 합니다. 쓰기 전용 속성에 대 한 `Get` 프로시저를 정의 하면 안 됩니다.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>속성 값을 쓰는 Set 프로시저를 만들려면  
  
1. `Property` 문과 `End Property` 문 사이에 [Set 문과](../../../../visual-basic/language-reference/statements/set-statement.md)`End Set` 문을 차례로 작성 합니다.  
  
2. `Set` 문에서 괄호 안의 매개 변수 목록을 사용 하 여 `Set` 키워드를 따릅니다. 이 매개 변수 목록은 호출 코드에서 전달 된 값에 대해 적어도 하나의 값 매개 변수를 포함 해야 합니다. 이 값 매개 변수에 대 한 기본 이름은 `Value`이지만 해당 하는 경우 다른 이름을 사용할 수 있습니다. 값 매개 변수는 속성 자체와 동일한 데이터 형식 이어야 합니다.  
  
3. `Set`와 `End Set` 문 사이에 속성에 값을 저장 하는 코드 문을 삽입 합니다. 이 코드에는 속성 값의 유효성을 검사 하 고 저장 하는 것 외에 다른 계산과 데이터 조작을 포함할 수 있습니다.  
  
4. 값 매개 변수를 사용 하 여 호출 코드에서 제공 하는 값을 적용 합니다. 이 값을 대입문에 직접 저장 하거나 식에 사용 하 여 저장할 내부 값을 계산할 수 있습니다.  
  
 읽기/쓰기 속성 및 쓰기 전용 속성에 대 한 `Set` 프로시저를 작성 해야 합니다. 읽기 전용 속성에 대 한 `Set` 프로시저를 정의 하면 안 됩니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 전체 이름을 두 개의 구성 이름, 이름 및 성으로 저장 하는 읽기/쓰기 속성을 만듭니다. 호출 코드가 `fullName`를 읽을 때 `Get` 프로시저는 두 가지 구성 이름을 결합 하 고 전체 이름을 반환 합니다. 호출 코드에서 새 전체 이름을 할당 하면 `Set` 프로시저는 두 개의 구성 된 이름으로 코드를 분리 하려고 시도 합니다. 공백을 찾지 못하면 모두 이름으로 저장 합니다.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 다음 예에서는 `fullName`의 속성 프로시저에 대 한 일반적인 호출을 보여 줍니다. 첫 번째 호출은 속성 값을 설정 하 고 두 번째 호출은이를 검색 합니다.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [속성 프로시저](./property-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)
- [방법: 액세스 수준이 혼합된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)
- [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)
- [방법: Visual Basic에서 기본 속성 선언 및 호출](./how-to-declare-and-call-a-default-property.md)
- [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)
- [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)
