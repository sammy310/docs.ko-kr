---
title: 매개 변수와 인수의 차이점
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: dd0a62b6567f3e74763b7f2e9b96803c193c7976
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403358"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>매개 변수와 인수의 차이점(Visual Basic)
대부분의 경우 프로시저에는 호출 된 상황에 대 한 정보가 있어야 합니다. 반복 되거나 공유 된 작업을 수행 하는 프로시저는 각 호출에 대해 서로 다른 정보를 사용 합니다. 이 정보는 프로시저를 호출할 때 프로시저에 전달 하는 변수, 상수 및 식으로 구성 됩니다.  
  
 프로시저에이 정보를 전달 하기 위해 프로시저는 *매개 변수*를 정의 하 고 호출 하는 코드는 *인수* 를 해당 매개 변수에 전달 합니다. 매개 변수를 파킹 공간으로, 인수를 자동차로 간주할 수 있습니다. 서로 다른 시간에 서로 다른 자동차이 주차 공간을 파킹 할 수 있는 것 처럼 호출 코드는 프로시저를 호출할 때마다 동일한 매개 변수에 다른 인수를 전달할 수 있습니다.  
  
## <a name="parameters"></a>매개 변수  
 *매개 변수* 는 프로시저에서 호출할 때 전달할 것으로 예상 하는 값을 나타냅니다. 프로시저의 선언에서 매개 변수를 정의 합니다.  
  
 또는 프로시저를 정의할 `Function` 때는 `Sub` 프로시저 이름 바로 뒤에 괄호 안에 *매개 변수 목록을* 지정 합니다. 각 매개 변수에 대해 이름, 데이터 형식 및 전달 메커니즘 ([ByVal](../../../language-reference/modifiers/byval.md) 또는 [ByRef](../../../language-reference/modifiers/byref.md))을 지정 합니다. 매개 변수가 선택적 임을 나타낼 수도 있습니다. 즉, 호출 하는 코드에서 값을 전달할 필요가 없습니다.  
  
 각 매개 변수의 이름은 프로시저에서 *지역 변수로* 사용 됩니다. 다른 변수를 사용 하는 것과 동일한 방식으로 매개 변수 이름을 사용 합니다.  
  
## <a name="arguments"></a>인수  
 *인수* 는 프로시저를 호출할 때 프로시저 매개 변수에 전달 하는 값을 나타냅니다. 호출 코드는 프로시저를 호출할 때 인수를 제공 합니다.  
  
 또는 프로시저를 호출 하는 경우 `Function` `Sub` 프로시저 이름 바로 뒤에 괄호 안에 *인수 목록을* 포함 합니다. 각 인수는 목록에서 같은 위치에 있는 매개 변수에 해당 합니다.  
  
 매개 변수 정의와 달리 인수에는 이름이 없습니다. 각 인수는 0 개 이상의 변수, 상수 및 리터럴을 포함할 수 있는 식입니다. 계산 된 식의 데이터 형식은 일반적으로 해당 매개 변수에 대해 정의 된 데이터 형식과 일치 해야 하며, 모든 경우에 매개 변수 형식으로 변환할 수 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [하위 프로시저](./sub-procedures.md)
- [함수 프로시저](./function-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [방법: 프로시저의 매개 변수 정의](./how-to-define-a-parameter-for-a-procedure.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [재귀 프로시저](./recursive-procedures.md)
- [프로시저 오버로딩](./procedure-overloading.md)
