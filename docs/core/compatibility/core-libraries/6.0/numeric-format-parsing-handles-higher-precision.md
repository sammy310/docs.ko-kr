---
title: '호환성이 손상되는 변경: 표준 숫자 형식 구문 분석 정밀도'
description: 이제 표준 숫자 형식 구문 분석이 더 높은 정밀도를 처리하는 핵심 .NET 라이브러리의 .NET 6 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 02/26/2021
ms.openlocfilehash: ad1555493bbc6198541365132cc421db7c01a5a2
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256922"
---
# <a name="standard-numeric-format-parsing-precision"></a>표준 숫자 형식 구문 분석 정밀도

이제 .NET은 `ToString` 및 `TryFormat`을 사용하여 숫자 형식을 문자열로 지정할 때 더 큰 정밀도 값을 지원합니다.

## <a name="change-description"></a>변경 내용 설명

숫자 형식을 문자열로 지정하는 경우 [형식 문자열](../../../../standard/base-types/standard-numeric-format-strings.md)의 ‘전체 자릿수 지정자’는 결과 문자열의 자릿수를 나타냅니다. [문자열의 시작 문자](../../../../standard/base-types/standard-numeric-format-strings.md#standard-format-specifiers)인 ‘형식 지정자’에 따라 정밀도는 전체 자릿수, 유효 자릿수 또는 소수 자릿수를 나타낼 수 있습니다.

이전 .NET 버전에서 표준 숫자 형식 구문 분석 논리는 99 이하의 정밀도로 제한됩니다. 일부 숫자 형식은 더 큰 정밀도를 사용하지만 `ToString(string format)`은 정밀도를 올바르게 표시하지 않습니다. 99보다 큰 정밀도를 지정하는 경우(예: `32.ToString("C100")`) 형식 문자열은 “정밀도 100의 통화” 대신 [사용자 지정 숫자 형식 문자열](../../../../standard/base-types/custom-numeric-format-strings.md)로 해석됩니다. 사용자 지정 숫자 형식 문자열에서 문자는 [문자 리터럴](../../../../standard/base-types/custom-numeric-format-strings.md#character-literals)로 해석됩니다. 또한 잘못된 형식 지정자를 포함하는 형식 문자열은 정밀도 값에 따라 다르게 해석됩니다. `H99`는 잘못된 형식 지정자에 대해 <xref:System.FormatException>을 throw하지만, `H100`은 사용자 지정 숫자 형식 문자열로 해석됩니다.

.NET 6부터 .NET은 최대 <xref:System.Int32.MaxValue?displayProperty=nameWithType>의 정밀도를 지원합니다. 자릿수를 포함하는 형식 지정자로 구성된 형식 문자열은 정밀도를 포함하는 표준 숫자 형식 문자열로 해석됩니다. 다음 조건 중 하나 또는 둘 다에 대해 <xref:System.FormatException>이 throw됩니다.

- 형식 지정자 문자는 [표준 형식 지정자](../../../../standard/base-types/standard-numeric-format-strings.md#standard-format-specifiers)가 아닙니다.
- 정밀도는 <xref:System.Int32.MaxValue?displayProperty=nameWithType>보다 큽니다.

해당 변경은 모든 숫자 형식에 영향을 주는 구문 분석 논리로 구현되었습니다.

다음 표에서는 다양한 형식 문자열의 동작 변경 내용을 보여 줍니다.

| 형식 문자열 | 이전 동작 | .NET 6 이상 동작 |
| - | - | - |
| `C2` | 소수 자릿수 2자리를 포함하는 통화를 나타냅니다. | 소수 자릿수 2자리를 포함하는 통화를 나타냅니다(‘변경 없음’). |
| `C100` | “C100”을 출력하는 사용자 지정 숫자 형식 문자열을 나타냅니다. | 소수 자릿수 100자리를 포함하는 통화를 나타냅니다. |
| `H99` | 잘못된 표준 형식 지정자 “H”로 인해 <xref:System.FormatException>을 throw합니다. | 잘못된 표준 형식 지정자 “H”로 인해 <xref:System.FormatException>을 throw합니다(‘변경 없음’). |
| `H100` | 사용자 지정 숫자 형식 문자열을 나타냅니다. | 잘못된 표준 형식 지정자 “H”로 인해 <xref:System.FormatException>을 throw합니다. |

## <a name="version-introduced"></a>도입된 버전

6.0 미리 보기 2

## <a name="reason-for-change"></a>변경 이유

이 변경은 숫자 형식 구문 분석에 더 높은 정밀도를 사용하는 경우 예기치 않은 동작을 수정합니다.

## <a name="recommended-action"></a>권장 조치

대부분의 경우 아무 작업도 필요하지 않으며 결과 문자열에 올바른 정밀도가 표시됩니다.

그러나 정밀도가 99보다 큰 경우 형식 지정자가 리터럴 문자로 해석되는 이전 동작으로 되돌리기 위해 해당 문자를 작은따옴표로 래핑하거나 백슬래시로 이스케이프할 수 있습니다. 예를 들어, 이전 .NET 버전에서 `42.ToString("G999")`은 `G999`를 반환합니다. 해당 동작을 유지하려면 형식 문자열을 `"'G'999"` 또는 `"\\G999"`로 변경합니다. 이 기능은 .NET Framework, .NET Core, .NET 5 이상에서 작동합니다.

다음 형식 문자열은 사용자 지정 숫자 형식 문자열로 계속 해석됩니다.

- ASCII 알파벳 문자가 아닌 문자로 시작합니다(예: `$` 또는 `è`).
- ASCII 숫자가 뒤에 오는 ASCII 알파벳 문자로 시작합니다(예: `A$`).
- ASCII 알파벳 문자로 시작하고 ASCII 숫자 시퀀스가 뒤에 온 다음, ASCII 숫자 문자가 아닌 문자가 옵니다(예: `A12A`).

## <a name="affected-apis"></a>영향을 받는 API

해당 변경은 모든 숫자 형식에 영향을 주는 구문 분석 논리로 구현되었습니다.

- <xref:System.Numerics.BigInteger.ToString(System.String)?displayProperty=fullName>
- <xref:System.Numerics.BigInteger.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Numerics.BigInteger.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int32.ToString(System.String)?displayProperty=fullName>
- <xref:System.Int32.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt32.ToString(System.String)?displayProperty=fullName>
- <xref:System.UInt32.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Byte.ToString(System.String)?displayProperty=fullName>
- <xref:System.Byte.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Byte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.SByte.ToString(System.String)?displayProperty=fullName>
- <xref:System.SByte.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.SByte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int16.ToString(System.String)?displayProperty=fullName>
- <xref:System.Int16.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt16.ToString(System.String)?displayProperty=fullName>
- <xref:System.UInt16.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int64.ToString(System.String)?displayProperty=fullName>
- <xref:System.Int64.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Int64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt64.ToString(System.String)?displayProperty=fullName>
- <xref:System.UInt64.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.UInt64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Half.ToString(System.String)?displayProperty=fullName>
- <xref:System.Half.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Half.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Single.ToString(System.String)?displayProperty=fullName>
- <xref:System.Single.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Single.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Double.ToString(System.String)?displayProperty=fullName>
- <xref:System.Double.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Double.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Decimal.ToString(System.String)?displayProperty=fullName>
- <xref:System.Decimal.ToString(System.String,System.IFormatProvider)?displayProperty=fullName>
- <xref:System.Decimal.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)?displayProperty=fullName>

## <a name="see-also"></a>참고 항목

- [표준 숫자 형식 문자열](../../../../standard/base-types/standard-numeric-format-strings.md)
- [사용자 지정 형식 문자열의 문자 리터럴](../../../../standard/base-types/custom-numeric-format-strings.md#character-literals)

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Numerics.BigInteger.ToString(System.String)`
- `M:System.Numerics.BigInteger.ToString(System.String,System.IFormatProvider)`
- `M:System.Numerics.BigInteger.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Int32.ToString(System.String)`
- `M:System.Int32.ToString(System.String,System.IFormatProvider)`
- `M:System.Int32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.UInt32.ToString(System.String)`
- `M:System.UInt32.ToString(System.String,System.IFormatProvider)`
- `M:System.UInt32.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Byte.ToString(System.String)`
- `M:System.Byte.ToString(System.String,System.IFormatProvider)`
- `M:System.Byte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.SByte.ToString(System.String)`
- `M:System.SByte.ToString(System.String,System.IFormatProvider)`
- `M:System.SByte.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Int16.ToString(System.String)`
- `M:System.Int16.ToString(System.String,System.IFormatProvider)`
- `M:System.Int16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.UInt16.ToString(System.String)`
- `M:System.UInt16.ToString(System.String,System.IFormatProvider)`
- `M:System.UInt16.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Int64.ToString(System.String)`
- `M:System.Int64.ToString(System.String,System.IFormatProvider)`
- `M:System.Int64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.UInt64.ToString(System.String)`
- `M:System.UInt64.ToString(System.String,System.IFormatProvider)`
- `M:System.UInt64.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Half.ToString(System.String)`
- `M:System.Half.ToString(System.String,System.IFormatProvider)`
- `M:System.Half.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Single.ToString(System.String)`
- `M:System.Single.ToString(System.String,System.IFormatProvider)`
- `M:System.Single.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Double.ToString(System.String)`
- `M:System.Double.ToString(System.String,System.IFormatProvider)`
- `M:System.Double.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`
- `M:System.Decimal.ToString(System.String)`
- `M:System.Decimal.ToString(System.String,System.IFormatProvider)`
- `M:System.Decimal.TryFormat(System.Span{System.Char},System.Int32@,System.ReadOnlySpan{System.Char},System.IFormatProvider)`

-->
