---
title: '방법: 상수 선언'
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: 138dd58dac9d1983e35e61f8b98a77810fc6e38b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058848"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>방법: 상수 선언(Visual Basic)

문을 사용 하 여 `Const` 상수를 선언 하 고 해당 값을 설정 합니다. 상수를 선언 하 여 값에 의미 있는 이름을 할당 합니다. 상수를 선언한 후에는 수정 하거나 새 값을 할당할 수 없습니다.  
  
 프로시저 내에서 상수를 선언 하거나 모듈, 클래스 또는 구조체의 선언 섹션에서 상수를 선언 합니다. 클래스 또는 구조체 수준 상수는 `Private` 기본적으로 이지만 `Public` 적절 한 `Friend` `Protected` `Protected Friend` 수준의 코드 액세스에 대해,, 또는로 선언할 수도 있습니다.  
  
 상수에는 유효한 기호화 된 이름 (규칙은 변수 이름을 만드는 데 사용할 수 있는 이름)과 숫자 또는 문자열 상수와 연산자로 구성 된 식 (함수 호출은 제외)이 있어야 합니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>상수를 선언 하려면  
  
- `Const`다음 예제와 같이 액세스 지정자, 키워드 및 식을 포함 하는 선언을 작성 합니다.  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     [Option 유추](../../../language-reference/statements/option-infer-statement.md) 는이 `Off` 고 [option Strict](../../../language-reference/statements/option-strict-statement.md) 가 이면 데이터 형식 (,,,,,,,,, `On` `Boolean` `Byte` `Char` `DateTime` `Decimal` `Double` `Integer` `Long` `Short` `Single` 또는 `String` )을 지정 하 여 상수를 명시적으로 선언 해야 합니다.  
  
     `Option Infer`가 `On` 이거나 `Option Strict` 가 인 경우 `Off` 절을 사용 하 여 데이터 형식을 지정 하지 않고 상수를 선언할 수 있습니다 `As` . 컴파일러는 식의 형식에서 상수의 형식을 결정 합니다. 자세한 내용은 [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md)을 참조 하세요.  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>명시적으로 언급 된 데이터 형식이 있는 상수를 선언 하려면  
  
- `As`다음 예제와 같이 키워드 및 명시적 데이터 형식을 포함 하는 선언을 작성 합니다.  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     한 줄에 하나의 상수만 선언 하는 경우 코드를 더 쉽게 읽을 수 있지만 단일 줄에 여러 상수를 선언할 수 있습니다. 단일 줄에 여러 상수를 선언 하는 경우 모두 동일한 액세스 수준 ( `Public` , `Private` ,, `Friend` `Protected` 또는 `Protected Friend` )을 가져야 합니다.  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>한 줄에 여러 상수를 선언 하려면  
  
- 다음 예제와 같이 선언을 쉼표와 공백으로 구분 합니다.  
  
    ```vb  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>참조

- [Const 문](../../../language-reference/statements/const-statement.md)
- [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md)
- [상수 개요](constants-overview.md)
- [방법: 상수 선언](how-to-declare-a-constant.md)
- [사용자 정의 상수](user-defined-constants.md)
- [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md)
- [방법: 관련 상수 값 그룹화](how-to-group-related-constant-values-together.md)
- [열거형 개요](enumerations-overview.md)
- [방법: 열거형 선언](how-to-declare-enumerations.md)
- [방법: 열거형 멤버 참조](how-to-refer-to-an-enumeration-member.md)
- [열거형 및 이름 한정](enumerations-and-name-qualification.md)
- [방법: 열거형 반복](how-to-iterate-through-an-enumeration.md)
- [방법: 열거형 값과 연결된 문자열 확인](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [열거형을 사용하는 경우](when-to-use-an-enumeration.md)

- [열거형 개요](enumerations-overview.md)
- [상수 개요](constants-overview.md)
- [방법: 열거형 선언](how-to-declare-enumerations.md)
- [열거형 및 이름 한정](enumerations-and-name-qualification.md)
- [Option Strict 문](../../../language-reference/statements/option-strict-statement.md)
- [상수 및 열거형](../../../language-reference/constants-and-enumerations.md)
