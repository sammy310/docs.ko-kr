---
ms.openlocfilehash: 1b4b0aba3ea24682ae972bf283ac387692c83781
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901739"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a><span data-ttu-id="ef890-101">HTTP: DefaultHttpContext 확장성이 제거됨</span><span class="sxs-lookup"><span data-stu-id="ef890-101">HTTP: DefaultHttpContext extensibility removed</span></span>

<span data-ttu-id="ef890-102">ASP.NET Core 3.0 성능 향상의 일환으로 `DefaultHttpContext`의 확장성이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef890-102">As part of ASP.NET Core 3.0 performance improvements, the extensibility of `DefaultHttpContext` was removed.</span></span> <span data-ttu-id="ef890-103">클래스는 이제 `sealed`입니다.</span><span class="sxs-lookup"><span data-stu-id="ef890-103">The class is now `sealed`.</span></span> <span data-ttu-id="ef890-104">자세한 내용은 [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef890-104">For more information, see [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).</span></span>

<span data-ttu-id="ef890-105">단위 테스트에서 `Mock<DefaultHttpContext>`를 사용하는 경우, 대신 `Mock<HttpContext>`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ef890-105">If your unit tests use `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` instead.</span></span>

<span data-ttu-id="ef890-106">토론은 [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef890-106">For discussion, see [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ef890-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="ef890-107">Version introduced</span></span>

<span data-ttu-id="ef890-108">3.0</span><span class="sxs-lookup"><span data-stu-id="ef890-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ef890-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="ef890-109">Old behavior</span></span>

<span data-ttu-id="ef890-110">클래스는 `DefaultHttpContext`에서 파생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef890-110">Classes can derive from `DefaultHttpContext`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ef890-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="ef890-111">New behavior</span></span>

<span data-ttu-id="ef890-112">클래스는 `DefaultHttpContext`에서 파생될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef890-112">Classes can't derive from `DefaultHttpContext`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ef890-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="ef890-113">Reason for change</span></span>

<span data-ttu-id="ef890-114">확장성은 처음에는 `HttpContext`의 풀링을 허용하기 위해 제공되었지만 불필요 한 복잡성을 야기하고 기타 최적화를 방해했습니다.</span><span class="sxs-lookup"><span data-stu-id="ef890-114">The extensibility was provided initially to allow pooling of the `HttpContext`, but it introduced unnecessary complexity and impeded other optimizations.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ef890-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="ef890-115">Recommended action</span></span>

<span data-ttu-id="ef890-116">단위 테스트에서 `Mock<DefaultHttpContext>`를 사용하는 경우, 대신 `Mock<HttpContext>`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ef890-116">If you're using `Mock<DefaultHttpContext>` in your unit tests, begin using `Mock<HttpContext>` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="ef890-117">범주</span><span class="sxs-lookup"><span data-stu-id="ef890-117">Category</span></span>

<span data-ttu-id="ef890-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ef890-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ef890-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ef890-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
