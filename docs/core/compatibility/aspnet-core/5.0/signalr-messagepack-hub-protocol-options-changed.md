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
# <a name="signalr-messagepack-hub-protocol-options-type-changed"></a>SignalR: MessagePack 허브 프로토콜 옵션 형식이 변경됨

ASP.NET Core SignalR MessagePack 허브 프로토콜 옵션 형식이 `IList<MessagePack.IFormatterResolver>`에서 [MessagePack](https://www.nuget.org/packages/MessagePack) 라이브러리의 `MessagePackSerializerOptions` 형식으로 변경되었습니다.

이 문제에 관한 자세한 내용은 [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506)을 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 4

## <a name="old-behavior"></a>이전 동작

다음 예제와 같이 옵션에 추가할 수 있습니다.

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

옵션을 다음과 같이 바꿉니다.

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

## <a name="new-behavior"></a>새 동작

다음 예제와 같이 옵션에 추가할 수 있습니다.

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

옵션을 다음과 같이 바꿉니다.

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

## <a name="reason-for-change"></a>변경 이유

이 변경은 [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404)에서 발표된 MessagePack v2.x로 이동하는 과정의 일부입니다. v2.x 라이브러리는 더 쉽게 사용할 수 있는 옵션 API를 추가했으며 이전에 공개된 `MessagePack.IFormatterResolver` 목록보다 많은 기능을 제공합니다.

## <a name="recommended-action"></a>권장 조치

이 주요 변경 내용은 <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>에서 값을 구성하는 모두에게 영향을 줍니다. ASP.NET Core SignalR MessagePack 허브 프로토콜을 사용하고 옵션을 수정하는 경우 위와 같이 새 옵션 API를 사용하도록 사용법을 업데이트합니다.

## <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
