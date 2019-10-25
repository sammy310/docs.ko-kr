---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394147"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a>Razor: 런타임 컴파일이 패키지로 이동됨

Razor 뷰 및 Razor Pages의 런타임 컴파일을 지원하기 위해 별도의 패키지로 이동되었습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

추가 패키지 없이 런타임 컴파일을 사용할 수 있습니다.

#### <a name="new-behavior"></a>새 동작

기능이 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 패키지로 이동되었습니다.

런타임 컴파일을 지원하기 위해 이전에 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`에서 다음 API를 사용할 수 있었습니다. 이제 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`를 통해 API를 사용할 수 있습니다.

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

또한 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange`가 제거되었습니다. 파일 변경 시 재컴파일은 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 패키지를 참조하여 기본적으로 사용하도록 설정됩니다.

#### <a name="reason-for-change"></a>변경 이유

이 변경은 Roslyn에서 ASP.NET Core 공유 프레임워크 종속성을 제거하기 위해 필요했습니다.

#### <a name="recommended-action"></a>권장 작업

Razor 파일의 런타임 컴파일 또는 재컴파일이 필요한 앱은 다음 단계를 수행해야 합니다.

1. `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 패키지에 대한 참조를 추가합니다.
1. `AddMvcRazorRuntimeCompilation`에 대한 호출을 포함하도록 프로젝트의 `Startup.ConfigureServices` 메서드를 업데이트합니다. 예를 들어 `Startup.ConfigureServices`에서는 다음과 같습니다.

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
