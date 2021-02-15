---
description: '자세한 정보: 프로시저 매개 변수 및 인수 (Visual Basic)'
title: 프로시저 매개 변수 및 인수
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: c2239c76450f503e74dbf5f191cd212e05d11600
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100423162"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a>프로시저 매개 변수 및 인수(Visual Basic)

대부분의 경우 프로시저에는 호출 된 상황에 대 한 일부 정보가 필요 합니다. 반복 되거나 공유 된 작업을 수행 하는 프로시저는 각 호출에 대해 서로 다른 정보를 사용 합니다. 이 정보는 프로시저를 호출할 때 프로시저에 전달 하는 변수, 상수 및 식으로 구성 됩니다.  
  
 *매개 변수* 는 프로시저에서 호출할 때 제공할 것으로 예상 하는 값을 나타냅니다. 프로시저의 선언에서 매개 변수를 정의 합니다.  
  
 매개 변수 없이 프로시저를 정의 하거나, 매개 변수를 하나 이상 정의할 수 있습니다. 매개 변수를 지정 하는 프로시저 정의의 일부를 *매개 변수 목록* 이라고 합니다.  
  
 *인수* 는 프로시저를 호출할 때 프로시저 매개 변수에 제공 하는 값을 나타냅니다. 호출 코드는 프로시저를 호출할 때 인수를 제공 합니다. 인수를 지정 하는 프로시저 호출의 일부를 *인수 목록* 이라고 합니다.  
  
 다음 그림에서는 `safeSquareRoot` 서로 다른 두 위치에서 프로시저를 호출 하는 코드를 보여 줍니다. 첫 번째 호출은 변수 값 `x` (4.0)을 매개 변수에 전달 `number` 하 고 `root` (2.0)의 반환 값이 변수에 할당 됩니다 `y` . 두 번째 호출은 리터럴 값 9.0를에 전달 하 `number` 고 반환 값 (3.0)을 변수에 할당 합니다 `z` .  
  
 ![매개 변수에 인수를 전달 하는 방법을 보여 주는 다이어그램](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 자세한 내용은 [매개 변수와 인수 간의 차이점](./differences-between-parameters-and-arguments.md)을 참조 하세요.  
  
## <a name="parameter-data-type"></a>매개 변수 데이터 형식  

 선언에서 절을 사용 하 여 매개 변수의 데이터 형식을 정의 `As` 합니다. 예를 들어 다음 함수는 문자열과 정수를 허용 합니다.  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 형식 검사 스위치 ([Option Strict 문](../../../language-reference/statements/option-strict-statement.md))가 절 인 경우에는 모든 매개 변수가 사용 하는 경우를 제외 하 고는 `Off,` `As` 선택 사항입니다. 형식 검사가 인 경우 `On` `As` 모든 프로시저 매개 변수에 절이 필요 합니다.  
  
 호출 코드에서 매개 변수와 같이 해당 매개 변수와 다른 데이터 형식의 인수를 제공할 것으로 예상 하는 경우 다음 중 `Byte` 하나를 `String` 수행 해야 합니다.  
  
- 매개 변수 데이터 형식으로 확장 되는 데이터 형식의 인수만 제공 합니다.  
  
- `Option Strict Off`암시적 축소 변환을 허용 하도록 설정 합니다. 또는  
  
- 변환 키워드를 사용 하 여 데이터 형식을 명시적으로 변환 합니다.  
  
### <a name="type-parameters"></a>형식 매개 변수  

 *제네릭 프로시저* 는 일반 매개 변수 외에도 하나 이상의 *형식 매개 변수도* 정의 합니다. 제네릭 프로시저를 사용 하면 호출 코드가 프로시저를 호출할 때마다 서로 다른 데이터 형식을 전달할 수 있으므로 각 개별 호출의 요구 사항에 맞게 데이터 형식을 조정할 수 있습니다. [Generic Procedures in Visual Basic](../data-types/generic-procedures.md)을 참조하세요.  
  
## <a name="see-also"></a>추가 정보

- [절차](./index.md)
- [하위 프로시저](./sub-procedures.md)
- [함수 프로시저](./function-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [방법: 프로시저의 매개 변수 정의](./how-to-define-a-parameter-for-a-procedure.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [Visual Basic의 형식 변환](../data-types/type-conversions.md)
