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
ms.openlocfilehash: cc5e5cc437175e9aebfba559488ca74283faa9ad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870151"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>CStr 함수의 반환 값(Visual Basic)

다음 표에서는 `CStr` 의 여러 데이터 형식에 대 한 반환 값을 설명 합니다 `expression` .  
  
|`expression`형식이 인 경우|`CStr` return|  
|-----------------------------|--------------------|  
|[Boolean 데이터 형식](../data-types/boolean-data-type.md)|"True" 또는 "False"를 포함 하는 문자열입니다.|  
|[날짜 데이터 형식](../data-types/date-data-type.md)|`Date`시스템의 간단한 날짜 형식 값 (날짜 및 시간)을 포함 하는 문자열입니다.|  
|[숫자 데이터 형식](../../programming-guide/language-features/data-types/numeric-data-types.md)|숫자를 나타내는 문자열입니다.|  
  
## <a name="cstr-and-date"></a>CStr 및 Date  

 형식에는 `Date` 항상 날짜 및 시간 정보가 포함 됩니다. 형식 변환의 목적을 위해 Visual Basic은 1/1/0001 (1 년 1 월 1 일)을 날짜의 *중립 값* 으로 간주 하 고 00:00:00 (자정)을 시간에 대 한 중립 값으로 간주 합니다. `CStr` 결과 문자열에 중립 값을 포함 하지 않습니다. 예를 들어 문자열로 변환 하는 경우 `#January 1, 0001 9:30:00#` 결과는 "9:30:00 AM"이 고 날짜 정보는 표시 되지 않습니다. 그러나 날짜 정보는 여전히 원래 값에 존재 하며와 `Date` 같은 함수를 사용 하 여 복구할 수 있습니다 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .  
  
> [!NOTE]
> `CStr`함수는 응용 프로그램의 현재 문화권 설정에 따라 변환을 수행 합니다. 특정 문화권의 숫자에 대 한 문자열 표현을 가져오려면 숫자의 메서드를 사용 `ToString(IFormatProvider)` 합니다. 예를 들어 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을로 변환할 때를 사용 `Double` `String` 합니다.  
  
## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [형식 변환 함수](type-conversion-functions.md)
- [Boolean 데이터 형식](../data-types/boolean-data-type.md)
- [날짜 데이터 형식](../data-types/date-data-type.md)
