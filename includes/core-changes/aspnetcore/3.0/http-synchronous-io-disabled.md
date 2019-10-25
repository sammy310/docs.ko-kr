---
ms.openlocfilehash: ab7c097f6b65d539117e5a6ef38eb67b24695a32
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394224"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a><span data-ttu-id="73bf8-101">HTTP: 모든 서버에서 동기 IO 비활성화</span><span class="sxs-lookup"><span data-stu-id="73bf8-101">HTTP: Synchronous IO disabled in all servers</span></span>

<span data-ttu-id="73bf8-102">ASP.NET Core 3.0부터 동기 서버 작업은 기본적으로 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-102">Starting with ASP.NET Core 3.0, synchronous server operations are disabled by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="73bf8-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="73bf8-103">Change description</span></span>

<span data-ttu-id="73bf8-104">`AllowSynchronousIO`는 `HttpRequest.Body.Read`, `HttpResponse.Body.Write` 및 `Stream.Flush`와 같은 동기 IO API를 사용하거나 사용하지 않도록 설정하는 각 서버의 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-104">`AllowSynchronousIO` is an option in each server that enables or disables synchronous IO APIs like `HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush`.</span></span> <span data-ttu-id="73bf8-105">이러한 API는 오랫동안 스레드 고갈과 앱 중지의 원인이었습니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-105">These APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="73bf8-106">ASP.NET Core 3.0 미리 보기 3부터 이러한 동기 작업은 기본적으로 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-106">Starting in ASP.NET Core 3.0 Preview 3, these synchronous operations are disabled by default.</span></span>

<span data-ttu-id="73bf8-107">영향을 받는 서버:</span><span class="sxs-lookup"><span data-stu-id="73bf8-107">Affected servers:</span></span>

- <span data-ttu-id="73bf8-108">Kestrel</span><span class="sxs-lookup"><span data-stu-id="73bf8-108">Kestrel</span></span>
- <span data-ttu-id="73bf8-109">HttpSys</span><span class="sxs-lookup"><span data-stu-id="73bf8-109">HttpSys</span></span>
- <span data-ttu-id="73bf8-110">IIS In-Process</span><span class="sxs-lookup"><span data-stu-id="73bf8-110">IIS in-process</span></span>
- <span data-ttu-id="73bf8-111">TestServer</span><span class="sxs-lookup"><span data-stu-id="73bf8-111">TestServer</span></span>

<span data-ttu-id="73bf8-112">다음과 유사한 오류가 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-112">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

<span data-ttu-id="73bf8-113">각 서버에는 이 동작을 제어하는 `AllowSynchronousIO` 옵션이 있으며 모든 항목에 대한 기본값은 이제 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-113">Each server has an `AllowSynchronousIO` option that controls this behavior and the default for all of them is now `false`.</span></span>

<span data-ttu-id="73bf8-114">이 동작은 요청에 따라 임시 완화로 재정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-114">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span> <span data-ttu-id="73bf8-115">예:</span><span class="sxs-lookup"><span data-stu-id="73bf8-115">For example:</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

<span data-ttu-id="73bf8-116">`TextWriter` 또는 `Dispose`에서 동기 API를 호출하는 다른 스트림에 문제가 있는 경우 대신 새 `DisposeAsync` API를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-116">If you have trouble with a `TextWriter` or another stream calling a synchronous API in `Dispose`, call the new `DisposeAsync` API instead.</span></span>

<span data-ttu-id="73bf8-117">자세한 내용은 [aspnet/AspNetCore#7644](https://github.com/aspnet/AspNetCore/issues/7644)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73bf8-117">For discussion, see [aspnet/AspNetCore#7644](https://github.com/aspnet/AspNetCore/issues/7644).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="73bf8-118">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="73bf8-118">Version introduced</span></span>

<span data-ttu-id="73bf8-119">3.0</span><span class="sxs-lookup"><span data-stu-id="73bf8-119">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="73bf8-120">이전 동작</span><span class="sxs-lookup"><span data-stu-id="73bf8-120">Old behavior</span></span>

<span data-ttu-id="73bf8-121">기본적으로 `HttpRequest.Body.Read`, `HttpResponse.Body.Write` 및 `Stream.Flush`가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-121">`HttpRequest.Body.Read`, `HttpResponse.Body.Write`, and `Stream.Flush` were allowed by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="73bf8-122">새 동작</span><span class="sxs-lookup"><span data-stu-id="73bf8-122">New behavior</span></span>

<span data-ttu-id="73bf8-123">이러한 동기 API는 기본적으로 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-123">These synchronous APIs are disallowed by default:</span></span> 

<span data-ttu-id="73bf8-124">다음과 유사한 오류가 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-124">Expect errors similar to:</span></span>

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a><span data-ttu-id="73bf8-125">변경 이유</span><span class="sxs-lookup"><span data-stu-id="73bf8-125">Reason for change</span></span>

<span data-ttu-id="73bf8-126">이러한 동기 API는 오랫동안 스레드 고갈과 앱 중지의 원인이었습니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-126">These synchronous APIs have long been a source of thread starvation and app hangs.</span></span> <span data-ttu-id="73bf8-127">ASP.NET Core 3.0 미리 보기 3부터 동기 작업은 기본적으로 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-127">Starting in ASP.NET Core 3.0 Preview 3, the synchronous operations are disabled by default.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="73bf8-128">권장 작업</span><span class="sxs-lookup"><span data-stu-id="73bf8-128">Recommended action</span></span>

<span data-ttu-id="73bf8-129">비동기 버전의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-129">Use the asynchronous versions of the methods.</span></span> <span data-ttu-id="73bf8-130">이 동작은 요청에 따라 임시 완화로 재정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73bf8-130">The behavior can also be overridden on a per-request basis as a temporary mitigation.</span></span>

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a><span data-ttu-id="73bf8-131">범주</span><span class="sxs-lookup"><span data-stu-id="73bf8-131">Category</span></span>

<span data-ttu-id="73bf8-132">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="73bf8-132">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="73bf8-133">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="73bf8-133">Affected APIs</span></span>

- <xref:System.IO.Stream.Flush%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.IO.Stream.Flush`
- `Overload:System.IO.Stream.Read`
- `Overload:System.IO.Stream.Write`

-->
