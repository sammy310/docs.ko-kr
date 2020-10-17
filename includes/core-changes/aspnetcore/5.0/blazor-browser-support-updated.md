---
ms.openlocfilehash: 584014572ab799e1e3ab2f02c9fbf4fe6b0c17e7
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804930"
---
### <a name="blazor-updated-browser-support"></a>Blazor: 업데이트된 브라우저 지원

ASP.NET Core 5.0에는 [새로운 Blazor 기능](https://github.com/dotnet/aspnetcore/issues/21514)이 도입되었으며, 일부 기능은 이전 브라우저와 호환되지 않습니다. 이에 따라 ASP.NET Core 5.0의 Blazor에서 지원되는 브라우저 목록이 업데이트되었습니다.

자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

5.0

#### <a name="old-behavior"></a>이전 동작

Blazor Server가 충분한 보충 기능으로 Microsoft Internet Explorer 11을 지원합니다. Blazor Server와 Blazor WebAssembly가 [Microsoft Edge 레거시](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)에서도 작동합니다.

#### <a name="new-behavior"></a>새 동작

ASP.NET Core 5.0의 Blazor Server가 Microsoft Internet Explorer 11에서 지원되지 않습니다. Blazor Server와 Blazor WebAssembly가 Microsoft Edge 레거시에서 완전히 작동하지 않습니다.

#### <a name="reason-for-change"></a>변경 이유

ASP.NET Core 5.0의 새로운 Blazor 기능은 이전 브라우저와 호환되지 않으며, 이전 브라우저 사용이 감소하고 있습니다. 자세한 내용은 다음 자료를 참조하세요.

* [Microsoft Edge 레거시에 대한 Windows 지원도 2021년 3월 9일에 종료됩니다.](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [Microsoft Internet Explorer 11에 대한 Microsoft 365 앱과 서비스 지원이 2021년 8월 17일에 종료됩니다.](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

#### <a name="recommended-action"></a>권장 조치

이전 브라우저에서 [Chromium 기반의 새로운 Microsoft Edge](https://www.microsoft.com/edge)로 업그레이드합니다. 이전 브라우저를 지원해야 하는 Blazor 앱의 경우 ASP.NET Core 3.1을 사용합니다. ASP.NET Core 3.1에서는 Blazor 지원 브라우저 목록이 변경되지 않았으며 [지원되는 플랫폼](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1)에 문서화되어 있습니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!--

#### Affected APIs

Not detectable via API analysis

-->
