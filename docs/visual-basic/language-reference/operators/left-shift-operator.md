---
title: << 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 327d0e5cbd1ebcc43bd47fb068f4513940c2165a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350977"
---
# <a name="-operator-visual-basic"></a>\<\< 연산자 (Visual Basic)
비트 패턴에 산술 왼쪽 시프트를 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 정수 숫자 값입니다. 결과 비트 패턴을 이동한입니다. 데이터 형식은 `pattern`와 동일 합니다.  
  
 `pattern`  
 필수 요소. 정수 계열 숫자 식입니다. 이동할 비트 패턴입니다. 데이터 형식은 정수 계열 형식 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`또는 `ULong`) 이어야 합니다.  
  
 `amount`  
 필수 요소. 숫자 식입니다. 비트 패턴을 이동할 비트 수입니다. 데이터 형식을 `Integer` 하거나 `Integer`으로 확장 해야 합니다.  
  
## <a name="remarks"></a>설명  
 산술 시프트는 순환 하지 않습니다. 즉, 결과의 한쪽 끝에서 이동 하는 비트가 다른 쪽 끝에서는 다시 계산 되지 않습니다. 산술 왼쪽 시프트에서 결과 데이터 형식의 범위를 벗어나 이동 하는 비트는 무시 되 고 오른쪽에서 비워진 비트 위치는 0으로 설정 됩니다.  
  
 결과에 포함 될 수 있는 것 보다 더 많은 비트로 시프트를 방지 하기 위해 Visual Basic는 `pattern`의 데이터 형식에 해당 하는 크기 마스크를 사용 하 여 `amount` 값을 마스크 합니다. 이러한 값의 이진은 이동 양에 사용 됩니다. 크기 마스크는 다음과 같습니다.  
  
|`pattern` 데이터 형식|크기 마스크 (10 진수)|크기 마스크 (16 진수)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 `amount` 0 이면 `result`의 값이 `pattern`의 값과 동일 합니다. `amount` 음수 이면 부호 없는 값으로 사용 되 고 적절 한 크기 마스크로 마스크 됩니다.  
  
 산술 시프트는 오버플로 예외를 생성 하지 않습니다.  
  
> [!NOTE]
> `<<` 연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다. 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예에서는 `<<` 연산자를 사용 하 여 정수 값에 대 한 산술 왼쪽 시프트 연산을 수행 합니다. 결과는 항상 이동 하는 식의 데이터 형식과 같습니다.  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 이전 예제의 결과는 다음과 같습니다.  
  
- `result1`은 192 (0000 0000 1100 0000)입니다.  
  
- `result2`은 3072 (0000 1100 0000 0000)입니다.  
  
- `result3`-32768 (1000 0000 0000 0000)입니다.  
  
- `result4`은 384 (0000 0001 1000 0000)입니다.  
  
- `result5`은 0 (왼쪽으로 15 자리 이동)입니다.  
  
 `result4`의 이동 금액은 17과 15로 계산 되며 1과 같습니다.  
  
## <a name="see-also"></a>참고자료

- [비트 시프트 연산자](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<<= 연산자](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
