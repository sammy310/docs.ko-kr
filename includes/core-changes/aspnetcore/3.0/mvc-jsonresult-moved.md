---
ms.openlocfilehash: 96c2a32dd7cca91e965601d715bbd4625bba439a
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032620"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a><span data-ttu-id="2aa1b-101">MVC: JsonResult를 Microsoft.AspNetCore.Mvc.Core로 이동</span><span class="sxs-lookup"><span data-stu-id="2aa1b-101">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>

<span data-ttu-id="2aa1b-102">`JsonResult`가 `Microsoft.AspNetCore.Mvc.Core` 어셈블리로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-102">`JsonResult` has moved to the `Microsoft.AspNetCore.Mvc.Core` assembly.</span></span> <span data-ttu-id="2aa1b-103">이 형식은 [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json)에서 정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-103">This type used to be defined in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span></span> <span data-ttu-id="2aa1b-104">대부분 사용자의 문제를 해결하기 위해 어셈블리 수준 [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) 특성이 `Microsoft.AspNetCore.Mvc.Formatters.Json`에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-104">An assembly-level [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) attribute was added to `Microsoft.AspNetCore.Mvc.Formatters.Json` to address this issue for the majority of users.</span></span> <span data-ttu-id="2aa1b-105">타사 라이브러리를 사용하는 앱에서 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-105">Apps that use third-party libraries may encounter issues.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2aa1b-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="2aa1b-106">Version introduced</span></span>

<span data-ttu-id="2aa1b-107">3.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="2aa1b-107">3.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2aa1b-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="2aa1b-108">Old behavior</span></span>

<span data-ttu-id="2aa1b-109">2\.2 기반 라이브러리를 사용하는 앱이 성공적으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-109">An app using a 2.2-based library builds successfully.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="2aa1b-110">새 동작</span><span class="sxs-lookup"><span data-stu-id="2aa1b-110">New behavior</span></span>

<span data-ttu-id="2aa1b-111">2\.2 기반 라이브러리를 사용하는 앱이 컴파일에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-111">An app using a 2.2-based library fails compilation.</span></span> <span data-ttu-id="2aa1b-112">다음 텍스트의 변형을 포함하는 오류가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-112">An error containing a variation of the following text is provided:</span></span>

```output
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

<span data-ttu-id="2aa1b-113">이러한 문제의 예는 [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-113">For an example of such an issue, see [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2aa1b-114">변경 이유</span><span class="sxs-lookup"><span data-stu-id="2aa1b-114">Reason for change</span></span>

<span data-ttu-id="2aa1b-115">플랫폼 수준이 [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325)에서 설명하는 것과 같이 ASP.NET Core의 컴퍼지션으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-115">Platform-level changes to the composition of ASP.NET Core as described at [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2aa1b-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="2aa1b-116">Recommended action</span></span>

<span data-ttu-id="2aa1b-117">`Microsoft.AspNetCore.Mvc.Formatters.Json` 2.2 버전에 대해 컴파일된 라이브러리를 다시 컴파일하여 모든 소비자에 대한 문제를 해결해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-117">Libraries compiled against the 2.2 version of `Microsoft.AspNetCore.Mvc.Formatters.Json` may need to recompile to address the problem for all consumers.</span></span> <span data-ttu-id="2aa1b-118">영향을 받는 경우 라이브러리 작성자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-118">If affected, contact the library author.</span></span> <span data-ttu-id="2aa1b-119">ASP.NET Core 3.0을 대상으로 하는 라이브러리의 재컴파일을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="2aa1b-119">Request recompilation of the library to target ASP.NET Core 3.0.</span></span>

#### <a name="category"></a><span data-ttu-id="2aa1b-120">범주</span><span class="sxs-lookup"><span data-stu-id="2aa1b-120">Category</span></span>

<span data-ttu-id="2aa1b-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2aa1b-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2aa1b-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2aa1b-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
