---
ms.openlocfilehash: 8979b7ffc09726c6588fe3ba60b916202697648f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522709"
---
### <a name="signalr-hubconnectioncontext-constructors-changed"></a><span data-ttu-id="98594-101">SignalR: HubConnectionContext 생성자가 변경됨</span><span class="sxs-lookup"><span data-stu-id="98594-101">SignalR: HubConnectionContext constructors changed</span></span>

<span data-ttu-id="98594-102">SignalR의 `HubConnectionContext` 생성자는 이후 증명 추가 옵션에 대해 여러 매개 변수 대신 옵션 유형을 허용하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="98594-102">SignalR's `HubConnectionContext` constructors changed to accept an options type, rather than multiple parameters, to future-proof adding options.</span></span> <span data-ttu-id="98594-103">이 변경 내용은 두 개의 생성자를 옵션 유형을 허용하는 단일 생성자로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="98594-103">This change replaces two constructors with a single constructor that accepts an options type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="98594-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="98594-104">Version introduced</span></span>

<span data-ttu-id="98594-105">3.0</span><span class="sxs-lookup"><span data-stu-id="98594-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="98594-106">이전 동작</span><span class="sxs-lookup"><span data-stu-id="98594-106">Old behavior</span></span>

<span data-ttu-id="98594-107">`HubConnectionContext`에는 두 개의 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98594-107">`HubConnectionContext` has two constructors:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory);
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory, TimeSpan clientTimeoutInterval);
```

#### <a name="new-behavior"></a><span data-ttu-id="98594-108">새 동작</span><span class="sxs-lookup"><span data-stu-id="98594-108">New behavior</span></span>

<span data-ttu-id="98594-109">두 개의 생성자가 제거되고 하나의 생성자로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="98594-109">The two constructors were removed and replaced with one constructor:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, HubConnectionContextOptions contextOptions, ILoggerFactory loggerFactory)
```

#### <a name="reason-for-change"></a><span data-ttu-id="98594-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="98594-110">Reason for change</span></span>

<span data-ttu-id="98594-111">새 생성자는 새 옵션 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98594-111">The new constructor uses a new options object.</span></span> <span data-ttu-id="98594-112">따라서 나중에 추가 생성자 및 호환성이 손상되는 변경 없이 `HubConnectionContext`의 기능을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98594-112">Consequently, the features of `HubConnectionContext` can be expanded in the future without making more constructors and breaking changes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="98594-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="98594-113">Recommended action</span></span>

<span data-ttu-id="98594-114">다음 생성자 사용하는 대신:</span><span class="sxs-lookup"><span data-stu-id="98594-114">Instead of using the following constructor:</span></span>

```csharp
HubConnectionContext connectionContext = new HubConnectionContext(
    connectionContext,
    keepAliveInterval: TimeSpan.FromSeconds(15),
    loggerFactory,
    clientTimeoutInterval: TimeSpan.FromSeconds(15));
```

<span data-ttu-id="98594-115">다음 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98594-115">Use the following constructor:</span></span>

```csharp
HubConnectionContextOptions contextOptions = new HubConnectionContextOptions()
{
    KeepAliveInterval = TimeSpan.FromSeconds(15),
    ClientTimeoutInterval = TimeSpan.FromSeconds(15)
};
HubConnectionContext connectionContext = new HubConnectionContext(connectionContext, contextOptions, loggerFactory);
```

#### <a name="category"></a><span data-ttu-id="98594-116">범주</span><span class="sxs-lookup"><span data-stu-id="98594-116">Category</span></span>

<span data-ttu-id="98594-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="98594-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="98594-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="98594-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)`
- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)`

-->
