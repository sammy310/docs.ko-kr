---
title: '>> 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: 8803dc2e25edde756958a243d429dd30c5c78bcf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816969"
---
# <a name="-operator-visual-basic"></a>>> 연산자 (Visual Basic)
비트 패턴에 산술 오른쪽 시프트를 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 정수 계열 숫자 값입니다. 결과 비트 패턴을 이동한입니다. 데이터 형식이 동일 `pattern`합니다.  
  
 `pattern`  
 필수 요소. 정수 계열 숫자 식입니다. 이동할 비트 패턴입니다. 데이터 형식은 정수 계열 형식 이어야 합니다 (`SByte`, `Byte`, `Short`, `UShort`를 `Integer`를 `UInteger`를 `Long`, 또는 `ULong`).  
  
 `amount`  
 필수. 숫자 식입니다. 비트 패턴을 이동할 비트 수입니다. 데이터 형식 이어야 합니다 `Integer` 변환할 또는 `Integer`합니다.  
  
## <a name="remarks"></a>설명  
 산술 shifts 순환있지 않습니다 즉, 결과의 한쪽 끝에서 벗어나 이동한 비트는 반대쪽 다시 도입 되지 않습니다. 산술 오른쪽 시프트에서 가장 오른쪽 비트 위치를 넘어 이동 하는 비트 무시 되 고 왼쪽 (기호) 비트 비워진 왼쪽 비트 위치로 전파 됩니다. 즉 `pattern` 음수 값을 가진 비워진된 위치 중 하나로 설정 됩니다; 그렇지 않으면 0으로 설정 됩니다.  
  
 데이터 형식을 `Byte`, `UShort`를 `UInteger`, 및 `ULong` 전파할 수 없습니다 부호 비트 이므로 서명 되지 않은 합니다. 경우 `pattern` 의 부호 없는 형식이, 비워진된 위치는 항상 0으로 설정 됩니다.  
  
 Visual Basic로 결과 보유할 수 있는 보다 자세한 비트 시프트를 방지 하려면의 값을 마스크 `amount` 의 데이터 형식에 해당 하는 크기 마스크를 사용 하 여 `pattern`입니다. 이러한 값의 이진 AND 시프트에 대 한 사용 됩니다. 마스크 크기는 다음과 같습니다.  
  
|데이터 형식 `pattern`|크기 마스크 (10 진수)|크기 마스크 (16 진수)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 하는 경우 `amount` 가 0 이면 값 `result` 의 값과 일치 `pattern`합니다. 경우 `amount` 가 음수 이면 해당 부호 없는 값으로 취급 되며 적절 한 크기 마스크입니다.  
  
 산술 shifts 오버플로 예외를 생성 하지 않습니다.  
  
## <a name="overloading"></a>오버로딩  
 합니다 `>>` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `>>` 정수 값에 산술 오른쪽 시프트를 수행 하는 연산자입니다. 결과 항상 동일한 데이터 이동 되는 식의 형식에 있습니다.  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 앞의 예제 결과 다음과 같습니다.  
  
-   `result1` 2560 (0000 1010 0000 0000)입니다.  
  
-   `result2` 160 (0000 0000 1010 0000)입니다.  
  
-   `result3` 2 (0000 0000 0000 0010)입니다.  
  
-   `result4` 640 (0010 1000 0000 0000)입니다.  
  
-   `result5` 0 (오른쪽으로 15 자리 이동된).  
  
 에 대 한 이동량 `result4` 18로 계산 됩니다가 2 및 15입니다.  
  
 다음 예에서는 음수 값에 산술 shifts를 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 앞의 예제 결과 다음과 같습니다.  
  
-   `negresult1` -512 (1111 1110 0000 0000)입니다.  
  
-   `negresult2` 이-1 (부호 비트 전파 됨 입니다).  
  
## <a name="see-also"></a>참고자료

- [비트 시프트 연산자](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [>>= 연산자](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
