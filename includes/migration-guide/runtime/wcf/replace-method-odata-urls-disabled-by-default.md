---
ms.openlocfilehash: b2fcacdb02c411c4dcb12051bf0c6759faccdea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620389"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="e6e39-101">OData URL의 Replace 메서드는 기본적으로 비활성화되어 있음</span><span class="sxs-lookup"><span data-stu-id="e6e39-101">The Replace method in OData URLs is disabled by default</span></span>

#### <a name="details"></a><span data-ttu-id="e6e39-102">설명</span><span class="sxs-lookup"><span data-stu-id="e6e39-102">Details</span></span>

<span data-ttu-id="e6e39-103">.NET Framework 4.5를 시작할 때 OData URL의 Replace 메서드는 기본적으로 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e39-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="e6e39-104">OData Replace가 비활성화되면(기본값) Replace 기능(일반적이지 않음)을 포함한 모든 사용자 요청이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e39-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e6e39-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e6e39-105">Suggestion</span></span>

<span data-ttu-id="e6e39-106">Replace 메서드가 필요한 경우(일반적이지 않음) 구성 설정(<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>)을 통해 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e39-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName>).</span></span> <span data-ttu-id="e6e39-107">그러나 활성화된 Replace 메서드는 보안 취약점을 열 수 있어 신중하게 검토한 후에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e39-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>

| <span data-ttu-id="e6e39-108">이름</span><span class="sxs-lookup"><span data-stu-id="e6e39-108">Name</span></span>    | <span data-ttu-id="e6e39-109">값</span><span class="sxs-lookup"><span data-stu-id="e6e39-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e6e39-110">Scope</span><span class="sxs-lookup"><span data-stu-id="e6e39-110">Scope</span></span>   |<span data-ttu-id="e6e39-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e6e39-111">Edge</span></span>|
|<span data-ttu-id="e6e39-112">버전</span><span class="sxs-lookup"><span data-stu-id="e6e39-112">Version</span></span>|<span data-ttu-id="e6e39-113">4.5</span><span class="sxs-lookup"><span data-stu-id="e6e39-113">4.5</span></span>|
|<span data-ttu-id="e6e39-114">형식</span><span class="sxs-lookup"><span data-stu-id="e6e39-114">Type</span></span>|<span data-ttu-id="e6e39-115">런타임</span><span class="sxs-lookup"><span data-stu-id="e6e39-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e6e39-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e6e39-116">Affected APIs</span></span>

-<xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
