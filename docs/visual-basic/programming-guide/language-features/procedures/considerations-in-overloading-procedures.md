---
title: 프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: bd5b0032ca63ccb2f2cc30d72a5b3f3c7eb3c346
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775733"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)
프로시저를 오버 로드 하는 경우 오버 로드 된 각 버전에 대해 다른 *서명을* 사용 해야 합니다. 이는 일반적으로 각 버전이 서로 다른 매개 변수 목록을 지정 해야 함을 의미 합니다. 자세한 내용은 [프로시저 오버 로드](./procedure-overloading.md)에서 "다른 서명"을 참조 하세요.  
  
 @No__t_1 프로시저를 사용 하 여 `Function` 프로시저를 오버 로드할 수 있으며, 다른 시그니처가 있는 경우 그 반대의 경우도 마찬가지입니다. 두 오버 로드는 반환 값을 가지 며 다른 오버 로드는 그렇지 않습니다.  
  
 프로시저를 오버 로드 하는 것과 동일한 방식으로 속성을 오버 로드 하 여 동일한 제한 사항을 적용할 수 있습니다. 그러나 속성을 사용 하 여 프로시저를 오버 로드할 수 없으며 그 반대의 경우도 마찬가지입니다.  
  
## <a name="alternatives-to-overloaded-versions"></a>오버 로드 된 버전의 대안  
 경우에 따라 오버 로드 된 버전에 대 한 대안이 있을 수 있습니다. 특히 인수 유무는 선택 사항이 나 변수의 숫자가 가변적 일 때입니다.  
  
 선택적 인수는 모든 언어에서 반드시 지원 되는 것은 아니며 매개 변수 배열은 Visual Basic로 제한 됩니다. 여러 다른 언어로 작성 된 코드에서 호출 될 수 있는 프로시저를 작성 하는 경우 오버 로드 된 버전이 가장 큰 유연성을 제공 합니다.  
  
### <a name="overloads-and-optional-arguments"></a>오버 로드 및 선택적 인수  
 호출 코드에서 하나 이상의 인수를 선택적으로 제공 하거나 생략할 수 있는 경우 여러 오버 로드 된 버전을 정의 하거나 선택적 매개 변수를 사용할 수 있습니다.  
  
#### <a name="when-to-use-overloaded-versions"></a>오버 로드 된 버전을 사용 하는 경우  
 다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 하는 것을 고려할 수 있습니다.  
  
- 프로시저 코드의 논리는 호출 코드에서 선택적 인수를 제공 하는지 여부에 따라 크게 다릅니다.  
  
- 프로시저 코드는 호출 코드에서 선택적 인수를 제공 했는지 여부를 안정적으로 테스트할 수 없습니다. 예를 들어, 호출 코드에서 제공 하지 않을 수 있는 기본 값에 대해 가능한 후보가 없는 경우이 오류가 발생 합니다.  
  
#### <a name="when-to-use-optional-parameters"></a>선택적 매개 변수를 사용 하는 경우  
 다음과 같은 경우 하나 이상의 선택적 매개 변수를 사용 하는 것이 좋습니다.  
  
- 호출 하는 코드에서 선택적 인수를 제공 하지 않는 경우에만 필요한 작업은 매개 변수를 기본값으로 설정 하는 것입니다. 이 경우 하나 이상의 `Optional` 매개 변수를 사용 하 여 단일 버전을 정의 하는 경우 프로시저 코드가 더 복잡할 수 있습니다.  
  
 자세한 내용은 [선택적 매개 변수](./optional-parameters.md)를 참조 하세요.  
  
### <a name="overloads-and-paramarrays"></a>오버 로드 및 ParamArrays  
 호출 코드에서 다양 한 수의 인수를 전달할 수 있는 경우 여러 오버 로드 된 버전을 정의 하거나 매개 변수 배열을 사용할 수 있습니다.  
  
#### <a name="when-to-use-overloaded-versions"></a>오버 로드 된 버전을 사용 하는 경우  
 다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 하는 것을 고려할 수 있습니다.  
  
