---
title: .NET에서 형식이 지정된 데이터 표시 및 유지 모범 사례
description: .NET 애플리케이션에서 숫자 및 날짜 데이터를 효율적으로 표시하고 유지하는 방법을 알아봅니다.
ms.date: 05/01/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.openlocfilehash: 83a491f6c843225c6242a343fe4132c2ce7caa74
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93403479"
---
# <a name="best-practices-for-displaying-and-persisting-formatted-data"></a>형식이 지정된 데이터 표시 및 유지 모범 사례

이 문서에서는 숫자 데이터 및 날짜/시간 데이터와 같은 형식이 지정된 데이터를 표시 및 스토리지를 위해 처리하는 방법을 살펴봅니다.

.NET을 사용하여 개발할 때는 문화권이 구분되는 형식 지정을 사용하여 사용자 인터페이스에서 숫자 및 날짜와 같이 문자열이 아닌 데이터를 표시합니다. [고정 문화권](xref:System.Globalization.CultureInfo.InvariantCulture)과 함께 형식 지정을 사용하여 문자열 양식에서 문자열이 아닌 데이터를 유지합니다. 문자열 양식에서 숫자 또는 날짜 및 시간 데이터를 유지하는 데 문화권이 구분되는 형식 지정을 사용하지 마세요.

## <a name="displaying-formatted-data"></a>형식이 지정된 데이터 표시

숫자와 날짜 및 시간과 같은 문자열이 아닌 데이터를 사용자에게 표시할 때 사용자의 문화권 설정을 사용하여 형식을 지정합니다. 기본적으로 다음 항목은 모두 서식 지정 작업에서 현재 스레드 문화권을 사용합니다.

