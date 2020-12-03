---
title: '호환성이 손상되는 변경: SignalR: MessagePack 허브 프로토콜 옵션 형식이 변경됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. SignalR: MessagePack 허브 프로토콜 옵션 형식이 변경됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b75dbec834699472f18b3058052274476bd9751d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760026"
---
# <a name="signalr-messagepack-hub-protocol-options-type-changed"></a><span data-ttu-id="273a1-103">SignalR: MessagePack 허브 프로토콜 옵션 형식이 변경됨</span><span class="sxs-lookup"><span data-stu-id="273a1-103">SignalR: MessagePack Hub Protocol options type changed</span></span>

<span data-ttu-id="273a1-104">ASP.NET Core SignalR MessagePack 허브 프로토콜 옵션 형식이 `IList<MessagePack.IFormatterResolver>`에서 [MessagePack](https://www.nuget.org/packages/MessagePack) 라이브러리의 `MessagePackSerializerOptions` 형식으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="273a1-104">The ASP.NET Core SignalR MessagePack Hub Protocol options type has changed from `IList<MessagePack.IFormatterResolver>` to the [MessagePack](https://www.nuget.org/packages/MessagePack) library's `MessagePackSerializerOptions` type.</span></span>

<span data-ttu-id="273a1-105">이 문제에 관한 자세한 내용은 [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="273a1-105">For discussion on this change, see [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="273a1-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="273a1-106">Version introduced</span></span>

<span data-ttu-id="273a1-107">5.0 미리 보기 4</span><span class="sxs-lookup"><span data-stu-id="273a1-107">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="273a1-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="273a1-108">Old behavior</span></span>

<span data-ttu-id="273a1-109">다음 예제와 같이 옵션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="273a1-109">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="273a1-110">옵션을 다음과 같이 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="273a1-110">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers = new List<MessagePack.IFormatterResolver>()
        {
            MessagePack.Resolvers.StandardResolver.Instance
        };
    });
```

## <a name="new-behavior"></a><span data-ttu-id="273a1-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="273a1-111">New behavior</span></span>

<span data-ttu-id="273a1-112">다음 예제와 같이 옵션에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="273a1-112">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="273a1-113">옵션을 다음과 같이 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="273a1-113">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions = MessagePackSerializerOptions
                .Standard
                .WithResolver(MessagePack.Resolvers.StandardResolver.Instance)
                .WithSecurity(MessagePackSecurity.UntrustedData);
    });
```

## <a name="reason-for-change"></a><span data-ttu-id="273a1-114">변경 이유</span><span class="sxs-lookup"><span data-stu-id="273a1-114">Reason for change</span></span>

<span data-ttu-id="273a1-115">이 변경은 [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404)에서 발표된 MessagePack v2.x로 이동하는 과정의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="273a1-115">This change is part of moving to MessagePack v2.x, which was announced in [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span></span> <span data-ttu-id="273a1-116">v2.x 라이브러리는 더 쉽게 사용할 수 있는 옵션 API를 추가했으며 이전에 공개된 `MessagePack.IFormatterResolver` 목록보다 많은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="273a1-116">The v2.x library has added an options API that's easier to use and provides more features than the list of `MessagePack.IFormatterResolver` that was exposed before.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="273a1-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="273a1-117">Recommended action</span></span>

<span data-ttu-id="273a1-118">이 주요 변경 내용은 <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>에서 값을 구성하는 모두에게 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="273a1-118">This breaking change affects anyone who is configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span> <span data-ttu-id="273a1-119">ASP.NET Core SignalR MessagePack 허브 프로토콜을 사용하고 옵션을 수정하는 경우 위와 같이 새 옵션 API를 사용하도록 사용법을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="273a1-119">If you're using the ASP.NET Core SignalR MessagePack Hub Protocol and modifying the options, update your usage to use the new options API as shown above.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="273a1-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="273a1-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