- 호출 코드가 매개 변수 배열에 적은 수의 값을 더 이상 전달 하지 않는다는 것을 알고 있습니다.  
  
- 프로시저 코드의 논리는 호출 코드가 전달 하는 값의 수에 따라 크게 다릅니다.  
  
- 호출 하는 코드는 서로 다른 데이터 형식의 값을 전달할 수 있습니다.  
  
#### <a name="when-to-use-a-parameter-array"></a>매개 변수 배열을 사용 하는 경우  
 다음과 같은 경우에는 `ParamArray` 매개 변수를 통해 더 효율적으로 처리할 수 있습니다.  
  
- 호출 코드가 매개 변수 배열에 전달할 수 있는 값의 수를 예측할 수 없으며 숫자가 클 수 있습니다.  
  
- 프로시저 논리는 호출 코드가 전달 하는 모든 값을 반복 하 여 기본적으로 모든 값에 대해 동일한 작업을 수행 하는 데 적합 합니다.  
  
 자세한 내용은 [매개 변수 배열](./parameter-arrays.md)을 참조 하세요.  
  
## <a name="implicit-overloads-for-optional-parameters"></a>선택적 매개 변수에 대 한 암시적 오버 로드  
 [선택적](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수를 사용 하는 프로시저는 두 개의 오버 로드 된 프로시저와 동일 합니다. 하나는 선택적 매개 변수를 포함 하 고 하나는 포함 하지 않습니다. 이러한 프로시저 중 하나에 해당 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다. 다음 선언에서는이를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 선택적 매개 변수를 두 개 이상 사용 하는 프로시저의 경우 앞의 예제와 비슷한 논리를 통해 도착 하는 암시적 오버 로드 집합이 있습니다.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>ParamArray 매개 변수에 대 한 암시적 오버 로드  
 컴파일러는 다음과 같이 호출 코드가 매개 변수 배열에 전달 하는 것과는 다른 [매개 변수를](../../../../visual-basic/language-reference/modifiers/paramarray.md) 사용 하 여 오버 로드 수를 무한대로 간주 합니다.  
  
- 호출 코드가 `ParamArray`에 인수를 제공 하지 않는 경우에 대 한 오버 로드  
  
- 호출 코드가 `ParamArray` 요소 형식의 1 차원 배열을 제공할 때의 오버 로드 하나  
  
- 모든 양의 정수에 대해 호출 코드에서 해당 개수의 인수를 제공 하는 경우에 대 한 오버 로드 하나는 각 `ParamArray` 요소 형식입니다.  
  
 다음 선언에서는 이러한 암시적 오버 로드를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 매개 변수 배열에 1 차원 배열을 사용 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다. 그러나 다른 암시적 오버 로드의 시그니처를 사용할 수 있습니다. 다음 선언에서는이를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>오버 로드에 대 한 대 안으로 형식이 없는 프로그래밍  
 호출 코드가 다른 데이터 형식을 매개 변수에 전달할 수 있게 하려는 경우 다른 방법으로는 형식이 없는 프로그래밍이 있습니다. [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 또는 [-옵션 strict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 사용 하 여 형식 확인 스위치를 `Off`로 설정할 수 있습니다. 그런 다음 매개 변수의 데이터 형식을 선언할 필요가 없습니다. 그러나이 방법은 오버 로드에 비해 다음과 같은 단점이 있습니다.  
  
- 형식이 없는 프로그래밍은 효율성이 떨어지는 실행 코드를 생성 합니다.  
  
- 프로시저는 전달 될 것으로 예상 되는 모든 데이터 형식에 대해 테스트 해야 합니다.  
  
- 호출 하는 코드가 프로시저에서 지원 하지 않는 데이터 형식을 전달 하는 경우 컴파일러에서 오류를 알릴 수 없습니다.  
  
## <a name="see-also"></a>참조

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [프로시저 문제 해결](./troubleshooting-procedures.md)
- [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)
- [방법: 오버로드된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)
- [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [오버로드 확인](./overload-resolution.md)
- [오버로드](../../../../visual-basic/language-reference/modifiers/overloads.md)
