---
ms.openlocfilehash: 203d75f5858c8ff039cf579c0539efda0c5c9f02
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474382"
---
### <a name="kestrel-libuv-transport-marked-as-obsolete"></a><span data-ttu-id="52d8d-101">Kestrel: 사용되지 않는 것으로 표시된 Libuv 전송</span><span class="sxs-lookup"><span data-stu-id="52d8d-101">Kestrel: Libuv transport marked as obsolete</span></span>

<span data-ttu-id="52d8d-102">이전 버전의 ASP.NET Core는 비동기 입력 및 출력을 수행하는 방법에 대한 구현 세부 정보로 Libuv를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-102">Earlier versions of ASP.NET Core used Libuv as an implementation detail of how asynchronous input and output was performed.</span></span> <span data-ttu-id="52d8d-103">ASP.NET Core 2.0에서는 대안으로 <xref:System.Net.Sockets.Socket> 기반 전송이 개발되었습니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-103">In ASP.NET Core 2.0, an alternative, <xref:System.Net.Sockets.Socket>-based transport was developed.</span></span> <span data-ttu-id="52d8d-104">ASP.NET Core 2.1에서 Kestrel은 기본적으로 `Socket` 기반 전송을 사용하도록 전환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-104">In ASP.NET Core 2.1, Kestrel switched to using the `Socket`-based transport by default.</span></span> <span data-ttu-id="52d8d-105">Libuv 지원은 호환성을 위해 유지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-105">Libuv support was maintained for compatibility reasons.</span></span>

<span data-ttu-id="52d8d-106">이 시점에서 `Socket` 기반 전송을 사용하는 것은 Libuv 전송을 사용하는 것보다 훨씬 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-106">At this point, use of the `Socket`-based transport is far more common than the Libuv transport.</span></span> <span data-ttu-id="52d8d-107">결과적으로, Libuv 지원은 .NET 5.0에서 사용되지 않는 것으로 표시되고 .NET 6.0에서 완전히 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-107">Consequently, Libuv support is marked as obsolete in .NET 5.0 and will be removed entirely in .NET 6.0.</span></span>

<span data-ttu-id="52d8d-108">이러한 변경의 일환으로 새로운 운영 체제 플랫폼(예: Windows ARM64)에 대한 Libuv 지원은 .NET 5.0 기간에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-108">As part of this change, Libuv support for new operating system platforms (like Windows ARM64) won't be added in the .NET 5.0 timeframe.</span></span>

<span data-ttu-id="52d8d-109">Libuv 전송을 필수적으로 사용해야 하는 문제에 대한 내용은 [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409)에서 GitHub 문제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52d8d-109">For discussion on blocking issues that require the use of the Libuv transport, see the GitHub issue at [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="52d8d-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="52d8d-110">Version introduced</span></span>

<span data-ttu-id="52d8d-111">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="52d8d-111">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="52d8d-112">이전 동작</span><span class="sxs-lookup"><span data-stu-id="52d8d-112">Old behavior</span></span>

<span data-ttu-id="52d8d-113">Libuv API는 사용되지 않는 것으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-113">The Libuv APIs aren't marked as obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="52d8d-114">새 동작</span><span class="sxs-lookup"><span data-stu-id="52d8d-114">New behavior</span></span>

<span data-ttu-id="52d8d-115">Libuv API는 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-115">The Libuv APIs are marked as obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="52d8d-116">변경 이유</span><span class="sxs-lookup"><span data-stu-id="52d8d-116">Reason for change</span></span>

<span data-ttu-id="52d8d-117">기본값은 `Socket` 기반 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-117">The `Socket`-based transport is the default.</span></span> <span data-ttu-id="52d8d-118">Libuv 전송을 계속 사용해야 할 뚜렷한 이유는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-118">There aren't any compelling reasons to continue using the Libuv transport.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="52d8d-119">권장 조치</span><span class="sxs-lookup"><span data-stu-id="52d8d-119">Recommended action</span></span>

<span data-ttu-id="52d8d-120">[Libuv 패키지](https://www.nuget.org/packages/Libuv) 및 확장 메서드의 사용을 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="52d8d-120">Discontinue use of the [Libuv package](https://www.nuget.org/packages/Libuv) and extension methods.</span></span>

#### <a name="category"></a><span data-ttu-id="52d8d-121">범주</span><span class="sxs-lookup"><span data-stu-id="52d8d-121">Category</span></span>

<span data-ttu-id="52d8d-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="52d8d-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="52d8d-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="52d8d-123">Affected APIs</span></span>

- [<span data-ttu-id="52d8d-124">WebHostBuilderLibuvExtensions</span><span class="sxs-lookup"><span data-stu-id="52d8d-124">WebHostBuilderLibuvExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [<span data-ttu-id="52d8d-125">WebHostBuilderLibuvExtensions.UseLibuv</span><span class="sxs-lookup"><span data-stu-id="52d8d-125">WebHostBuilderLibuvExtensions.UseLibuv</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [<span data-ttu-id="52d8d-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span><span class="sxs-lookup"><span data-stu-id="52d8d-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [<span data-ttu-id="52d8d-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span><span class="sxs-lookup"><span data-stu-id="52d8d-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [<span data-ttu-id="52d8d-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span><span class="sxs-lookup"><span data-stu-id="52d8d-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [<span data-ttu-id="52d8d-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span><span class="sxs-lookup"><span data-stu-id="52d8d-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [<span data-ttu-id="52d8d-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span><span class="sxs-lookup"><span data-stu-id="52d8d-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
