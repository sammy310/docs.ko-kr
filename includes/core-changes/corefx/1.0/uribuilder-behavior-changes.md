---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595686"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a>UriBuilder 속성은 더 이상 앞에 선행 문자를 추가하지 않음

<xref:System.UriBuilder.Fragment?displayProperty=nameWithType>는 더 이상 앞에 선행 `#` 문자를 추가하지 않으며 <xref:System.UriBuilder.Query?displayProperty=nameWithType>는 더 이상 앞에 선행 `?` 문자를 추가하지 않습니다(해당 문자가 이미 있는 경우).

#### <a name="change-description"></a>변경 내용 설명

.NET Framework에서 <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> 및 <xref:System.UriBuilder.Query?displayProperty=nameWithType> 속성은 항상 저장되는 값 앞에 각각 `#` 또는 `?` 문자를 추가합니다. 이 동작으로 인해 문자열에 이미 이 선행 문자 중 하나가 포함된 경우 저장된 값에 여러 `#` 또는 `?` 문자가 생성될 수 있습니다. 예를 들어 <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> 값이 `##main`이 될 수 있습니다.

.NET Core 1.0부터 이 속성은 더 이상 저장된 값 앞에 `#` 또는 `?` 문자를 추가하지 않습니다(해당 문자가 문자열의 시작 부분에 이미 있는 경우).

#### <a name="version-introduced"></a>도입된 버전

1.0

#### <a name="recommended-action"></a>권장 조치

속성 값을 설정할 때 더 이상 이 선행 문자를 명시적으로 제거할 필요가 없습니다. 더 이상 추가할 때마다 선행 `#` 또는 `?`를 제거할 필요가 없기 때문에 값을 추가할 경우 이 방법이 특히 유용합니다.

예를 들어 다음 코드 조각은 .NET Framework와 .NET Core의 동작 차이를 보여 줍니다.

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- .NET Framework에서 출력은 `????one=1&two=2&three=3&four=4`입니다.
- .NET Core에서 출력은 `?one=1&two=2&three=3&four=4`입니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
