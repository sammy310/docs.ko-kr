---
title: 오버로드 확인
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: 0e69136b1e3015055cad9852bf04151f57558b88
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352642"
---
# <a name="overload-resolution-visual-basic"></a>오버로드 확인(Visual Basic)
Visual Basic 컴파일러가 여러 오버 로드 된 버전에 정의 된 프로시저에 대 한 호출을 발견할 경우 컴파일러는 호출할 오버 로드를 결정 해야 합니다. 이렇게 하려면 다음 단계를 수행 합니다.  
  
1. **접근성.** 호출 코드에서 호출할 수 없도록 하는 액세스 수준으로 오버 로드를 제거 합니다.  
  
2. **매개 변수 수입니다.** 호출에 제공 되는 것과 다른 개수의 매개 변수를 정의 하는 오버 로드를 제거 합니다.  
  
3. **매개 변수 데이터 형식입니다.** 컴파일러는 확장 메서드에 대 한 인스턴스 메서드 기본 설정을 제공 합니다. 프로시저 호출과 일치 하기 위해 확대 변환만 수행 해야 하는 인스턴스 메서드가 있는 경우 모든 확장 메서드가 삭제 되 고 컴파일러는 인스턴스 메서드 후보로만 계속 됩니다. 이러한 인스턴스 메서드를 찾을 수 없으면 인스턴스와 확장 메서드를 모두 사용 하 여 계속 합니다.  
  
     이 단계에서는 호출 인수의 데이터 형식을 오버 로드에 정의 된 매개 변수 형식으로 변환할 수 없는 오버 로드를 모두 제거 합니다.  
  
4. **축소 변환.** 호출 하는 인수 형식에서 정의 된 매개 변수 형식으로 축소 변환 해야 하는 오버 로드를 제거 합니다. 이는 형식 검사 스위치 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))가 `On` 또는 `Off`인지 여부에 해당 합니다.  
  
5. **최소 확대.** 컴파일러는 나머지 오버 로드를 쌍으로 간주 합니다. 각 쌍에 대해 정의 된 매개 변수의 데이터 형식을 비교 합니다. 오버 로드 중 하나의 형식이 다른의 해당 형식으로 확장 되 면 컴파일러는 후자를 제거 합니다. 즉, 최소한의 확대를 필요로 하는 오버 로드를 유지 합니다.  
  
6. **단일 후보.** 하나의 오버 로드만 유지 되 고 해당 오버 로드에 대 한 호출을 확인 하는 오버 로드를 쌍으로 계속 고려 합니다. 컴파일러가 오버 로드를 단일 후보로 줄일 수 없는 경우 오류를 생성 합니다.  
  
 다음 그림에서는 호출할 오버 로드 된 버전 집합을 결정 하는 프로세스를 보여 줍니다.  
  
 ![오버 로드 확인 프로세스의 흐름 다이어그램](./media/overload-resolution/determine-overloaded-version.gif "오버 로드 된 버전 간 확인")    
  
 다음 예제에서는이 오버 로드 확인 프로세스를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 첫 번째 호출에서 컴파일러는 첫 번째 인수의 형식 (`Short`)이 해당 하는 매개 변수 (`Byte`)의 형식으로 축소 되기 때문에 첫 번째 오버 로드를 제거 합니다. 그런 다음 두 번째 오버 로드 (`Short` 및 `Single`)의 각 인수 형식이 세 번째 오버 로드 (`Integer` 및 `Single`)의 해당 형식으로 확대 되기 때문에 세 번째 오버 로드를 제거 합니다. 두 번째 오버 로드는 더 적게 확대 해야 하므로 컴파일러에서 호출에이 오버 로드를 사용 합니다.  
  
 두 번째 호출에서 컴파일러는 축소를 기준으로 오버 로드를 제거할 수 없습니다. 첫 번째 호출에서와 같은 이유로 세 번째 오버 로드를 제거 합니다 .이는 두 번째 오버 로드를 사용 하 여 인수 형식의 확대/축소를 줄일 수 있기 때문입니다. 그러나 컴파일러는 첫 번째 및 두 번째 오버 로드 사이를 확인할 수 없습니다. 각에는 다른 정의 된 매개 변수 형식 (`Short`에는`Byte` 하 고 `Double``Single`)에는 해당 형식으로 확대 됩니다. 따라서 컴파일러는 오버 로드 확인 오류를 생성 합니다.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>오버 로드 된 선택적 및 ParamArray 인수  
 프로시저의 두 오버 로드에 동일한 시그니처가 있는 경우, 즉 마지막 매개 변수가 하나에서 [선택적](../../../../visual-basic/language-reference/modifiers/optional.md) 으로 선언 되는 경우를 제외 [하 고,](../../../../visual-basic/language-reference/modifiers/paramarray.md) 컴파일러는 다음과 같이 해당 프로시저에 대 한 호출을 확인 합니다.  
  
|호출에서로 마지막 인수를 제공 하는 경우|컴파일러는 마지막 인수를로 선언 하는 오버 로드에 대 한 호출을 확인 합니다.|  
|---|---|  
|값 없음 (인수 생략)|`Optional`|  
|단일 값|`Optional`|  
|쉼표로 구분 된 목록에 있는 두 개 이상의 값|`ParamArray`|  
|임의의 길이 (빈 배열 포함)의 배열입니다.|`ParamArray`|  
  
## <a name="see-also"></a>참고자료

- [선택적 매개 변수](./optional-parameters.md)
- [매개 변수 배열](./parameter-arrays.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [프로시저 문제 해결](./troubleshooting-procedures.md)
- [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)
- [방법: 오버로드된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)
- [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [프로시저를 오버로드할 때 고려해야 할 사항](./considerations-in-overloading-procedures.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [확장명 메서드](./extension-methods.md)
