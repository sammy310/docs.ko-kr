---
title: '호환성이 손상되는 변경: Unix에서 비ASCII 문자를 포함하는 URI 경로가 올바르게 구문 분석됨'
description: ASCII가 아닌 문자를 포함하는 절대 URI 경로가 Unix 플랫폼에서 올바르게 구문 분석되는 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 94de4e0eb94a11153d873871d4003422a4286a0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759628"
---
# <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a>Unix에서 비ASCII 문자를 포함하는 URI 경로가 올바르게 구문 분석됨

비ASCII 문자를 포함하는 절대 URI 경로가 이제 Unix 플랫폼에서 올바르게 구문 분석되도록 <xref:System.Uri?displayProperty=fullName> 클래스의 버그가 수정되었습니다.

## <a name="change-description"></a>변경 내용 설명

이전 버전의 .NET에서는 비ASCII 문자를 포함하는 절대 URI 경로가 Unix 플랫폼에서 잘못 구문 분석되고 경로 세그먼트가 중복됩니다. 절대 경로는 “/”로 시작하는 경로입니다. .NET 5.0에서는 구문 분석 문제가 해결되었습니다. 이전 버전의 .NET에서 .NET 5.0 이상으로 이동하는 경우 <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType>, 기타 <xref:System.Uri> 멤버에서 다른 값이 생성됩니다.

Unix에서 실행할 때 다음 코드의 출력을 살펴봅니다.

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

이전 .NET 버전에서의 출력:

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

.NET 5.0 이상 버전에서의 출력:

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

중복된 경로 세그먼트를 예상해서 고려하는 코드가 있을 경우 해당 코드를 제거할 수 있습니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Uri?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
