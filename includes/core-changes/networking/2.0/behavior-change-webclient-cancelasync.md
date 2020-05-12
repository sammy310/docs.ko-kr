---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859627"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a><span data-ttu-id="e0daf-101">WebClient.CancelAsync가 항상 즉시 취소되지는 않음</span><span class="sxs-lookup"><span data-stu-id="e0daf-101">WebClient.CancelAsync doesn't always cancel immediately</span></span>

<span data-ttu-id="e0daf-102">.NET Core 2.0부터 응답을 가져오기 시작한 경우 <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>를 호출하면 요청이 즉시 취소되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-102">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> doesn't cancel the request immediately if the response has started to fetch.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e0daf-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e0daf-103">Change description</span></span>

<span data-ttu-id="e0daf-104">이전에는 <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>를 호출하면 요청이 즉시 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-104">Previously, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> canceled the request immediately.</span></span> <span data-ttu-id="e0daf-105">.NET Core 2.0부터 응답을 가져오기 시작하지 않은 경우에만 <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>를 호출하면 요청이 즉시 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-105">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> cancels the request immediately only if the response hasn't started fetching.</span></span> <span data-ttu-id="e0daf-106">응답을 가져오기 시작한 경우에는 전체 응답을 읽은 후에만 요청이 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-106">If the response has started to fetch, the request is cancelled only after a complete response is read.</span></span>

<span data-ttu-id="e0daf-107"><xref:System.Net.WebClient> API가 사용되지 않고 <xref:System.Net.Http.HttpClient>로 대체되었기 때문에 이러한 변경이 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-107">This change was implemented because the <xref:System.Net.WebClient> API is deprecated in favor of <xref:System.Net.Http.HttpClient>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e0daf-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e0daf-108">Version introduced</span></span>

<span data-ttu-id="e0daf-109">2.0</span><span class="sxs-lookup"><span data-stu-id="e0daf-109">2.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e0daf-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e0daf-110">Recommended action</span></span>

<span data-ttu-id="e0daf-111">더 이상 사용되지 않는 <xref:System.Net.WebClient?displayProperty=fullName> 대신 <xref:System.Net.Http.HttpClient?displayProperty=fullName> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0daf-111">Use the <xref:System.Net.Http.HttpClient?displayProperty=fullName> class instead of <xref:System.Net.WebClient?displayProperty=fullName>, which is deprecated.</span></span>

#### <a name="category"></a><span data-ttu-id="e0daf-112">범주</span><span class="sxs-lookup"><span data-stu-id="e0daf-112">Category</span></span>

<span data-ttu-id="e0daf-113">네트워킹</span><span class="sxs-lookup"><span data-stu-id="e0daf-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e0daf-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e0daf-114">Affected APIs</span></span>

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
