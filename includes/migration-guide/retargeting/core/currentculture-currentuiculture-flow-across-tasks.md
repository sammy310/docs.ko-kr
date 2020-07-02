---
ms.openlocfilehash: 78faa5f4008b41bac75c94ce09a58c8227e5b485
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614671"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a>CurrentCulture 및 CurrentUICulture가 작업에 걸쳐 전달됨

#### <a name="details"></a>설명

.NET Framework 4.6부터 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>은 스레드의 <xref:System.Threading.ExecutionContext?displayProperty=fullName>에 저장되며 비동기 작업을 통해 전달됩니다. 즉, <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>의 변경은 이후 비동기적으로 실행되는 작업에서 반영됩니다. 이는 모든 비동기 작업에서 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>을 다시 설정하는 이전 .NET Framework 버전의 동작과 다릅니다.

#### <a name="suggestion"></a>제안 해결 방법

이 변경의 영향을 받는 앱은 비동기 작업에서 원하는 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>을 첫 번째 작업으로 명확하게 설정하여 문제를 해결할 수 있습니다. 또는 다음 호환성 스위치를 설정하여 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>을 전달하지 않는 이전 동작을 옵트인할 수 있습니다.

```csharp
AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);
```

이 문제는 .NET Framework 4.6.2의 WPF에서 해결되었습니다. 또한 [KB 3139549](https://support.microsoft.com/kb/3139549)를 통해 .NET Frameworks 4.6, 4.6.1에서 해결되었습니다. .NET Framework 4.6 이상을 대상으로 하는 애플리케이션은 디스패처 작업 전반에 걸쳐 WPF 애플리케이션(<xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>)에서 올바른 동작을 자동으로 유지합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType>
