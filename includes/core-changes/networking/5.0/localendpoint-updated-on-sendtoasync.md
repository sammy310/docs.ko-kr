---
ms.openlocfilehash: 8de70b0c445aa48fc4c3249ccfc8c095890fb14c
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050527"
---
### <a name="socketlocalendpoint-is-updated-after-calling-sendtoasync"></a><span data-ttu-id="d0984-101">SendToAsync를 호출한 후 Socket.LocalEndPoint가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-101">Socket.LocalEndPoint is updated after calling SendToAsync</span></span>

<span data-ttu-id="d0984-102">이제 <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType>에서 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> 속성 값을 소켓의 로컬 주소로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-102"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> now updates the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property to the socket's local address.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d0984-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d0984-103">Version introduced</span></span>

<span data-ttu-id="d0984-104">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="d0984-104">5.0 RC1</span></span>

#### <a name="change-description"></a><span data-ttu-id="d0984-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="d0984-105">Change description</span></span>

<span data-ttu-id="d0984-106">이전 .NET 버전에서 <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType>은 소켓 인스턴스의 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> 속성 값을 변경하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-106">In previous .NET versions, <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=nameWithType> does not alter the value of the <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> property on the socket instance.</span></span> <span data-ttu-id="d0984-107">.NET 5.0부터 <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)>가 성공적으로 완료되면 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>의 값은 암시적으로 바인딩된 소켓의 로컬 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-107">Starting in .NET 5.0, when <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> successfully completes, the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType> is the implicitly bound socket's local address.</span></span> <span data-ttu-id="d0984-108">이 새로운 동작은 <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> 및 <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>의 동작과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-108">This new behavior is consistent with the behavior of <xref:System.Net.Sockets.Socket.SendTo(System.Byte[],System.Net.EndPoint)> and <xref:System.Net.Sockets.Socket.BeginSendTo(System.Byte[],System.Int32,System.Int32,System.Net.Sockets.SocketFlags,System.Net.EndPoint,System.AsyncCallback,System.Object)>/<xref:System.Net.Sockets.Socket.EndSendTo(System.IAsyncResult)>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d0984-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="d0984-109">Reason for change</span></span>

<span data-ttu-id="d0984-110">이 변경 내용은 [버그가 수정](https://github.com/dotnet/runtime/issues/915)되고 `SendTo` 변형에서 동작을 일관되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-110">This change [fixes a bug](https://github.com/dotnet/runtime/issues/915) and makes the behavior consistent across `SendTo` variants.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d0984-111">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d0984-111">Recommended action</span></span>

<span data-ttu-id="d0984-112"><xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)>가 <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>의 값을 변경하지 않는다고 가정하는 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d0984-112">Alter any code that assumes that <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)> won't alter the value of <xref:System.Net.Sockets.Socket.LocalEndPoint?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="d0984-113">범주</span><span class="sxs-lookup"><span data-stu-id="d0984-113">Category</span></span>

<span data-ttu-id="d0984-114">네트워킹</span><span class="sxs-lookup"><span data-stu-id="d0984-114">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d0984-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d0984-115">Affected APIs</span></span>

- <xref:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.Sockets.Socket.SendToAsync(System.Net.Sockets.SocketAsyncEventArgs)`

-->
