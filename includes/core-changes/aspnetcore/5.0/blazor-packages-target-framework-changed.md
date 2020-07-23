---
ms.openlocfilehash: 17a167e5245914329195d61ab45ae2d8ecb617d6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416262"
---
### <a name="blazor-target-framework-of-nuget-packages-changed"></a>Blazor: NuGet 패키지의 대상 프레임워크가 변경됨

Blazor 3.2 WebAssembly 프로젝트는 .NET Standard 2.1(`<TargetFramework>netstandard2.1</TargetFramework>`)을 대상으로 컴파일되었습니다. ASP.NET Core 5.0에서는 Blazor Server 및 Blazor WebAssembly 프로젝트가 모두 .NET 5.0(`<TargetFramework>net5.0</TargetFramework>`)을 대상으로 합니다. 대상 프레임워크 변경에 맞추기 위해 다음 Blazor 패키지는 더 이상 .NET Standard 2.1을 대상으로 하지 않습니다.

* [Microsoft.AspNetCore.Components](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)
* [Microsoft.AspNetCore.Components.Authorization](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [Microsoft.AspNetCore.Components.Forms](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [Microsoft.AspNetCore.Components.Web](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)
* [Microsoft.AspNetCore.Components.WebAssembly](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [Microsoft.AspNetCore.Components.WebAssembly.Authentication](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [Microsoft.JSInterop](https://www.nuget.org/packages/Microsoft.JSInterop)
* [Microsoft.JSInterop.WebAssembly](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [Microsoft.Authentication.WebAssembly.Msal](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 7

#### <a name="old-behavior"></a>이전 동작

Blazor 3.1 및 3.2에서는 패키지가 .NET Standard 2.1 및 .NET Core 3.1을 대상으로 합니다.

#### <a name="new-behavior"></a>새 동작

ASP.NET Core 5.0에서는 패키지가 .NET 5.0을 대상으로 합니다.

#### <a name="reason-for-change"></a>변경 이유

.NET 대상 프레임워크 요구 사항에 맞게 변경되었습니다.

#### <a name="recommended-action"></a>권장 조치

Blazor 3.2 WebAssembly 프로젝트는 패키지 참조를 5.x.x로 업데이트하는 과정의 일환으로 .NET 5.0을 대상으로 해야 합니다. 해당 패키지 중 하나를 참조하는 라이브러리는 요구 사항에 따라 .NET 5.0을 대상으로 하거나 다중 대상을 지정할 수 있습니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!--

#### Affected APIs

Not detectable via API analysis

-->
