---
description: '자세히 알아보기: 오버 로드 된 속성 및 메서드 (Visual Basic)'
title: 오버 로드 된 속성 및 메서드
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: fb46876d346ad5f391241aee0b07175df290e656
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100438777"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>오버 로드 된 속성 및 메서드 (Visual Basic)

오버 로드는 이름이 같지만 인수 형식이 다른 클래스에서 둘 이상의 프로시저, 인스턴스 생성자 또는 속성을 만드는 것입니다.

## <a name="overloading-usage"></a>사용 오버 로드

오버 로드는 개체 모델에서 서로 다른 데이터 형식에 대해 작동 하는 프로시저에 동일한 이름을 사용 하는 경우 특히 유용 합니다. 예를 들어 여러 다른 데이터 형식을 표시할 수 있는 클래스에는 `Display` 다음과 같은 프로시저가 있을 수 있습니다.

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

오버 로드를 사용 하지 않는 경우 다음에 표시 된 것 처럼 동일한 작업을 수행 하는 경우에도 각 프로시저에 대해 고유한 이름을 만들어야 합니다.

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

오버 로드를 사용 하면 사용할 수 있는 데이터 형식을 선택할 수 있기 때문에 속성 또는 메서드를 보다 쉽게 사용할 수 있습니다. 예를 들어 앞에서 설명한 오버 로드 된 `Display` 메서드는 다음 코드 줄을 사용 하 여 호출할 수 있습니다.

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

런타임에는 사용자가 지정 하는 매개 변수의 데이터 형식에 따라 올바른 프로시저를 호출 Visual Basic 합니다.

## <a name="overloading-rules"></a>오버 로드 규칙

 동일한 이름을 가진 둘 이상의 속성 또는 메서드를 추가 하 여 클래스에 대해 오버 로드 된 멤버를 만듭니다. 오버 로드 된 파생 멤버를 제외 하 고, 각 오버 로드 된 멤버는 서로 다른 매개 변수 목록을 포함 해야 하며, 다음 항목은 속성이 나 프로시저를 오버 로드할 때 차별화 기능으로 사용할 수 없습니다.

- `ByVal` `ByRef` 멤버에 적용 되는 또는와 같은 한정자 또는 멤버의 매개 변수입니다.

- 매개 변수 이름

- 프로시저의 반환 형식

`Overloads`오버 로드 하는 경우 키워드는 선택 사항 이지만 오버 로드 된 멤버에 키워드를 사용 하는 경우에는 `Overloads` 이름이 같은 오버 로드 된 다른 모든 멤버도이 키워드를 지정 해야 합니다.

파생 된 클래스는 동일한 매개 변수 및 매개 변수 형식이 있는 멤버로 상속 된 멤버를 오버 로드할 수 있습니다 .이 프로세스는 *이름 및 시그니처로 섀도잉* 이라고 합니다. `Overloads`이름 및 시그니처로 숨길 때 키워드를 사용 하는 경우 기본 클래스의 구현 대신 파생 클래스의 멤버 구현이 사용 되며, 해당 멤버에 대 한 다른 모든 오버 로드는 파생 클래스의 인스턴스에서 사용할 수 있습니다.

`Overloads`동일한 매개 변수 및 매개 변수 형식을 가진 멤버를 사용 하 여 상속 된 멤버를 오버 로드할 때 키워드를 생략 하면 *이름으로 숨김과* 오버 로드를 호출 합니다. 이름으로 숨김은 멤버의 상속 된 구현을 대체 하 고 파생 클래스의 인스턴스와 다른 모든 오버 로드를 사용할 수 없게 만듭니다.

`Overloads`및 `Shadows` 한정자는 동일한 속성 또는 메서드와 함께 사용할 수 없습니다.

### <a name="example"></a>예

다음 예에서는 `String` `Decimal` 달러 금액의 또는 표현을 허용 하 고 판매 세금을 포함 하는 문자열을 반환 하는 오버 로드 된 메서드를 만듭니다.

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>이 예제를 사용 하 여 오버 로드 된 메서드를 만들려면

1. 새 프로젝트를 열고 라는 클래스를 추가 `TaxClass` 합니다.

2. `TaxClass` 클래스에 다음 코드를 추가합니다.

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. 다음 프로시저를 폼에 추가 합니다.

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. 폼에 단추를 추가 하 고 `ShowTax` 단추의 이벤트에서 프로시저를 호출 합니다 `Button1_Click` .

5. 프로젝트를 실행 하 고 폼의 단추를 클릭 하 여 오버 로드 된 프로시저를 테스트 합니다 `ShowTax` .

런타임에는 컴파일러에서 사용 되는 매개 변수와 일치 하는 오버 로드 된 적절 한 함수를 선택 합니다. 단추를 클릭 하면 오버 로드 된 메서드는 `Price` 문자열 및 메시지 "Price가 문자열인 매개 변수를 사용 하 여 먼저 호출 됩니다. 세금은 $5.12이 표시 됩니다. `TaxAmount` 는 두 번째 시간 값을 사용 하 여 호출 되 `Decimal` 고 메시지 "Price는 10 진수입니다. 세금은 $5.12이 표시 됩니다.

## <a name="see-also"></a>추가 정보

- [개체 및 클래스](index.md)
- [Visual Basic에서 숨김](../declared-elements/shadowing.md)
- [Sub 문](../../../language-reference/statements/sub-statement.md)
- [상속 기본 사항](inheritance-basics.md)
- [Overloads](../../../language-reference/modifiers/shadows.md)
- [ByVal](../../../language-reference/modifiers/byval.md)
- [ByRef](../../../language-reference/modifiers/byref.md)
- [오버로드](../../../language-reference/modifiers/overloads.md)
- [Overloads](../../../language-reference/modifiers/shadows.md)
