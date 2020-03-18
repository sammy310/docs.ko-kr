---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394402"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a><span data-ttu-id="54b07-101">MVC: 웹 API 호환성 shim이 제거됨</span><span class="sxs-lookup"><span data-stu-id="54b07-101">MVC: Web API compatibility shim removed</span></span>

<span data-ttu-id="54b07-102">ASP.NET Core 3.0부터는 `Microsoft.AspNetCore.Mvc.WebApiCompatShim` 패키지를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54b07-102">Starting with ASP.NET Core 3.0, the `Microsoft.AspNetCore.Mvc.WebApiCompatShim` package is no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="54b07-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="54b07-103">Change description</span></span>

<span data-ttu-id="54b07-104">`Microsoft.AspNetCore.Mvc.WebApiCompatShim`(WebApiCompatShim) 패키지는 ASP.NET Core에서 ASP.NET 4.x Web API 2와의 부분 호환성을 제공하여 기존 Web API 구현을 ASP.NET Core로 마이그레이션하는 것을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="54b07-104">The `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) package provides partial compatibility in ASP.NET Core with ASP.NET 4.x Web API 2 to simplify migrating existing Web API implementations to ASP.NET Core.</span></span> <span data-ttu-id="54b07-105">그러나 WebApiCompatShim을 사용하는 앱은 최신 ASP.NET Core 릴리스에서 제공되는 API 관련 기능의 이점을 활용하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="54b07-105">However, apps using the WebApiCompatShim don't benefit from the API-related features shipping in recent ASP.NET Core releases.</span></span> <span data-ttu-id="54b07-106">이러한 기능에는 향상된 Open API 사양 생성, 표준화된 오류 처리 및 클라이언트 코드 생성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="54b07-106">Such features include improved Open API specification generation, standardized error handling, and client code generation.</span></span> <span data-ttu-id="54b07-107">3\.0에서 API 노력에 더 집중하기 위해 WebApiCompatShim이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="54b07-107">To better focus the API efforts in 3.0, WebApiCompatShim was removed.</span></span> <span data-ttu-id="54b07-108">WebApiCompatShim을 사용하는 기존 앱은 최신 `[ApiController]` 모델로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54b07-108">Existing apps using the WebApiCompatShim should migrate to the newer `[ApiController]` model.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="54b07-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="54b07-109">Version introduced</span></span>

<span data-ttu-id="54b07-110">3.0</span><span class="sxs-lookup"><span data-stu-id="54b07-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="54b07-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="54b07-111">Reason for change</span></span>

<span data-ttu-id="54b07-112">Web API 호환성 shim은 마이그레이션 도구였습니다.</span><span class="sxs-lookup"><span data-stu-id="54b07-112">The Web API compatibility shim was a migration tool.</span></span> <span data-ttu-id="54b07-113">ASP.NET Core에 추가된 새로운 기능에 대한 사용자 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="54b07-113">It restricts user access to new functionality added in ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="54b07-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="54b07-114">Recommended action</span></span>

<span data-ttu-id="54b07-115">이 shim의 사용을 제거하고 ASP.NET Core 자체의 유사한 기능으로 직접 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="54b07-115">Remove usage of this shim and migrate directly to the similar functionality in ASP.NET Core itself.</span></span>

#### <a name="category"></a><span data-ttu-id="54b07-116">범주</span><span class="sxs-lookup"><span data-stu-id="54b07-116">Category</span></span>

<span data-ttu-id="54b07-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="54b07-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="54b07-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="54b07-118">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
