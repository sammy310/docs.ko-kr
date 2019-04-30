---
title: Double 데이터 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 701d10a334757a96ffd634204c1e1d5eb5418ce6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054447"
---
# <a name="double-data-type-visual-basic"></a>Double 데이터 형식(Visual Basic)
부호 있는 IEEE 64 비트 (8 바이트) 배정밀도 부동 소수점 숫자 값에서-1.79769313486231570 + 308에서-범위에 있는 저장 4.94065645841246544E-324 음수 값을 한 경우 4.94065645841246544 e에서-324 1.79769313486231570 e + 308에 대 한 양수 값입니다. 배정밀도 숫자는 실수의 근사값을 저장 합니다.  
  
## <a name="remarks"></a>설명  
 `Double` 숫자 데이터 형식을 사용할 수 있는 가장 크고 가장 작은 크기를 제공 합니다.  
  
 `Double`의 기본값은 0입니다.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
- **전체 자릿수입니다.** 부동 소수점 숫자를 사용 하 여 작업할 때 없다는 점에 주의 해야 하는 항상 정확한 표현을 메모리에서. 값 비교 등의 특정 작업에서 예기치 않은 결과가 나타날 수 및 `Mod` 연산자입니다. 자세한 내용은 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.  
  
- **뒤에 오는 0입니다.** 부동 소수점 데이터 형식에 후행 0 문자의 모든 내부 표현이 없습니다. 예를 들어, 이러한 구분 하지 않습니다 4.2000 및 4.2 합니다. 결과적으로 후행 0 문자 표시 하는 경우 또는 인쇄 부동 소수점 값 표시 되지 않습니다.  
  
- **형식 문자입니다.** 리터럴 형식 문자 `R`를 리터럴에 추가하면 `Double` 데이터 형식이 됩니다. 예를 들어 정수 값을 뒤 `R`, 값으로 변경 되는 `Double`합니다.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     식별자 형식 문자 `#`를 식별자에 추가하면 `Double`가 됩니다. 다음 예에서 변수 `num` 으로 입력 된를 `Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
- **Framework 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Double?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Double?displayProperty=nameWithType>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [Decimal 데이터 형식](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Single 데이터 형식](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
