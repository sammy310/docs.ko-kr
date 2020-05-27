---
ms.openlocfilehash: fb23418816abcae125106c93b339a546aa9bc2ee
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720994"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="6aa2e-101">Kestrel: 전송 추상화 제거 및 공개</span><span class="sxs-lookup"><span data-stu-id="6aa2e-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="6aa2e-102">"pubternal" API에서 벗어나 이동하는 과정에서 Kestrel 전송 계층 API는 `Microsoft.AspNetCore.Connections.Abstractions` 라이브러리의 공용 인터페이스로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2e-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6aa2e-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6aa2e-103">Version introduced</span></span>

<span data-ttu-id="6aa2e-104">3.0</span><span class="sxs-lookup"><span data-stu-id="6aa2e-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6aa2e-105">이전 동작</span><span class="sxs-lookup"><span data-stu-id="6aa2e-105">Old behavior</span></span>

- <span data-ttu-id="6aa2e-106">전송 관련 추상화는 `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` 라이브러리에서 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2e-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="6aa2e-107">`ListenOptions.NoDelay` 속성을 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2e-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6aa2e-108">새 동작</span><span class="sxs-lookup"><span data-stu-id="6aa2e-108">New behavior</span></span>

- <span data-ttu-id="6aa2e-109">`IConnectionListener` 인터페이스는 `...Transport.Abstractions` 라이브러리에서 가장 많이 사용되는 기능을 노출하기 위해 `Microsoft.AspNetCore.Connections.Abstractions` 라이브러리에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2e-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="6aa2e-110">이제 `NoDelay`는 전송 옵션(`LibuvTransportOptions` 및 `SocketTransportOptions`)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2e-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="6aa2e-111">`SchedulingMode`를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2e-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6aa2e-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="6aa2e-112">Reason for change</span></span>

<span data-ttu-id="6aa2e-113">ASP.NET Core 3.0은 "pubternal" API에서 벗어나 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa2e-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6aa2e-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="6aa2e-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="6aa2e-115">범주</span><span class="sxs-lookup"><span data-stu-id="6aa2e-115">Category</span></span>

<span data-ttu-id="6aa2e-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6aa2e-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6aa2e-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6aa2e-117">Affected APIs</span></span>

<span data-ttu-id="6aa2e-118">없음</span><span class="sxs-lookup"><span data-stu-id="6aa2e-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
