---
ms.openlocfilehash: 06d5f48566c239e37355496c3f27163d952602c6
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032579"
---
### <a name="kestrel-connection-adapters-removed"></a><span data-ttu-id="b566d-101">Kestrel: 연결 어댑터가 제거됨</span><span class="sxs-lookup"><span data-stu-id="b566d-101">Kestrel: Connection adapters removed</span></span>

<span data-ttu-id="b566d-102">"pubternal" API를 `public`으로 이동하는 과정의 일부로, `IConnectionAdapter`의 개념이 Kestrel에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b566d-102">As part of the move to move "pubternal" APIs to `public`, the concept of an `IConnectionAdapter` was removed from Kestrel.</span></span> <span data-ttu-id="b566d-103">연결 어댑터는 연결 미들웨어(ASP.NET Core 파이프라인의 HTTP 미들웨어와 유사하지만 하위 수준 연결용)로 대체되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b566d-103">Connection adapters are being replaced with connection middleware (similar to HTTP middleware in the ASP.NET Core pipeline, but for lower-level connections).</span></span> <span data-ttu-id="b566d-104">HTTPS 및 연결 로깅은 연결 어댑터에서 연결 미들웨어로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="b566d-104">HTTPS and connection logging have moved from connection adapters to connection middleware.</span></span> <span data-ttu-id="b566d-105">이러한 확장 메서드는 계속해서 원활하게 작동하지만 구현 세부 정보는 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b566d-105">Those extension methods should continue to work seamlessly, but the implementation details have changed.</span></span>

<span data-ttu-id="b566d-106">자세한 내용은 [dotnet/aspnetcore#11412](https://github.com/dotnet/aspnetcore/pull/11412)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b566d-106">For more information, see [dotnet/aspnetcore#11412](https://github.com/dotnet/aspnetcore/pull/11412).</span></span> <span data-ttu-id="b566d-107">토론은 [dotnet/aspnetcore#11475](https://github.com/dotnet/aspnetcore/issues/11475)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b566d-107">For discussion, see [dotnet/aspnetcore#11475](https://github.com/dotnet/aspnetcore/issues/11475).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b566d-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="b566d-108">Version introduced</span></span>

<span data-ttu-id="b566d-109">3.0</span><span class="sxs-lookup"><span data-stu-id="b566d-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b566d-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="b566d-110">Old behavior</span></span>

<span data-ttu-id="b566d-111">`IConnectionAdapter`를 사용하여 kestrel 확장성 구성 요소를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="b566d-111">Kestrel extensibility components were created using `IConnectionAdapter`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b566d-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="b566d-112">New behavior</span></span>

<span data-ttu-id="b566d-113">kestrel 확장성 구성 요소는 [미들웨어](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f)로 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="b566d-113">Kestrel extensibility components are created as [middleware](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b566d-114">변경 이유</span><span class="sxs-lookup"><span data-stu-id="b566d-114">Reason for change</span></span>

<span data-ttu-id="b566d-115">이 변경은 보다 유연한 확장성 아키텍처를 제공하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b566d-115">This change is intended to provide a more flexible extensibility architecture.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b566d-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="b566d-116">Recommended action</span></span>

<span data-ttu-id="b566d-117">[여기에](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f) 표시된 대로 새 미들웨어 패턴을 사용하도록 `IConnectionAdapter`의 구현을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b566d-117">Convert any implementations of `IConnectionAdapter` to use the new middleware pattern as shown [here](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="category"></a><span data-ttu-id="b566d-118">범주</span><span class="sxs-lookup"><span data-stu-id="b566d-118">Category</span></span>

<span data-ttu-id="b566d-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b566d-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b566d-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b566d-120">Affected APIs</span></span>

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
