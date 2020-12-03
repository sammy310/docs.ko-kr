---
title: '호환성이 손상되는 변경: NegotiateStream 및 SslStream은 연속 Begin 작업을 허용합니다.'
description: 보안 스트림의 오류 사례가 다르게 처리되고 BeginAuthenticateAsServer 또는 BeginAuthenticateAsClient에 대한 연속 호출이 더 이상 실패하지 않는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 10/18/2020
ms.openlocfilehash: e0226d0f5586efca050ca3497ca1490fa21fd943
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759688"
---
# <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a><span data-ttu-id="8b6d8-103">NegotiateStream 및 SslStream은 연속 Begin 작업을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d8-103">NegotiateStream and SslStream allow successive Begin operations</span></span>

<span data-ttu-id="8b6d8-104">보안 스트림의 오류 사례는 다르게 처리되며, `BeginAuthenticateAsServer` 또는 `BeginAuthenticateAsClient`에 대한 후속 호출이 더 이상 실패하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d8-104">Error cases on security streams are handled differently, and successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` may no longer fail.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="8b6d8-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="8b6d8-105">Version introduced</span></span>

<span data-ttu-id="8b6d8-106">5.0</span><span class="sxs-lookup"><span data-stu-id="8b6d8-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="8b6d8-107">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="8b6d8-107">Change description</span></span>

<span data-ttu-id="8b6d8-108">이전 .NET 버전에서는 먼저 `EndAuthenticateAsServer` 또는 `EndAuthenticateAsClient`를 호출하지 않고 `BeginAuthenticateAsServer` 또는 `BeginAuthenticateAsClient`를 연속적으로 호출하면 <xref:System.NotSupportedException>이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d8-108">In previous .NET versions, calling `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` successively without first calling `EndAuthenticateAsServer` or `EndAuthenticateAsClient` results in a <xref:System.NotSupportedException>.</span></span> <span data-ttu-id="8b6d8-109">.NET 5.0부터는 `BeginAuthenticateAsServer` 또는 `BeginAuthenticateAsClient`에 대한 연속적인 호출이 더 이상 <xref:System.NotSupportedException>을 생성하지 않습니다. 이러한 API는 <xref:System.Threading.Tasks.Task> 기반 구현에서 지원되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d8-109">Starting in .NET 5.0, successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` no longer result in a <xref:System.NotSupportedException>, because these APIs are backed by a <xref:System.Threading.Tasks.Task>-based implementation.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="8b6d8-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="8b6d8-110">Reason for change</span></span>

<span data-ttu-id="8b6d8-111">내부 구현을 APM(비동기 프로그래밍 모델)에서 <xref:System.Threading.Tasks.Task> 기반으로 전환하면 성능이 향상되고 코드 복잡성도 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d8-111">Switching the internal implementation from asynchronous programming model (APM) to <xref:System.Threading.Tasks.Task>-based improves performance and decreases code complexity.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="8b6d8-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="8b6d8-112">Recommended action</span></span>

<span data-ttu-id="8b6d8-113">개발자는 아무 작업도 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d8-113">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="8b6d8-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="8b6d8-114">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.SslStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A?displayProperty=fullName>
- <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.SslStream.BeginAuthenticateAsClient`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer`
- `Overload:M:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient`

### Category

Networking

-->
