---
title: Const 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 089c2dca99373f379e1eff319cf8c41242e5f135
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835312"
---
# <a name="const-statement-visual-basic"></a>Const 문(Visual Basic)
선언 하 고 하나 이상의 상수를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a>요소  
 `attributelist`  
 선택 사항입니다. 이 문에서 선언 된 모든 상수에 적용 되는 특성의 목록입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").  
  
 `accessmodifier`  
 선택 사항입니다. 이러한 상수에 액세스할 수 있는 코드를 지정 하려면이 사용 합니다. 수 [공용](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [개인](../../../visual-basic/language-reference/modifiers/private.md), 또는 [Private Protected](../../language-reference/modifiers/private-protected.md)합니다.
  
 `Shadows`  
 선택 사항입니다. 이 사용 하 여 다시 선언 하 고 기본 클래스의 프로그래밍 요소를 숨깁니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.  
  
 `constantlist`  
 필수 요소. 이 문에서 선언 되는 상수의 목록입니다.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 각 `constant`에는 다음과 같은 구문과 요소가 있습니다.  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|파트|설명|  
|----------|-----------------|  
|`constantname`|필수 요소. 상수의 이름입니다. [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.|  
|`datatype`|필요한 경우 `Option Strict` 는 `On`합니다. 데이터 형식 상수입니다.|  
|`initializer`|필수 요소. 컴파일 시 계산 되 고 상수에 할당 되는 식입니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램에서 변경 되지 않는 값을 해야 하는 경우에 명명 된 상수를 정의할 수 있으며 리터럴 값 대신 사용할 수 있습니다. 이름 값에 비해 기억 하기 쉽습니다. 상수를 한 번만 정의 하 고 코드에서이 여러 위치에서 사용할 수 있습니다. 이후 버전에서는 값을 재정의 해야 하는 경우는 `Const` 문을 변경 해야 할 유일한 위치입니다.  
  
 사용할 수 있습니다 `Const` 모듈 또는 프로시저 수준 에서만. 즉, 합니다 *선언 컨텍스트* 변수에 클래스, 구조체, 모듈, 프로시저 또는 블록 이어야 하며 원본 파일, 네임 스페이스 또는 인터페이스 수는 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 공용 액세스를 기본 프로시저의 경우) (내의 로컬 상수에 액세스 한정자를 사용할 수 없습니다. 클래스와 모듈 멤버 (외부 프로시저) 상수 기본적으로 개인 액세스 및 구조체 멤버 상수는 기본적으로 공용 액세스 합니다. 액세스 한정자를 사용 하 여 해당 액세스 수준을 조정할 수 있습니다.  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** 모든 프로시저 외부 모듈 수준에서 선언 된 상수는 *멤버 상수*, 클래스, 구조체의 멤버인 또는 선언 하는 모듈입니다.  
  
     프로시저 수준에서 선언 된 상수는를 *지역 상수*; 프로시저 또는 블록을 선언한 로컬 것입니다.  
  
-   **특성입니다.** 지역 상수 아니라 멤버 상수에만 특성을 적용할 수 있습니다. 특성 지역 상수와 같은 임시 저장소에 의미가 없는 어셈블리의 메타 데이터에 대 한 정보를 제공 합니다.  
  
-   **한정자입니다.** 기본적으로 모든 상수는 `Shared`하십시오 `Static`, 및 `ReadOnly`합니다. 상수를 선언 하는 경우 이러한 키워드를 사용할 수 없습니다.  
  
     프로시저 수준에서 사용할 수 없습니다 `Shadows` 또는 액세스 한정자를 지역 상수 선언 합니다.  
  
-   **여러 상수입니다.** 동일한 선언문에서 여러 개의 상수를 선언할 수 있습니다 지정 하는 `constantname` 각각에 대 한 부분입니다. 여러 상수는 쉼표로 구분 됩니다.  
  
## <a name="data-type-rules"></a>데이터 형식 규칙  
  
-   **데이터 형식입니다.** `Const` 문은 데이터 형식의 변수를 선언할 수 있습니다. 모든 데이터 형식이 나 열거형의 이름을 지정할 수 있습니다.  
  
-   **기본 형식입니다.** 지정 하지 않는 경우 `datatype`, 상수는 데이터 형식의 `initializer`합니다. 둘 다 지정 하는 경우 `datatype` 하 고 `initializer`, 데이터 형식 `initializer` 변환할 수 있어야 합니다 `datatype`합니다. 모두 `datatype` 나 `initializer` 가 있는 경우 데이터 형식이 기본값으로 `Object`합니다.  
  
-   **다른 형식입니다.** 별도 사용 하 여 서로 다른 데이터 형식이 서로 다른 상수를 지정할 수 있습니다 `As` 선언 하는 각 변수에 대 한 절. 그러나 일반적인 사용 하 여 동일한 형식으로 여러 상수를 선언할 수 없습니다 `As` 절.  
  
-   **초기화 합니다.** 모든 상수 값을 초기화 해야 `constantlist`합니다. 사용할 `initializer` 상수에 할당할 식을 제공 합니다. 식에는 리터럴, 이미 정의 되어 있는 다른 상수 및 이미 정의 된 열거형 멤버의 조합일 수 있습니다. 이러한 요소를 결합 하 여 산술 및 논리 연산자를 사용할 수 있습니다.  
  
     변수 또는 함수에서 사용할 수 없습니다 `initializer`합니다. 와 같은 변환 키워드를 사용할 수는 있지만 `CByte` 고 `CShort`입니다. 사용할 수도 있습니다 `AscW` 상수를 사용 하 여 호출 하는 경우 `String` 또는 `Char` 인수를 컴파일 타임에 평가할 수 있는 때문입니다.  
  
## <a name="behavior"></a>동작  
  
-   **범위입니다.** 지역 상수는 해당 프로시저 또는 블록 내 에서만 액세스할 수 있습니다. 상수 멤버는 클래스, 구조체 또는 모듈 내의 모든 위치에서 액세스할 수 있습니다.  
  
-   **정규화 합니다.** 코드 클래스 이외에 구조체 또는 모듈 이름을 한 정해야 멤버 상수의 해당 클래스, 구조체 또는 모듈의 이름입니다. 코드 외부 프로시저 또는 블록을 해당 프로시저 또는 블록 내에 있는 로컬 상수를 참조할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Const` 문을 리터럴 값 대신 사용 하 여 상수를 선언 합니다.  
  
 [!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]  
  
## <a name="example"></a>예제  
 데이터 형식을 사용 하 여 상수를 정의 하는 경우 `Object`, Visual Basic 컴파일러의 형식을 제공 `initializer`를 대신 `Object`합니다. 다음 예제에서는 상수 `naturalLogBase` 런타임 형식이 `Decimal`합니다.  
  
 [!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]  
  
 앞의 예제에서는 <xref:System.Type.ToString%2A> 메서드를 <xref:System.Type> 에서 반환 된 개체를 [GetType 연산자](../../../visual-basic/language-reference/operators/gettype-operator.md)이므로 <xref:System.Type> 변환할 수 없습니다 `String` 를 사용 하 여 `CStr`합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)
- [#Const 지시문](../../../visual-basic/language-reference/directives/const-directive.md)
- [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)
- [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md)
- [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [상수 및 열거형](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [상수 및 열거형](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
