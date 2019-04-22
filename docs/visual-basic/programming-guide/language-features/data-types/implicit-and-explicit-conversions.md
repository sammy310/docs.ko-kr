---
title: 암시적 변환과 명시적 변환(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: 82ff710629089cd14c7e982b4afa4301d0790811
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833999"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a>암시적 변환과 명시적 변환(Visual Basic)
*암시적 변환* 소스 코드의 특수 구문이 필요 하지 않습니다. 다음 예제에서는 Visual Basic 암시적으로 변환 된 값 `k` 단 정밀도 부동 소수점 값에 할당 하기 전에 `q`입니다.  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 *명시적 변환* 형식 변환 키워드를 사용 합니다. Visual Basic에서는 이러한는 여러 키워드를 원하는 데이터 형식에 대 한 괄호 안에 식을 강제 변환 합니다. 이러한 키워드는 함수 처럼 동작 하지만 함수 호출을 사용 하 여 보다 약간 더 빠르게 실행 이므로 컴파일러 코드 인라인을 생성 합니다.  
  
 앞의 예제에서의 다음 확장에는 `CInt` 키워드의 값을 변환 `q` 에 할당 하기 전에 정수 돌아가기 `k`합니다.  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a>변환 키워드  
 다음 표에서 사용할 수 있는 변환 키워드를 보여 줍니다.  
  
|형식 변환 키워드|식 데이터 형식으로 변환합니다.|변환할 식의 허용 되는 데이터 형식|  
|---|---|---|  
|`CBool`|[Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `String`, `Object`|  
|`CByte`|[Byte 데이터 형식](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|모든 숫자 유형 (포함 `SByte` 열거 형식 및), `Boolean`, `String`, `Object`|  
|`CChar`|[Char 데이터 형식](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|  
|`CDate`|[Date 데이터 형식](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|  
|`CDbl`|[Double 데이터 형식](../../../../visual-basic/language-reference/data-types/double-data-type.md)|모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`|  
|`CDec`|[Decimal 데이터 형식](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`|  
|`CInt`|[Integer 데이터 형식](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`|  
|`CLng`|[Long 데이터 형식](../../../../visual-basic/language-reference/data-types/long-data-type.md)|모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`|  
|`CObj`|[Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)|모든 형식|  
|`CSByte`|[SByte 데이터 형식](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|모든 숫자 유형 (포함 `Byte` 열거 형식 및), `Boolean`, `String`, `Object`|  
|`CShort`|[Short 데이터 형식](../../../../visual-basic/language-reference/data-types/short-data-type.md)|모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`|  
|`CSng`|[Single 데이터 형식](../../../../visual-basic/language-reference/data-types/single-data-type.md)|모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`|  
|`CStr`|[String 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md)|모든 숫자 유형 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `Char`, `Char` 배열 `Date`, `Object`|  
|`CType`|쉼표를 다음 지정 된 형식 (`,`)|변환 하는 경우는 *기본 데이터 형식* 해당 변환 키워드에 허용 된 대로 형식을 동일한 (기본 형식의 배열을 포함)<br /><br /> 변환 하는 경우는 *복합 데이터 형식을*를 구현 하는 인터페이스 및 상속 된 클래스<br /><br /> 가 오버 로드는 클래스 또는 구조체를 변환할 때 `CType`, 해당 클래스 또는 구조체|  
|`CUInt`|[UInteger 데이터 형식](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`|  
|`CULng`|[ULong 데이터 형식](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`|  
|`CUShort`|[UShort 데이터 형식](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`|  
  
## <a name="the-ctype-function"></a>CType 함수  
 합니다 [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) 두 인수에 작동 합니다. 첫 번째 변환할 식이고 두 번째는 대상 데이터 형식 또는 개체 클래스. 첫 번째 인수 형식이 아닌 식 이어야 합니다 하는 참고 합니다.  
  
 `CType` *인라인 함수*변환 하면 컴파일된 코드 즉, 종종 함수를 생성 하지 않고 호출 합니다. 이 성능을 향상 시킵니다.  
  
 에 대 한 비교 `CType` 다른 형식 변환 키워드를 사용 하 여 볼 [DirectCast 연산자](../../../../visual-basic/language-reference/operators/directcast-operator.md) 하 고 [TryCast 연산자](../../../../visual-basic/language-reference/operators/trycast-operator.md)합니다.  
  
### <a name="elementary-types"></a>기본 형식  
 다음 예에서는 `CType`의 사용법을 보여줍니다.  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a>복합 형식  
 사용할 수 있습니다 `CType` 값 복합 데이터 형식을 기본 형식으로 변환 합니다. 개체 클래스를 다음 예제와 같이 해당 인터페이스 중 하나의 형식으로 강제 변환에 사용할 수 있습니다.  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a>배열 형식  
 `CType` 다음 예제와 같이 배열 데이터 형식에서 변환할 수도 있습니다.  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 자세한 내용 및 예제를 참조 하세요 [배열 변환](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)합니다.  
  
### <a name="types-defining-ctype"></a>CType 정의 형식  
 정의할 수 있습니다 `CType` 클래스 또는 구조체 정의에 있습니다. 이 클래스 또는 구조체의 형식에서 값을 변환할 수 있습니다. 자세한 내용 및 예제를 참조 하세요. [방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.  
  
> [!NOTE]
>  변환 키워드를 사용 하 여 사용 되는 값은 대상 데이터 형식에 대해 유효 해야 합니다. 그렇지 않으면 오류가 발생 합니다. 예를 들어, 변환 하려는 경우는 `Long` 에 `Integer`의 값을 `Long` 의 유효한 범위 내에 있어야는 `Integer` 데이터 형식.  
  
> [!CAUTION]
>  지정 `CType` 원본 유형을 대상 형식에서 파생 되지 않습니다 하는 경우 런타임 시 다른 실패 한 클래스 형식에서 변환할 수 있습니다. 이러한 오류를 throw 한 <xref:System.InvalidCastException> 예외입니다.  
  
 그러나 형식 중 하나를 구조체 또는 클래스를 정의한 경우 및 정의 하는 경우 `CType` 해당 구조체 또는 클래스에는 변환의 요구 사항을 충족 하는 경우 성공할 수 여 `CType`합니다. [방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.  
  
 명시적 변환을 수행 라고도 *캐스팅* 지정 된 데이터 형식 또는 개체 클래스에는 식입니다.  
  
## <a name="see-also"></a>참고자료

- [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [문자열과 다른 형식 사이의 변환](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [방법: Visual Basic에서 다른 형식으로 변환할 개체](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [구조체](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [데이터 형식](../../../../visual-basic/language-reference/data-types/index.md)
- [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
