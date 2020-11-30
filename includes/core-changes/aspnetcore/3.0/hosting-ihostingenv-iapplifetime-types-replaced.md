---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032519"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a>호스팅: IHostingEnvironment 및 IApplicationLifetime 형식이 사용되지 않는 것으로 표시되고 대체됨

기존 `IHostingEnvironment` 및 `IApplicationLifetime` 형식을 대체하기 위해 새로운 형식이 도입되었습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`Microsoft.Extensions.Hosting` 및 `Microsoft.AspNetCore.Hosting`과는 다른 두 가지(`IHostingEnvironment` 및 `IApplicationLifetime`) 형식이 있습니다.

#### <a name="new-behavior"></a>새 동작

이전 형식은 사용되지 않음으로 표시되었으며 새 형식으로 대체되었습니다.

#### <a name="reason-for-change"></a>변경 이유

ASP.NET Core 2.1에 `Microsoft.Extensions.Hosting`이 도입되었을 때 `IHostingEnvironment` 및 `IApplicationLifetime`과 같은 일부 형식이 `Microsoft.AspNetCore.Hosting`에서 복사되었습니다. 일부 ASP.NET Core 3.0 변경으로 인해 앱에 `Microsoft.Extensions.Hosting` 및 `Microsoft.AspNetCore.Hosting` 네임스페이스가 모두 포함됩니다. 이러한 중복 형식을 사용하면 네임스페이스가 모두 참조될 때 "모호한 참조" 컴파일러 오류가 발생합니다.

#### <a name="recommended-action"></a>권장 조치

이전 형식의 사용을 다음과 같이 새로 도입된 형식으로 대체했습니다.

**사용되지 않는 형식(경고):**

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

**새 형식:**

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

새 `IHostEnvironment` `IsDevelopment` 및 `IsProduction` 확장 메서드는 `Microsoft.Extensions.Hosting` 네임스페이스에 있습니다. 해당 네임스페이스를 프로젝트에 추가해야 할 수도 있습니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
