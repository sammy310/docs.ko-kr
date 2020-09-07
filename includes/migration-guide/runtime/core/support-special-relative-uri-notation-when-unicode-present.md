---
ms.openlocfilehash: 3c32d2e13447f8fd9aa6b185b5fc7e60f9e1bb61
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497932"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a><span data-ttu-id="050c3-101">유니코드가 있는 경우 특별한 상대 URI 표기법 지원</span><span class="sxs-lookup"><span data-stu-id="050c3-101">Support special relative URI notation when Unicode is present</span></span>

#### <a name="details"></a><span data-ttu-id="050c3-102">설명</span><span class="sxs-lookup"><span data-stu-id="050c3-102">Details</span></span>

<span data-ttu-id="050c3-103"><xref:System.Uri>은 유니코드를 포함하는 특정 상대 URI에서 <xref:System.Uri.TryCreate%2A>를 호출할 때 더 이상 <xref:System.NullReferenceException>을 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="050c3-103"><xref:System.Uri> will no longer throw a <xref:System.NullReferenceException> when calling <xref:System.Uri.TryCreate%2A> on certain relative URIs containing Unicode.</span></span> <span data-ttu-id="050c3-104"><xref:System.NullReferenceException>의 가장 간단한 재현은 두 개의 문이 동등한 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="050c3-104">The simplest reproduction of the <xref:System.NullReferenceException> is below, with the two statements being equivalent:</span></span><pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre><span data-ttu-id="050c3-105"><xref:System.NullReferenceException>을 재현하려면 다음 항목은 true여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="050c3-105">To reproduce the <xref:System.NullReferenceException>, the following items must be true:</span></span><ul><li><span data-ttu-id="050c3-106">‘http:’를 앞에 추가하고 ‘//’를 뒤에 오지 않게 하여 URI를 상대로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="050c3-106">The URI must be specified as relative by prepending it with ‘http:’ and not following it with ‘//’.</span></span></li><li><span data-ttu-id="050c3-107">URI는 백분율로 인코딩된 유니코드 또는 예약되지 않은 기호를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="050c3-107">The URI must contain percent-encoded Unicode or unreserved symbols.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="050c3-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="050c3-108">Suggestion</span></span>

<span data-ttu-id="050c3-109">이 동작에 따라 사용자는 상대 URI를 허용하지 않도록 URI를 만들 때 대신 <xref:System.UriKind.Absolute?displayProperty=nameWithType>을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="050c3-109">Users depending on this behavior to disallow relative URIs should instead specify <xref:System.UriKind.Absolute?displayProperty=nameWithType> when creating a URI.</span></span>

| <span data-ttu-id="050c3-110">이름</span><span class="sxs-lookup"><span data-stu-id="050c3-110">Name</span></span>    | <span data-ttu-id="050c3-111">값</span><span class="sxs-lookup"><span data-stu-id="050c3-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="050c3-112">Scope</span><span class="sxs-lookup"><span data-stu-id="050c3-112">Scope</span></span>   |<span data-ttu-id="050c3-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="050c3-113">Edge</span></span>|
|<span data-ttu-id="050c3-114">버전</span><span class="sxs-lookup"><span data-stu-id="050c3-114">Version</span></span>|<span data-ttu-id="050c3-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="050c3-115">4.7.2</span></span>|
|<span data-ttu-id="050c3-116">형식</span><span class="sxs-lookup"><span data-stu-id="050c3-116">Type</span></span>|<span data-ttu-id="050c3-117">런타임</span><span class="sxs-lookup"><span data-stu-id="050c3-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="050c3-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="050c3-118">Affected APIs</span></span>

- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)`
- `M:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)`
- `M:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)`

-->
