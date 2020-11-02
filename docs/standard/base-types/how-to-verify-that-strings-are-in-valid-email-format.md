---
title: '방법: 문자열이 올바른 전자 메일 형식인지 확인'
description: .NET에서 정규식을 통해 문자열이 유효한 전자 메일 형식인지 확인하는 방법의 예제를 찹조하세요.
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET], examples [Visual Basic]
- email [.NET], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
ms.openlocfilehash: 07b8e31e4a0203b87492eb01ab686a1c56f5565d
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889077"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a>방법: 문자열이 올바른 전자 메일 형식인지 확인

다음 예제에서는 정규식을 사용하여 문자열이 올바른 전자 메일 형식인지 확인합니다.

이 정규식은 실제로 메일로 사용될 수 있는 것에 비해 비교적 단순합니다. 정규식을 사용하여 메일의 유효성을 검사하는 것은 메일의 구조가 올바른지 확인하는 데 유용하지만 메일이 실제로 존재하는지 확인하는 작업을 대체하지는 않습니다.

✔️ 작은 정규식을 사용하여 메일의 유효한 구조를 확인합니다.

✔️ 앱 사용자가 제공한 주소로 테스트 메일을 보냅니다.

❌ 메일의 유효성을 검사하는 유일한 방법으로 정규식을 사용하지 마세요.

메일의 구조가 올바른지 확인하는 ‘완벽한’ 정규식을 만들려는 경우 해당 식은 아주 복잡해져서 디버그하거나 개선하기가 매우 어려워집니다. 정규식은 메일의 구조가 올바르게 구성된 경우에도 메일이 존재하는지 확인할 수 없습니다. 메일의 유효성을 검사하는 가장 좋은 방법은 주소로 테스트 메일을 보내는 것입니다.

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a>예제

이 예제에서는 문자열에 유효한 메일 주소가 포함되어 있으면 `IsValidEmail`을 반환하고, 그러지 않으면 `true`를 반환하지만 다른 작업을 수행하지 않는 `false` 메서드를 정의합니다.

전자 메일 주소가 올바른지 확인하기 위해 `IsValidEmail` 메서드는 <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> 정규식 패턴으로 `(@)(.+)$` 메서드를 호출하여 전자 메일 주소에서 도메인 이름을 분리합니다. 세 번째 매개 변수는 일치하는 텍스트를 처리하고 대체하는 메서드를 나타내는 <xref:System.Text.RegularExpressions.MatchEvaluator> 대리자입니다. 정규식 패턴은 다음과 같이 해석됩니다.

| 무늬 | 설명                                                                         |
|---------|-------------------------------------------------------------------------------------|
| `(@)`   | @ 문자를 찾습니다. 이 부분은 첫 번째 캡처 그룹입니다.                           |
| `(.+)`  | 하나 이상의 문자를 찾습니다. 이 부분은 두 번째 캡처 그룹입니다. |
| `$`     | 문자열의 끝 부분에서 일치 항목 찾기를 끝냅니다.                                             |

@ 문자와 함께 도메인 이름이 `DomainMapper` 메서드로 전달됩니다. 이 메서드는 <xref:System.Globalization.IdnMapping> 클래스를 사용하여 US-ASCII 문자 범위 외부에 있는 유니코드 문자를 Punycode로 변환합니다. 이 메서드는 `invalid` 메서드가 도메인 이름에서 잘못된 문자를 발견하는 경우 `True` 플래그를 <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> 로 설정합니다. 메서드는 앞에 @ 기호가 있는 Punycode 도메인 이름을 `IsValidEmail` 메서드에 반환합니다.

> [!TIP]
> 단순한 `(@)(.+)$` 정규식 패턴을 사용하여 도메인을 정규화한 후에 성공 또는 실패를 나타내는 값을 반환하는 것이 좋습니다. 하지만 이 문서의 예제에서는 정규식을 추가로 사용하여 메일의 유효성을 검사하는 방법을 설명합니다. 메일의 유효성을 검사하는 방법과 관계없이, 항상 주소로 테스트 메일을 전송하여 메일이 존재하는지 확인해야 합니다.

그러면 `IsValidEmail` 메서드는 <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> 메서드를 호출하여 주소가 정규식 패턴을 따르는지 확인합니다.

`IsValidEmail` 메서드는 메일 형식이 메일 주소에 유효한지 여부를 확인할 뿐이며 메일이 존재하는지 여부를 확인하지는 않습니다. 또한 `IsValidEmail` 메서드는 최상위 도메인 이름이 조회 작업 시 요구되는 [IANA 루트 영역 데이터베이스](https://www.iana.org/domains/root/db)에 나열된 유효한 도메인 이름인지 확인하지 않습니다.

:::code language="csharp" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/csharp/RegexUtilities.cs":::

:::code language="vb" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/vb/RegexUtilities.vb":::

이 예제에서 정규식 패턴 `^[^@\s]+@[^@\s]+\.[^@\s]+$`는 다음 테이블과 같이 해석됩니다. 정규식은 <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> 플래그를 사용하여 컴파일됩니다.

| 무늬   | 설명                                                                              |
|-----------|------------------------------------------------------------------------------------------|
| `^`       | 문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.                                              |
| `[^@\s]+` | @ 문자나 공백 이외의 다른 문자를 하나 이상 찾습니다. |
| `@`       | @ 문자를 찾습니다.                                                                   |
| `[^@\s]+` | @ 문자나 공백 이외의 다른 문자를 하나 이상 찾습니다. |
| `\.`      | 마침표 문자 하나를 찾습니다.                                                         |
| `[^@\s]+` | @ 문자나 공백 이외의 다른 문자를 하나 이상 찾습니다. |
| `$`       | 문자열의 끝 부분에서 일치 항목 찾기를 끝냅니다.                                                  |

> [!IMPORTANT]
> 이 정규식은 유효한 메일 주소의 모든 측면을 포괄하기 위한 것이 아닙니다. 필요에 따라 확장하는 예제로 제공됩니다.

## <a name="see-also"></a>참조

- [.NET 정규식](regular-expressions.md)
- [어느 정도까지 메일 주소의 유효성을 검사해야 하나요?](https://softwareengineering.stackexchange.com/questions/78353/how-far-should-one-take-e-mail-address-validation#78363)
