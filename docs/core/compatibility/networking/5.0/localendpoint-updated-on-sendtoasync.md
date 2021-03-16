---
title: '호환성이 손상되는 변경: SendToAsync를 호출한 후 Socket.LocalEndPoint가 업데이트됩니다.'
description: SendToAsync에서 로컬 엔드포인트 속성의 값을 소켓의 로컬 주소로 업데이트하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/18/2020
ms.openlocfilehash: 4be62f8bf6596cc3531d59f3e65eda005bff778a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256428"
---
# <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a>SendToAsync를 호출한 후 Socket.LocalEndPoint가 업데이트됩니다.

이제 <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType>에서 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> 속성 값을 소켓의 로컬 주소로 업데이트합니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서 <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType>은 소켓 인스턴스의 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> 속성 값을 변경하지 않았습니다. .NET 5부터 <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)>가 성공적으로 완료되면 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>의 값은 암시적으로 바인딩된 소켓의 로컬 주소입니다. 이 새로운 동작은 <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> 및 <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>의 동작과 일치합니다.

## <a name="reason-for-change"></a>변경 이유

이 변경 내용은 [버그가 수정](https://github.com/dotnet/runtime/issues/915)되고 `SendTo` 변형에서 동작을 일관되게 합니다.

## <a name="recommended-action"></a>권장 조치

<xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)>가 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>의 값을 변경하지 않는다고 가정하는 코드를 변경합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

### Category

Networking

-->
