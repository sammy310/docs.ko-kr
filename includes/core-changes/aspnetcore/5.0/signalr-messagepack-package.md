---
ms.openlocfilehash: ca0792a3fd05d28cecceac1d644e3e4bf64722bc
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345209"
---
### <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a><span data-ttu-id="6830f-101">SignalR: MessagePack 허브 프로토콜이 MessagePack 2.x 패키지로 이동됨</span><span class="sxs-lookup"><span data-stu-id="6830f-101">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>

<span data-ttu-id="6830f-102">ASP.NET Core SignalR [MessagePack 허브 프로토콜](/aspnet/core/signalr/messagepackhubprotocol)은 MessagePack serialization에 대해 [MessagePack NuGet 패키지](https://www.nuget.org/packages/MessagePack)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6830f-102">The ASP.NET Core SignalR [MessagePack Hub Protocol](/aspnet/core/signalr/messagepackhubprotocol) uses the [MessagePack NuGet package](https://www.nuget.org/packages/MessagePack) for MessagePack serialization.</span></span> <span data-ttu-id="6830f-103">ASP.NET Core 5.0은 패키지를 1.x에서 최신 2.x 패키지 버전으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="6830f-103">ASP.NET Core 5.0 upgrades the package from 1.x to the latest 2.x package version.</span></span>

<span data-ttu-id="6830f-104">이 문제에 대한 자세한 내용은 [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6830f-104">For discussion on this issue, see [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6830f-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6830f-105">Version introduced</span></span>

<span data-ttu-id="6830f-106">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="6830f-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6830f-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="6830f-107">Old behavior</span></span>

<span data-ttu-id="6830f-108">ASP.NET Core SignalR은 MessagePack 1.x 패키지를 사용하여 MessagePack 메시지를 직렬화 및 역직렬화했습니다.</span><span class="sxs-lookup"><span data-stu-id="6830f-108">ASP.NET Core SignalR used the MessagePack 1.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6830f-109">새 동작</span><span class="sxs-lookup"><span data-stu-id="6830f-109">New behavior</span></span>

<span data-ttu-id="6830f-110">ASP.NET Core SignalR은 MessagePack 2.x 패키지를 사용하여 MessagePack 메시지를 직렬화 및 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="6830f-110">ASP.NET Core SignalR uses the MessagePack 2.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6830f-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="6830f-111">Reason for change</span></span>

<span data-ttu-id="6830f-112">MessagePack 2.x 패키지의 최신 개선 사항에 유용한 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6830f-112">The latest improvements in the MessagePack 2.x package add useful functionality.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6830f-113">권장 작업</span><span class="sxs-lookup"><span data-stu-id="6830f-113">Recommended action</span></span>

<span data-ttu-id="6830f-114">이러한 주요 변경 내용은 다음 경우에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6830f-114">This breaking change applies when:</span></span>

* <span data-ttu-id="6830f-115"><xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>에서 값을 설정 또는 구성.</span><span class="sxs-lookup"><span data-stu-id="6830f-115">Setting or configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span>
* <span data-ttu-id="6830f-116">MessagePack API를 직접 사용하고 동일한 프로젝트에서 ASP.NET Core SignalR MessagePack 허브 프로토콜을 사용.</span><span class="sxs-lookup"><span data-stu-id="6830f-116">Using the MessagePack APIs directly and using the ASP.NET Core SignalR MessagePack Hub Protocol in the same project.</span></span> <span data-ttu-id="6830f-117">이전 버전 대신 새 버전이 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="6830f-117">The newer version will be loaded instead of the previous version.</span></span>

<span data-ttu-id="6830f-118">패키지 작성자를 위한 마이그레이션 지침은 [MessagePack v1.x에서 MessagePack v2.x로 마이그레이션](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6830f-118">For migration guidance from the package authors, see [Migrating from MessagePack v1.x to MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span></span> <span data-ttu-id="6830f-119">메시지 serialization 및 deserialization의 일부 측면이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6830f-119">Some aspects of message serialization and deserialization are affected.</span></span> <span data-ttu-id="6830f-120">특히 [DateTime 값이 직렬화되는 방식에 대한 동작 변경](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6830f-120">Specifically, there are [behavioral changes to how DateTime values are serialized](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span></span>

#### <a name="category"></a><span data-ttu-id="6830f-121">Category</span><span class="sxs-lookup"><span data-stu-id="6830f-121">Category</span></span>

<span data-ttu-id="6830f-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6830f-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6830f-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6830f-123">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
