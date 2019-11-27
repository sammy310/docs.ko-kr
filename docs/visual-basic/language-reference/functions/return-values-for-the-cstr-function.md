---
title: CStr 함수의 반환 값
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 4a40777c7290ec6d8c0d032f2edca5d889e20f04
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349996"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>CStr 함수의 반환 값(Visual Basic)
다음 표에서는 다양 한 데이터 형식 `expression`에 대 한 `CStr` 반환 값에 대해 설명 합니다.  
  
|`expression` 형식이 인 경우|`CStr` return|  
|-----------------------------|--------------------|  
|[Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|"True" 또는 "False"를 포함 하는 문자열입니다.|  
|[Date 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md)|시스템의 간단한 날짜 형식으로 된 `Date` 값 (날짜 및 시간)을 포함 하는 문자열입니다.|  
|[숫자 데이터 형식](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|숫자를 나타내는 문자열입니다.|  
  
## <a name="cstr-and-date"></a>CStr 및 Date  
 `Date` 형식에는 항상 날짜 및 시간 정보가 포함 됩니다. 형식 변환의 목적을 위해 Visual Basic은 1/1/0001 (1 년 1 월 1 일)을 날짜의 *중립 값* 으로 간주 하 고 00:00:00 (자정)을 시간에 대 한 중립 값으로 간주 합니다. `CStr`은 결과 문자열에 중립 값을 포함 하지 않습니다. 예를 들어 `#January 1, 0001 9:30:00#`을 문자열로 변환 하는 경우 결과는 "9:30:00 AM"입니다. 날짜 정보는 표시 되지 않습니다. 그러나 날짜 정보는 원래 `Date` 값에 계속 제공 되며 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>와 같은 기능을 사용 하 여 복구할 수 있습니다.  
  
> [!NOTE]
> `CStr` 함수는 응용 프로그램의 현재 문화권 설정에 따라 변환을 수행 합니다. 특정 문화권의 숫자에 대 한 문자열 표현을 가져오려면 숫자의 `ToString(IFormatProvider)` 메서드를 사용 합니다. 예를 들어 `Double` 형식의 값을 `String`로 변환할 때 <xref:System.Double.ToString%2A?displayProperty=nameWithType>를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Date 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md)
