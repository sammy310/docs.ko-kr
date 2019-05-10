---
title: 형식 변환 함수(Visual Basic)
ms.date: 10/24/2018
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: 3321a9a290e6ba49be289848e4d16907ad9edbda
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662587"
---
# <a name="type-conversion-functions-visual-basic"></a>형식 변환 함수(Visual Basic)
이러한 함수는 변환 코드가 식을 계산 하는 코드의 일부인 즉 인라인으로 컴파일됩니다. 때때로 성능을 향상 시키는 변환을 수행 하는 프로시저에 대 한 호출이 있습니다. 각 함수는 식에서 특정 데이터 형식으로 강제 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## <a name="part"></a>파트  
 `expression`  
 필수 요소. 원본 데이터 형식의 모든 식입니다.  
  
## <a name="return-value-data-type"></a>반환 값 데이터 형식  
 함수 이름은 다음 표에 나와 있는 것 처럼 반환 하는 값의 데이터 형식을 결정 합니다.  
  
|함수 이름|반환 데이터 형식|에 대 한 범위 `expression` 인수|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|유효한 `Char` 또는 `String` 또는 숫자 식입니다.|  
|`CByte`|[Byte 데이터 형식](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte.MinValue?displayProperty=nameWithType> (0)를 통해 <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (부호 없음); 소수 부분이 반올림 됩니다.<sup> 1</sup><br/><br/>Visual Basic 15.8부터 Visual Basic을 사용한 바이트 변환 하는 부동 소수점의 성능을 최적화 합니다 `CByte` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다. 참조를 [CInt 예제](#cint-example) 섹션 예입니다.|  
|`CChar`|[Char 데이터 형식](../../../visual-basic/language-reference/data-types/char-data-type.md)|유효한 `Char` 또는 `String` 식;의 첫 번째 문자만 `String` 변환 됩니다; 값 0 ~ 65535 (부호 없음) 될 수 있습니다.|  
|`CDate`|[Date 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md)|시간과 날짜의 모든 유효한 표현입니다.|  
|`CDbl`|[Double 데이터 형식](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1.79769313486231570 + 308에서-4.94065645841246544E-324 음수 값이 있습니다. 4.94065645841246544E-324 1.79769313486231570 e + 308 양수 값에 대 한 합니다.|  
|`CDec`|[Decimal 데이터 형식](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|+ /-79228162514264337593543950335-즉, 소수 자릿수가 없는 숫자입니다. 소수 자릿수가 28 숫자 범위는 + /-7.9228162514264337593543950335 사이입니다. 가장 작은 가능한 0이 아닌 숫자는 0.0000000000000000000000000001 (+ 1E-28).|  
|`CInt`|[Integer 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32.MinValue?displayProperty=nameWithType> (-2147483648)부터 <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2147483647); 소수 부분이 반올림 됩니다.<sup> 1</sup> <br/><br/>Visual Basic 15.8부터 Visual Basic을 사용 하 여 정수 변환 부동 소수점의 성능을 최적화 합니다 `CInt` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다. 참조를 [CInt 예제](#cint-example) 섹션 예입니다. |  
|`CLng`|[Long 데이터 형식](../../../visual-basic/language-reference/data-types/long-data-type.md)|<xref:System.Int64.MinValue?displayProperty=nameWithType> (-9223372036854775808)부터 <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9223372036854775807); 소수 부분이 반올림 됩니다.<sup> 1</sup><br/><br/>Visual Basic 15.8부터 Visual Basic을 사용 하 여 64 비트 정수로 변환 하는 부동 소수점의 성능을 최적화 합니다 `CLng` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다. 참조를 [CInt 예제](#cint-example) 섹션 예입니다.|  
|`CObj`|[Object 데이터 형식](../../../visual-basic/language-reference/data-types/object-data-type.md)|모든 유효한 식입니다.|  
|`CSByte`|[SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte.MinValue?displayProperty=nameWithType> (-128)를 통해 <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); 소수 부분이 반올림 됩니다.<sup> 1</sup><br/><br/>Visual Basic 15.8부터 Visual Basic을 사용 하 여 부호 있는 바이트 변환 부동 소수점의 성능을 최적화 합니다 `CSByte` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다. 참조를 [CInt 예제](#cint-example) 섹션 예입니다.|  
|`CShort`|[Short 데이터 형식](../../../visual-basic/language-reference/data-types/short-data-type.md)|<xref:System.Int16.MinValue?displayProperty=nameWithType> (-32768)부터 <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32767); 소수 부분이 반올림 됩니다.<sup> 1</sup><br/><br/>Visual Basic 15.8부터 Visual Basic을 사용 하 여 16 비트 정수로 변환 하는 부동 소수점의 성능을 최적화 합니다 `CShort` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다. 참조를 [CInt 예제](#cint-example) 섹션 예입니다.|  
|`CSng`|[Single 데이터 형식](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3.402823E + 38에서-1.401298E-45 음수 값이 있습니다. 1.401298E-45 3.402823E + 38 양수 값에 대 한 합니다.|  
|`CStr`|[String 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)|에 대 한 반환 `CStr` 종속 된 `expression` 인수입니다. 참조 [CStr 함수의 반환 값](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)합니다.|  
|`CUInt`|[UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32.MinValue?displayProperty=nameWithType> (0)를 통해 <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4294967295) (부호 없음); 소수 부분이 반올림 됩니다.<sup> 1</sup><br/><br/>Visual Basic 15.8부터 Visual Basic을 사용 하 여 부호 없는 정수로 변환 하는 부동 소수점의 성능을 최적화 합니다 `CUInt` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다. 참조를 [CInt 예제](#cint-example) 섹션 예입니다.|  
|`CULng`|[ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64.MinValue?displayProperty=nameWithType> (0)를 통해 <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (부호 없음); 소수 부분이 반올림 됩니다.<sup> 1</sup><br/><br/>Visual Basic 15.8부터 Visual Basic을 사용 하 여 부호 없는 정수 (long) 변환 부동 소수점의 성능을 최적화 합니다 `CULng` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다. 참조를 [CInt 예제](#cint-example) 섹션 예입니다.|  
|`CUShort`|[UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16.MinValue?displayProperty=nameWithType> (0)를 통해 <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (부호 없음); 소수 부분이 반올림 됩니다.<sup> 1</sup><br/><br/>Visual Basic 15.8부터 Visual Basic을 사용 하 여 부호 없는 16 비트 정수로 변환 하는 부동 소수점의 성능을 최적화 합니다 `CUShort` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다. 참조를 [CInt 예제](#cint-example) 섹션 예입니다.|  
  
 <sup>1</sup> 소수 부분이 호출 반올림 하는 특수 한 유형의 대상이 될 수 있습니다 *은행원의 반올림*합니다. 자세한 내용은 "주의"를 참조 하세요.  
  
## <a name="remarks"></a>설명  
 일반적으로 사용 해야는 Visual Basic 형식 변환 함수는.NET Framework 메서드 보다 우선적으로 같은 `ToString()`하거나에서 <xref:System.Convert> 클래스 또는 개별 형식 구조체 또는 클래스에서. Visual Basic 함수는 Visual Basic 코드를 사용 하 여 최적의 상호 작용을 위해 설계 되었습니다 및 더 간결 하 고 읽기 쉽게 소스 코드 할 수도 있습니다. 또한.NET Framework 변환 메서드를 생성 하지 않을 경우 Visual Basic 함수 예를 들어 변환 하는 경우와 동일한 결과 `Boolean` 에 `Integer`입니다. 자세한 내용은 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.  

Visual Basic 15.8부터 부동으로 소수점을 정수로 변환의 성능을 최적화 된 전달 하는 경우는 <xref:System.Single> 또는 <xref:System.Double> 정수 변환 함수 중 하나에 다음과 같은 방법으로 반환 되는 값 (`CByte`합니다 `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

이 최적화는 많은 수의 정수 변환 실행할 배 더 빠르게 수행 하는 코드를 허용 합니다. 다음 예제에서는 이러한 최적화 부동으로 소수점을 정수로 변환 합니다.

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a>동작  
  
- **강제 변환 합니다.** 일반적으로 기본 데이터 형식 보다는 특정 데이터 형식 작업의 결과 강제 하는 데이터 형식 변환 함수를 사용할 수 있습니다. 사용 예를 들어 `CDec` 10 진수 연산을 경우는 단 정밀도, 배정밀도 정수 산술 연산은 일반적으로 수행 됩니다.  
  
- **변환 실패입니다.** 경우는 `expression` 함수에 전달 되는 데이터 형식의 범위를 벗어난 하는 변환할는 <xref:System.OverflowException> 발생 합니다.  
  
- **소수 부분입니다.** 정수가 아닌 값을 정수 계열 변환 하는 경우 입력에서 정수 변환 함수 (`CByte`, `CInt`, `CLng`, `CSByte`를 `CShort`를 `CUInt`, `CULng`, 및 `CUShort`) 제거 합니다 소수 부분 및 값을 가장 가까운 정수로 반올림 합니다.  
  
     소수 부분이 정확 하 게 하는 경우 0.5 정수 변환 함수를 반올림 하는 가장 근사한 짝수 정수로 합니다. 예를 들어 0.5 0 및 1.5와 2.5는 2로 반올림으로 반올림 합니다. 이 라고도 *은행원의 반올림*, 및 이러한 많은 숫자를 함께 추가 하는 경우 누적 될 수 있습니다를 보완 하기 위한 것입니다.  
  
     `CInt` 및 `CLng` 에서 다를 <xref:Microsoft.VisualBasic.Conversion.Int%2A> 및 <xref:Microsoft.VisualBasic.Conversion.Fix%2A> 함수는 숫자의 소수 부분을 반올림 하는 것이 아니라, truncate입니다. 또한 `Fix` 고 `Int` 에 통과할 때 항상 동일한 데이터 형식의 값을 반환 합니다.  
  
- **변환 날짜/시간입니다.** 사용 된 <xref:Microsoft.VisualBasic.Information.IsDate%2A> 날짜 및 시간 값을 변환할 수 있는지를 결정 하는 함수입니다. `CDate` 리터럴 날짜 및 시간 리터럴 하지만 숫자가 아닌 값을 인식합니다. Visual Basic 6.0을 변환할 `Date` 값을 `Date` Visual Basic 2005의에서 값 또는 이상 버전을 사용할 수는 <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> 메서드.  
  
- **중립 날짜/시간 값입니다.** 합니다 [날짜 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md) 항상 날짜 및 시간 정보를 포함 합니다. 형식 변환 목적으로, Visual Basic은 간주 1/1/0001 (1 년 1 월 1 일) 수를 *중립 값* 시간에 대 한 중립 값으로 날짜 및 00시: 00 (자정)에 대 한 합니다. 변환 하는 경우는 `Date` 값을 문자열로 `CStr` 기본값이 결과 문자열에 포함 되지 않습니다. 예를 들어, 변환 하는 경우 `#January 1, 0001 9:30:00#` 문자열로 결과 "오전 9시 30분: 00"은 날짜 정보를 표시 하지 않습니다. 그러나 날짜 정보는 여전히 원래 `Date` 값과 같은 함수를 사용 하 여 복구할 수 있습니다 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> 함수입니다.  
  
- **문화권 구분 합니다.** 응용 프로그램에 대 한 현재 문화권 설정에 따라 변환을 수행 하는 문자열을 포함 하는 형식 변환 함수입니다. 예를 들어 `CDate` 시스템의 로캘 설정에 따라 날짜 형식을 인식 합니다. 일, 월 및 연도 로캘에 대 한 올바른 순서로 제공 해야 합니다 또는 날짜를 올바르게 해석 될 수 있습니다. 자세한 날짜 형식은 "Wednesday" 등의 주 날짜 문자열을 포함 하는 경우 인식 되지 않습니다.  
  
     로캘에 지정 된 것과 다른 형식으로 값의 문자열 표현에서 변환 해야 할 경우 Visual Basic 형식 변환 함수를 사용할 수 없습니다. 이 위해 사용 합니다 `ToString(IFormatProvider)` 및 `Parse(String, IFormatProvider)` 메서드는 값의 형식입니다. 사용 예를 들어 <xref:System.Double.Parse%2A?displayProperty=nameWithType> 문자열을 변환 하는 경우는 `Double`를 사용 하 여 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을 변환 하는 경우 `Double` 문자열로 합니다.  
  
## <a name="ctype-function"></a>CType Function  
 [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) 두 번째 인수 `typename`, 강제 변환 하 고 `expression` 에 `typename`여기서 `typename` 데이터 형식, 구조체, 클래스 또는 인터페이스를 있을 변환할 수 있습니다.  
  
 에 대 한 비교 `CType` 다른 형식 변환 키워드를 사용 하 여 볼 [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 하 고 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md)합니다.  
  
## <a name="cbool-example"></a>CBool 예제  
 다음 예제에서는 합니다 `CBool` 함수 식을 변환할 `Boolean` 값입니다. 식이 0이 아닌 값으로 계산 될 경우 `CBool` 반환 `True`이 고, 그렇지 않으면 반환 `False`합니다.  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a>CByte 예제  
 다음 예제에서는 합니다 `CByte` 식을 변환 하는 함수를 `Byte`입니다.  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a>CChar 예제  
 다음 예제에서는 합니다 `CChar` 의 첫 번째 문자를 변환 하는 함수를 `String` 식을 `Char` 형식.  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 입력된 인수 `CChar` 데이터 형식 이어야 합니다 `Char` 또는 `String`합니다. 사용할 수 없습니다 `CChar` 때문에 숫자를 문자로 변환할 `CChar` 숫자 데이터 형식을 허용할 수 없습니다. 다음 예제에서는 코드 포인트 (문자 코드)를 나타내는 숫자를 가져오고 해당 문자로 변환 합니다. 사용 하 여는 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> 숫자의 문자열을 가져올 함수 `CInt` 형식으로 문자열을 변환할 `Integer`, 및 `ChrW` 숫자 형식으로 변환 `Char`합니다.  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a>CDate 예제  
 다음 예제에서는 합니다 `CDate` 문자열을 변환 하는 함수 `Date` 값입니다. 일반적으로 하드 코딩 된 날짜 및 시간 문자열 (이 예제 에서처럼)으로 권장 되지 않습니다. 날짜 리터럴과 #Feb 12, 1969 # 등의 시간 리터럴을 사용 하 여 및 # 4시 45분: 23 PM #를 대신 합니다.  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a>CDbl 예제  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a>CDec 예제  
 다음 예제에서는 합니다 `CDec` 숫자 값으로 변환 하는 함수 `Decimal`합니다.  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a>CInt 예제  
 다음 예제에서는 합니다 `CInt` 함수에 값을 변환할 `Integer`합니다.  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a>CLng 예제
 다음 예제에서는 합니다 `CLng` 값을 변환 하는 함수 `Long`합니다.  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a>CObj 예제  
 다음 예제에서는 합니다 `CObj` 숫자 값으로 변환 하는 함수 `Object`합니다. `Object` 변수 자체에 4 바이트 포인터를 가리키는 포함 된 `Double` 값이 할당 합니다.  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a>CSByte 예제  
 다음 예제에서는 합니다 `CSByte` 숫자 값으로 변환 하는 함수 `SByte`합니다.  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a>CShort 예제  
 다음 예제에서는 합니다 `CShort` 숫자 값으로 변환 하는 함수 `Short`합니다.  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a>CSng 예제  
 다음 예제에서는 합니다 `CSng` 값을 변환 하는 함수 `Single`합니다.  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a>CStr 예제  
 다음 예제에서는 합니다 `CStr` 숫자 값으로 변환 하는 함수 `String`합니다.  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 다음 예제에서는 합니다 `CStr` 변환할 함수 `Date` 값을 `String` 값입니다.  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 `CStr` 항상 렌더링을 `Date` 예를 들어, 현재 로캘에 대 한 표준 짧은 형식으로 값 "2003 년 6 월 15 오후 4시 35분: 47"입니다. 그러나 `CStr` 를 표시 하지 않습니다 합니다 *중립 값* 1/1/0001의 날짜와 시간에 대 한 00시: 00입니다.  
  
 반환 값에 대 한 자세한 `CStr`를 참조 하세요 [CStr 함수의 반환 값](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)합니다.  
  
## <a name="cuint-example"></a>CUInt 예제  
 다음 예제에서는 합니다 `CUInt` 숫자 값으로 변환 하는 함수 `UInteger`합니다.  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a>CULng 예제  
 다음 예제에서는 합니다 `CULng` 숫자 값으로 변환 하는 함수 `ULong`합니다.  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a>CUShort 예제  
 다음 예제에서는 합니다 `CUShort` 숫자 값으로 변환 하는 함수 `UShort`합니다.  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [변환 함수](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Visual Basic의 형식 변환](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
