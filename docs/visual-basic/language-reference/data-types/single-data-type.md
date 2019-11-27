---
title: Single 데이터 형식
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343926"
---
# <a name="single-data-type-visual-basic"></a>Single 데이터 형식(Visual Basic)

음수 값의 경우-3.4028235 E + 38부터-1.401298 E-45 까지의 값에 해당 하는 부호 있는 IEEE 32 비트 (4 바이트) 단 정밀도 부동 소수점 숫자와 양수 값의 경우 1.401298 E-45 ~ 3.4028235 E + 38 사이의 값을 포함 합니다. 단 정밀도 숫자는 실수의 근사값을 저장 합니다.  
  
## <a name="remarks"></a>주의  

 `Single` 데이터 형식을 사용 하 여 `Double`의 전체 데이터 너비가 필요 하지 않은 부동 소수점 값을 포함 합니다. 경우에 따라 공용 언어 런타임에서 `Single` 변수를 긴밀 하 게 압축 하 고 메모리 사용을 줄일 수 있습니다.  
  
 `Single`의 기본값은 0입니다.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
- **소수.** 부동 소수점 숫자를 사용 하는 경우 항상 메모리에 정확한 표현이 없다는 점에 유의 하세요. 이로 인해 값 비교 및 `Mod` 연산자와 같은 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다. 자세한 내용은 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조 하세요.  
  
- **넓혀.** `Single` 데이터 형식은 `Double`으로 확대 됩니다. 즉 <xref:System.OverflowException?displayProperty=nameWithType> 오류가 발생 하지 않고 `Single`을 `Double`로 변환할 수 있습니다.  
  
- **후행 0입니다.** 부동 소수점 데이터 형식에는 후행 0 문자에 대 한 내부 표현이 없습니다. 예를 들어 4.2000과 4.2를 구분 하지 않습니다. 따라서 부동 소수점 값을 표시 하거나 인쇄할 때 후행 0 문자는 표시 되지 않습니다.  
  
- **문자를 입력 합니다.** 리터럴 형식 문자 `F`를 리터럴에 추가하면 `Single` 데이터 형식이 됩니다. 식별자 형식 문자 `!`를 식별자에 추가하면 `Single`가 됩니다.  
  
- **프레임 워크 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Single?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Single?displayProperty=nameWithType>
- [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
- [Decimal 데이터 형식](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Double 데이터 형식](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
