---
title: '호환성이 손상되는 변경: NegotiateStream 및 SslStream은 연속 Begin 작업을 허용합니다.'
description: 보안 스트림의 오류 사례가 다르게 처리되고 BeginAuthenticateAsServer 또는 BeginAuthenticateAsClient에 대한 연속 호출이 더 이상 실패하지 않는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/18/2020
ms.openlocfilehash: 5c042be01873849cc154111a31fc007521508c7b
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256441"
---
# <a name="negotiatestream-and-sslstream-allow-successive-begin-operations"></a><span data-ttu-id="08cc2-103">NegotiateStream 및 SslStream은 연속 Begin 작업을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="08cc2-103">NegotiateStream and SslStream allow successive Begin operations</span></span>

<span data-ttu-id="08cc2-104">보안 스트림의 오류 사례는 다르게 처리되며, `BeginAuthenticateAsServer` 또는 `BeginAuthenticateAsClient`에 대한 후속 호출이 더 이상 실패하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cc2-104">Error cases on security streams are handled differently, and successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` may no longer fail.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="08cc2-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="08cc2-105">Version introduced</span></span>

<span data-ttu-id="08cc2-106">5.0</span><span class="sxs-lookup"><span data-stu-id="08cc2-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="08cc2-107">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="08cc2-107">Change description</span></span>

<span data-ttu-id="08cc2-108">이전 .NET 버전에서는 먼저 `EndAuthenticateAsServer` 또는 `EndAuthenticateAsClient`를 호출하지 않고 `BeginAuthenticateAsServer` 또는 `BeginAuthenticateAsClient`를 연속적으로 호출하면 <xref:System.NotSupportedException>이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08cc2-108">In previous .NET versions, calling `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` successively without first calling `EndAuthenticateAsServer` or `EndAuthenticateAsClient` results in a <xref:System.NotSupportedException>.</span></span> <span data-ttu-id="08cc2-109">.NET 5부터는 `BeginAuthenticateAsServer` 또는 `BeginAuthenticateAsClient`에 대한 연속적인 호출이 더 이상 <xref:System.NotSupportedException>을 생성하지 않습니다. 해당 API는 <xref:System.Threading.Tasks.Task> 기반 구현에서 지원되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="08cc2-109">Starting in .NET 5, successive calls to `BeginAuthenticateAsServer` or `BeginAuthenticateAsClient` no longer result in a <xref:System.NotSupportedException>, because these APIs are backed by a <xref:System.Threading.Tasks.Task>-based implementation.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="08cc2-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="08cc2-110">Reason for change</span></span>

<span data-ttu-id="08cc2-111">내부 구현을 APM(비동기 프로그래밍 모델)에서 <xref:System.Threading.Tasks.Task> 기반으로 전환하면 성능이 향상되고 코드 복잡성도 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="08cc2-111">Switching the internal implementation from asynchronous programming model (APM) to <xref:System.Threading.Tasks.Task>-based improves performance and decreases code complexity.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="08cc2-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="08cc2-112">Recommended action</span></span>

<span data-ttu-id="08cc2-113">개발자는 아무 작업도 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08cc2-113">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="08cc2-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="08cc2-114">Affected APIs</span></span>

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
