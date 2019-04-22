---
title: CStr 함수의 반환 값(Visual Basic)
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
ms.openlocfilehash: 3653194c7e48533e664ac7513ca7f4f48d1c69f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819517"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>CStr 함수의 반환 값(Visual Basic)
다음 표에서 반환 값에 대 한 설명 `CStr` 의 다른 데이터 형식에 대 한 `expression`합니다.  
  
|경우 `expression` 형식은|`CStr` return|  
|-----------------------------|--------------------|  
|[Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|"True"를 포함 하는 문자열 또는 "False"입니다.|  
|[Date 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md)|포함 된 문자열을 `Date` 시스템의 간단한 날짜 형식의 값 (날짜 및 시간).|  
|[숫자 데이터 형식](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|수를 나타내는 문자열입니다.|  
  
## <a name="cstr-and-date"></a>CStr 및 날짜  
 `Date` 형식을 항상 날짜 및 시간 정보를 포함 합니다. 형식 변환 목적으로, Visual Basic은 간주 1/1/0001 (1 년 1 월 1 일) 수를 *중립 값* 시간에 대 한 중립 값으로 날짜 및 00시: 00 (자정)에 대 한 합니다. `CStr` 중립 값의 결과 문자열에 포함 되지 않습니다. 예를 들어, 변환 하는 경우 `#January 1, 0001 9:30:00#` 문자열로 결과 "오전 9시 30분: 00"은 날짜 정보를 표시 하지 않습니다. 그러나 날짜 정보는 여전히 원래 `Date` 값과 같은 함수를 사용 하 여 복구할 수 있습니다 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>합니다.  
  
> [!NOTE]
>  `CStr` 함수가 응용 프로그램에 대 한 현재 문화권 설정에 따라 해당 변환을 수행 합니다. 숫자의 문자열 표현을 특정 문화권에서을 사용 수의 `ToString(IFormatProvider)` 메서드. 사용 예를 들어 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을 변환할 때는 `Double` 에 `String`합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Date 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md)
