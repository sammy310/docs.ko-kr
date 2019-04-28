---
title: 상수 개요(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 2939110de77718baf32e2a0d8f1aa52dba997cf3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907090"
---
# <a name="constants-overview-visual-basic"></a>상수 개요(Visual Basic)
상수는 숫자 또는 변경 되지 않는 문자열의 발생 하는 의미 있는 이름입니다. 상수 이름에서 알 수 있듯이 동일 하 게 유지에서 전체 응용 프로그램의 실행 하는 값을 저장 합니다. 크게 코드의 가독성을 향상 하 고 쉽게 상수를 사용 하 여 유지할 수 있습니다. 다시 나타나는 값을 포함 하는 코드에서 사용 하거나 기억 하거나 의미가 명확 하지 않은 어려운 특정 번호에 따라 달라 집니다.  
  
## <a name="how-to-create-and-use-constants"></a>만들기 및 상수를 사용 하는 방법  
 Visual Basic 인쇄 및 표시를 위해 주로 사용 하 여 다양 한 미리 정의 된 상수를 포함 합니다. 고유한 상수를 사용 하 여 만들 수도 있습니다는 `Const` 변수 이름을 만들 경우 동일한 지침을 사용 하 여 문입니다. 하는 경우 `Option Strict` 는 `On`, 상수 형식을 명시적으로 선언 해야 합니다.  
  
 해당 이름을 한정 하지 않고 변수를 참조할 수 있는 모든 코드 집합인 상수의 범위와 동일한 위치에 선언 된 변수는 같습니다. 특정 절차의 범위 내에 존재 하는 상수를 만들려면 해당 프로시저 내에서 선언 합니다. 응용 프로그램을 통해 사용할 수 있는 상수를 만들려면 사용 하 여 선언 된 `Public` 클래스의 선언 섹션에는 키워드입니다.  
  
> [!NOTE]
>  상수 변수를 다소 유사, 있지만 수정 하거나 하는 변수 새 값을 할당 수 없습니다.  
  
 컨트롤 또는 구성 요소를 사용 하 여 작업에 대 한 개체 모델에서 코드에 사용할 상수를 정의할 수 있습니다 또는 사용자 정의 될 수 있습니다 (즉, 해당 사용자가 직접 만든).  
  
## <a name="compile-time-and-run-time-constants"></a>컴파일 시간 및 런타임 상수  
 컴파일 시간 상수는 응용 프로그램이 실행 되는 동안에 런타임 상수를 계산할 수 있지만 코드를 컴파일할 때 계산 됩니다. 컴파일 시간 상수 런타임 상수 될 때마다 변경 될 수 있지만 응용 프로그램을 실행할 때마다 동일한 값을 갖게 됩니다. 컴파일 시간 상수는 열거자 이니셜라이저, 배열 및 case 식 등의 경우에 필요 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
|정의|용어|  
|---|---|  
|[방법: 상수 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|사용 하는 방법에 설명 합니다 `Const` 상수를 선언 하 고 해당 값을 설정 하는 문을 상수를 선언 하 여 값에 의미 있는 이름을 할당 합니다.|  
|[사용자 정의 상수](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|범위 지정에 대 한 정보를 포함 하 여 고유한 상수를 만드는 방법 및 순환 참조를 방지 하는 방법을 설명 합니다.|  
|[상수 및 리터럴 데이터 형식](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|Visual Basic 컴파일러 상수를 초기화 하는 방법에 대해 설명 하면 `Option Explicit` 해제 됩니다.|  
|[방법: 관련 상수 값 그룹화](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|관련 된 상수 값을 그룹화 하는 방법을 보여 줍니다.|  
  
## <a name="reference"></a>참조  
  
|정의|용어|  
|---|---|  
|[상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)|Visual Basic에서 미리 정의 된 상수를 나열 합니다.|  
|[Const 문](../../../../visual-basic/language-reference/statements/const-statement.md)|에 대해 설명 합니다 `Const` 문 및 사용 합니다.|  
|[Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|에 대해 설명 합니다 `Option Strict` 문 및 사용 합니다.|  
  
## <a name="see-also"></a>참고자료

- [열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [방법: Visual Basic에서 배열 변수 초기화](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
