---
title: ASP.NET SignalR 및 ASP.NET Core SignalR 비교
description: ASP.NET Core SignalR는 선행 ASP.NET SignalR와 어떻게 다릅니까?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 89236bd0272c8f20cf9838dddefeb9afee1f3d93
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401694"
---
# <a name="compare-aspnet-signalr-and-aspnet-core-signalr"></a><span data-ttu-id="371bc-103">ASP.NET SignalR 및 ASP.NET Core SignalR 비교</span><span class="sxs-lookup"><span data-stu-id="371bc-103">Compare ASP.NET SignalR and ASP.NET Core SignalR</span></span>

<span data-ttu-id="371bc-104">ASP.NET Core SignalR는 ASP.NET SignalR를 사용 하는 클라이언트 또는 서버와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-104">ASP.NET Core SignalR is incompatible with clients or servers using ASP.NET SignalR.</span></span> <span data-ttu-id="371bc-105">ASP.NET Core SignalR을 사용 하려면 클라이언트와 서버를 모두 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-105">You'll need to update both clients and server to use ASP.NET Core SignalR.</span></span> <span data-ttu-id="371bc-106">일부 차이점은이 섹션에 설명 되어 있지만 전체 목록은 [문서](/aspnet/core/signalr/version-differences)에서 사용할 수 있습니다. ASP.NET Core SignalR에는 .NET Core 2.1 이상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-106">Some differences are described in this section, while the full list is available in the [docs](/aspnet/core/signalr/version-differences). ASP.NET Core SignalR requires .NET Core 2.1 or greater.</span></span>

## <a name="feature-differences"></a><span data-ttu-id="371bc-107">기능 차이점</span><span class="sxs-lookup"><span data-stu-id="371bc-107">Feature differences</span></span>

- <span data-ttu-id="371bc-108">ASP.NET SignalR에서 자동으로 삭제 된 연결을 다시 연결 하려고 시도 합니다. 이 동작은 ASP.NET Core SignalR 클라이언트에 옵트인 (opt in) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-108">ASP.NET SignalR automatically attempts to reconnect dropped connections; this behavior is opt-in for ASP.NET Core SignalR clients</span></span>
- <span data-ttu-id="371bc-109">두 프레임 워크 모두 JSON을 지원 합니다. 또한 ASP.NET Core SignalR는 MessagePack를 기반으로 하는 이진 프로토콜을 지원 하며 사용자 지정 프로토콜을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-109">Both frameworks support JSON; ASP.NET Core SignalR also supports a binary protocol based on MessagePack, and custom protocols can be created.</span></span>
- <span data-ttu-id="371bc-110">ASP.NET SignalR에서 지 원하는 무한 프레임 전송은 ASP.NET Core SignalR에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-110">The Forever Frame transport, supported by ASP.NET SignalR, isn't supported in ASP.NET Core SignalR.</span></span>
- <span data-ttu-id="371bc-111">ASP.NET Core SignalR는 `services.AddSignalR()` 각각 및에서 및를 추가 하 여 구성 해야 합니다 `app.UseEndpoints` `Startup.ConfigureServices` `Startup.Configure` .</span><span class="sxs-lookup"><span data-stu-id="371bc-111">ASP.NET Core SignalR must be configured by adding `services.AddSignalR()` and `app.UseEndpoints` in `Startup.ConfigureServices` and `Startup.Configure`, respectively.</span></span>
- <span data-ttu-id="371bc-112">ASP.NET Core SignalR에 고정 세션이 필요 합니다. ASP.NET SignalR는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-112">ASP.NET Core SignalR requires sticky sessions; ASP.NET SignalR doesn't.</span></span>
- <span data-ttu-id="371bc-113">ASP.NET Core는 연결 모델을 단순화 합니다. 단일 허브에 대 한 연결만 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-113">ASP.NET Core simplifies the connection model; connections are only made to a single hub.</span></span>
- <span data-ttu-id="371bc-114">ASP.NET Core SignalR는 허브에서 클라이언트로의 스트리밍 데이터를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-114">ASP.NET Core SignalR supports streaming data from the hub to the client.</span></span>
- <span data-ttu-id="371bc-115">ASP.NET Core SignalR는 클라이언트와 허브 간의 상태 전달을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-115">ASP.NET Core SignalR doesn't support passing state between clients and the hub.</span></span>
- <span data-ttu-id="371bc-116">`PersistentConnection`클래스가 ASP.NET Core SignalR에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-116">The `PersistentConnection` class doesn't exist in ASP.NET Core SignalR.</span></span>
- <span data-ttu-id="371bc-117">ASP.NET SignalR는 SQL Server 및 Redis를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-117">ASP.NET SignalR supports SQL Server and Redis.</span></span> <span data-ttu-id="371bc-118">ASP.NET Core SignalR는 [Azure SignalR](/azure/azure-signalr/) 및 Redis를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="371bc-118">ASP.NET Core SignalR supports [Azure SignalR](/azure/azure-signalr/) and Redis.</span></span>

## <a name="references"></a><span data-ttu-id="371bc-119">참조</span><span class="sxs-lookup"><span data-stu-id="371bc-119">References</span></span>

- [<span data-ttu-id="371bc-120">ASP.NET SignalR와 ASP.NET Core SignalR의 차이점</span><span class="sxs-lookup"><span data-stu-id="371bc-120">Differences between ASP.NET SignalR and ASP.NET Core SignalR</span></span>](/aspnet/core/signalr/version-differences)
- [<span data-ttu-id="371bc-121">Azure SignalR Service</span><span class="sxs-lookup"><span data-stu-id="371bc-121">Azure SignalR Service</span></span>](/azure/azure-signalr/)

>[!div class="step-by-step"]
><span data-ttu-id="371bc-122">[이전](razor-differences.md)
>[다음](testing-differences.md)</span><span class="sxs-lookup"><span data-stu-id="371bc-122">[Previous](razor-differences.md)
[Next](testing-differences.md)</span></span>
