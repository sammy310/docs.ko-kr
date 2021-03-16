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
# <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a><span data-ttu-id="f0d92-103">SendToAsync를 호출한 후 Socket.LocalEndPoint가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d92-103">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>

<span data-ttu-id="f0d92-104">이제 <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType>에서 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> 속성 값을 소켓의 로컬 주소로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d92-104"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> now updates the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property to the socket's local address.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f0d92-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f0d92-105">Version introduced</span></span>

<span data-ttu-id="f0d92-106">5.0</span><span class="sxs-lookup"><span data-stu-id="f0d92-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="f0d92-107">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="f0d92-107">Change description</span></span>

<span data-ttu-id="f0d92-108">이전 .NET 버전에서 <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType>은 소켓 인스턴스의 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> 속성 값을 변경하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d92-108">In previous .NET versions, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> does not alter the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property on the socket instance.</span></span> <span data-ttu-id="f0d92-109">.NET 5부터 <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)>가 성공적으로 완료되면 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>의 값은 암시적으로 바인딩된 소켓의 로컬 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f0d92-109">Starting in .NET 5, when <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> successfully completes, the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> is the implicitly bound socket's local address.</span></span> <span data-ttu-id="f0d92-110">이 새로운 동작은 <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> 및 <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>의 동작과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d92-110">This new behavior is consistent with the behavior of <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> and <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f0d92-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="f0d92-111">Reason for change</span></span>

<span data-ttu-id="f0d92-112">이 변경 내용은 [버그가 수정](https://github.com/dotnet/runtime/issues/915)되고 `SendTo` 변형에서 동작을 일관되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d92-112">This change [fixes a bug](https://github.com/dotnet/runtime/issues/915) and makes the behavior consistent across `SendTo` variants.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f0d92-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="f0d92-113">Recommended action</span></span>

<span data-ttu-id="f0d92-114"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)>가 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>의 값을 변경하지 않는다고 가정하는 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d92-114">Alter any code that assumes that <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> won't alter the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f0d92-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f0d92-115">Affected APIs</span></span>

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

### Category

Networking

-->
