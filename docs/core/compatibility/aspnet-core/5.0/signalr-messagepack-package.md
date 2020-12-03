---
title: '호환성이 손상되는 변경: SignalR: MessagePack 허브 프로토콜이 MessagePack 2.x 패키지로 이동됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. SignalR: MessagePack 허브 프로토콜이 MessagePack 2.x 패키지로 이동됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 1e666c40d7046233c9fb06af819b901fd1251b06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760025"
---
# <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a>SignalR: MessagePack 허브 프로토콜이 MessagePack 2.x 패키지로 이동됨

ASP.NET Core SignalR [MessagePack 허브 프로토콜](/aspnet/core/signalr/messagepackhubprotocol)은 MessagePack serialization에 대해 [MessagePack NuGet 패키지](https://www.nuget.org/packages/MessagePack)를 사용합니다. ASP.NET Core 5.0은 패키지를 1.x에서 최신 2.x 패키지 버전으로 업그레이드합니다.

이 문제에 대한 자세한 내용은 [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692)를 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 1

## <a name="old-behavior"></a>이전 동작

ASP.NET Core SignalR은 MessagePack 1.x 패키지를 사용하여 MessagePack 메시지를 직렬화 및 역직렬화했습니다.

## <a name="new-behavior"></a>새 동작

ASP.NET Core SignalR은 MessagePack 2.x 패키지를 사용하여 MessagePack 메시지를 직렬화 및 역직렬화합니다.

## <a name="reason-for-change"></a>변경 이유

MessagePack 2.x 패키지의 최신 개선 사항에 유용한 기능이 추가되었습니다.

## <a name="recommended-action"></a>권장 작업

이러한 주요 변경 내용은 다음 경우에 적용됩니다.

* <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>에서 값을 설정 또는 구성.
* MessagePack API를 직접 사용하고 동일한 프로젝트에서 ASP.NET Core SignalR MessagePack 허브 프로토콜을 사용. 이전 버전 대신 새 버전이 로드됩니다.

패키지 작성자를 위한 마이그레이션 지침은 [MessagePack v1.x에서 MessagePack v2.x로 마이그레이션](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md)을 참조하세요. 메시지 serialization 및 deserialization의 일부 측면이 영향을 받습니다. 특히 [DateTime 값이 직렬화되는 방식에 대한 동작 변경](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes)이 있습니다.

## <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