- [C#](../../csharp/language-reference/tokens/interpolated.md) 및 [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) 컴파일러에서 지원하는 보간된 문자열입니다.
- [C#](../../csharp/language-reference/operators/addition-operator.md#string-concatenation) 또는 [Visual Basic](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) 연결 연산자를 사용하거나 직접 <xref:System.String.Concat%2A?displayProperty=nameWithType> 메서드를 호출하는 문자열 연결 연산자입니다.
- <xref:System.String.Format%2A?displayProperty=nameWithType> 메서드
- 숫자 형식과 날짜 및 시간 형식의 `ToString` 메서드.

지정된 문화권의 규칙 또는 [고정 문화권](xref:System.Globalization.CultureInfo.InvariantCulture)을 사용하여 문자열의 서식을 지정해야 함을 명시적으로 지정하려면 다음을 수행합니다.

- <xref:System.String.Format%2A?displayProperty=nameWithType> 및 `ToString` 메서드를 사용하는 경우 <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 또는 <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType>과 같이 `provider` 매개 변수가 있는 오버로드를 호출하고 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> 속성, 원하는 문화권을 나타내는 <xref:System.Globalization.CultureInfo> 인스턴스 또는 <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType> 속성을 전달합니다.

- 문자열 연결의 경우 컴파일러에서 암시적 변환을 수행하지 못하게 합니다. 대신 `provider` 매개 변수가 있는 `ToString` 오버로드를 호출하여 명시적 변환을 수행합니다. 예를 들어 컴파일러는 다음 코드에서 <xref:System.Double> 값을 문자열로 변환할 때 암시적으로 현재 문화권을 사용합니다.

  [!code-csharp[Implicit String Conversion](./snippets/best-practices-strings/csharp/tostring/Program.cs#1)]
  [!code-vb[Implicit String Conversion](./snippets/best-practices-strings/vb/tostring/Program.vb#1)]

  대신, 다음 코드와 같이 <xref:System.Double.ToString(System.IFormatProvider)?displayProperty=nameWithType> 메서드를 호출하여 변환에 사용되는 서식 지정 규칙을 사용하는 문화권을 명시적으로 지정할 수 있습니다.

  [!code-csharp[Explicit String Conversion](./snippets/best-practices-strings/csharp/tostring/Program.cs#2)]
  [!code-vb[Implicit String Conversion](./snippets/best-practices-strings/vb/tostring/Program.vb#2)]

- 문자열 보간의 경우, 보간된 문자열을 <xref:System.String> 인스턴스에 할당하는 대신 <xref:System.FormattableString>에 할당합니다. 그런 다음, 해당 <xref:System.FormattableString.ToString?displayProperty=nameWithType> 메서드를 호출하여 현재 문화권의 규칙을 반영하는 결과 문자열을 생성하거나 <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> 메서드를 호출하여 지정된 문화권의 규칙을 반영하는 결과 문자열을 생성할 수 있습니다. 서식 지정 가능 문자열을 정적 <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> 메서드에 전달하여 고정 문화권의 규칙을 반영하는 결과 문자열을 생성할 수도 있습니다. 다음 예제에서 이 방법을 보여 줍니다. (이 예제의 출력에는 en-US의 현재 문화권이 반영됩니다.)

  [!code-csharp[String interpolation](./snippets/best-practices-strings/csharp/formattable/Program.cs)]
  [!code-vb[String interpolation](./snippets/best-practices-strings/vb/formattable/Program.vb)]

## <a name="persisting-formatted-data"></a>형식이 지정된 데이터 유지

문자열이 아닌 데이터를 이진 데이터 또는 형식이 지정된 데이터로 유지할 수 있습니다. 서식이 지정된 데이터로 저장하는 경우 `provider` 매개 변수를 포함하는 서식 지정 메서드 오버로드를 호출하고 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> 속성에 전달해야 합니다. 고정 문화권은 문화권 및 컴퓨터와 관계없는 형식이 지정된 데이터에 대해 일관된 형식을 제공합니다. 반대로 고정 문화권이 아닌 문화권을 사용하여 형식이 지정된 영구 데이터에는 많은 제한 사항이 있습니다.

- 다른 문화권이 포함된 시스템에서 데이터를 검색하거나 현재 시스템의 사용자가 현재 문화권을 변경하고 데이터를 검색하려고 하면 데이터를 사용하지 못할 수 있습니다.
- 특정 컴퓨터의 문화권 속성은 표준 값과 다를 수 있습니다. 언제든지 사용자가 문화권 구분 표시 설정을 사용자 지정할 수 있습니다. 이로 인해 사용자가 문화권 설정을 사용자 지정한 후에는 시스템에 저장된 형식이 지정된 데이터를 읽지 못할 수 있습니다. 컴퓨터 간에 형식이 지정된 데이터의 이식성은 훨씬 더 제한적일 수 있습니다.
- 숫자 또는 날짜/시간의 형식 지정을 관리하는 국제, 지역 또는 국가 표준은 시간에 지나면서 변경되고 이들 변경은 Windows 운영 체제 업데이트에 통합됩니다. 형식 지정 규칙이 변경될 때 이전 규칙을 사용하여 형식이 지정된 데이터를 읽지 못하게 될 수 있습니다.

다음 예제에서는 문화권 구분 형식 지정을 사용하여 데이터를 유지함으로 인해 제한된 이식성을 보여 줍니다. 예제에서는 날짜 및 시간 값 배열을 파일에 저장합니다. 이들 값은 영어(미국) 문화권의 규칙을 사용하여 형식이 지정됩니다. 애플리케이션이 현재 스레드 문화권을 프랑스어(스위스)로 변경하고 나면 현재 문화권의 형식 지정 규칙을 사용하여 저장된 값을 읽으려고 합니다. 두 데이터 항목을 읽으려는 시도로 인해 <xref:System.FormatException> 예외가 throw되고 날짜 배열에는 <xref:System.DateTime.MinValue>와 같은 잘못된 두 가지 요소가 포함됩니다.

[!code-csharp[Conceptual.Strings.BestPractices#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/persistence.cs#21)]
[!code-vb[Conceptual.Strings.BestPractices#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/persistence.vb#21)]

그러나 <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 및 <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>에 대한 호출에서 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> 속성을 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>로 바꾸면 다음 출력과 같이 영구 날짜 및 시간 데이터가 성공적으로 복원됩니다.

```console
06.05.1758 21:26
05.05.1818 07:19
22.04.1870 23:54
08.09.1890 06:47
18.02.1905 15:12
```
