---
title: '방법: 선택적 매개 변수를 사용하는 프로시저 오버로드'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 4d31980e4b968cff274091ba4f307dffddab1100
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350858"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>방법: 선택적 매개 변수를 사용하는 프로시저 오버로드(Visual Basic)
프로시저에 하나 이상의 [선택적](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수가 있는 경우 해당 암시적 오버 로드와 일치 하는 오버 로드 된 버전을 정의할 수 없습니다. 자세한 내용은 [오버 로드 절차의 고려 사항](./considerations-in-overloading-procedures.md)에서 "선택적 매개 변수에 대 한 암시적 오버 로드"를 참조 하십시오.  
  
## <a name="one-optional-parameter"></a>하나의 선택적 매개 변수  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>선택적 매개 변수 하나를 사용 하는 프로시저를 오버 로드 하려면  
  
1. 매개 변수 목록에 선택적 매개 변수를 포함 하는 `Sub` 또는 `Function` 선언문을 작성 합니다. 이 오버 로드 된 버전에는 `Optional` 키워드를 사용 하지 마십시오.  
  
2. `Sub` 또는 `Function` 키워드 앞에 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 사용 합니다.  
  
3. 호출 코드에서 선택적 인수를 제공할 때 실행 되어야 하는 프로시저 코드를 작성 합니다.  
  
4. `End Sub` 또는 `End Function` 문을 사용 하 여 프로시저를 적절 하 게 종료 합니다.  
  
5. 매개 변수 목록에 선택적 매개 변수를 포함 하지 않는 경우를 제외 하 고 첫 번째 선언과 동일한 두 번째 선언문을 작성 합니다.  
  
6. 호출 코드에서 선택적 인수를 제공 하지 않는 경우 실행 되는 프로시저 코드를 작성 합니다. `End Sub` 또는 `End Function` 문을 사용 하 여 프로시저를 적절 하 게 종료 합니다.  
  
     다음 예에서는 선택적 매개 변수를 사용 하 여 정의 된 프로시저, 두 오버 로드 된 프로시저의 동등한 집합 및 유효 하지 않은 오버 로드 된 버전의 마지막 예제를 보여 줍니다.  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a>여러 선택적 매개 변수  
 둘 이상의 선택적 매개 변수가 있는 프로시저의 경우 일반적으로 두 개 이상의 오버 로드 된 버전이 필요 합니다. 예를 들어 두 개의 선택적 매개 변수가 있고 호출 코드에서 서로 독립적으로 각 매개 변수를 제공 하거나 생략할 수 있는 경우 제공 된 인수의 가능한 각 조합에 대해 하나씩 4 개의 오버 로드 된 버전이 필요 합니다.  
  
 선택적 매개 변수 수가 늘어나면 오버 로드의 복잡성이 증가 합니다. 제공 된 인수의 일부 조합이 허용 되지 않는 한, N 개의 선택적 매개 변수에는 2 ^ N 개의 오버 로드 된 버전이 필요 합니다. 프로시저의 특성에 따라 논리의 명확성은 오버 로드 된 모든 버전을 정의 하는 추가 작업을 정렬 하는 것을 알 수 있습니다.  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>둘 이상의 선택적 매개 변수를 사용 하는 프로시저를 오버 로드 하려면  
  
1. 제공 된 선택적 인수의 조합을 프로시저 논리에 허용 되는지 확인 합니다. 하나의 선택적 매개 변수가 다른 매개 변수에 종속 되는 경우 허용 되지 않는 조합이 발생할 수 있습니다. 예를 들어 한 매개 변수가 개인의 이름을 허용 하 고 다른 매개 변수가 해당 사용자의 연령를 수락 하는 경우 나이를 제공 하지만 이름을 생략 하는 인수를 조합 하 여 사용할 수 없습니다.  
  
2. 제공 된 선택적 인수의 허용 가능한 각 조합에 대해 해당 매개 변수 목록을 정의 하는 `Sub` 또는 `Function` 선언문을 작성 합니다. `Optional` 키워드를 사용 하지 마십시오.  
  
3. 각 선언에서 `Sub` 또는 `Function` 키워드 앞에 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 사용 합니다.  
  
4. 각 선언 후에 호출 코드에서 해당 선언의 매개 변수 목록에 해당 하는 인수 목록을 제공할 때 실행 해야 하는 프로시저 코드를 작성 합니다.  
  
5. `End Sub` 또는 `End Function` 문을 사용 하 여 각 프로시저를 적절 하 게 종료 합니다.  
  
## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [선택적 매개 변수](./optional-parameters.md)
- [매개 변수 배열](./parameter-arrays.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [프로시저 문제 해결](./troubleshooting-procedures.md)
- [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)
- [방법: 오버로드된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)
- [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [오버로드 확인](./overload-resolution.md)
