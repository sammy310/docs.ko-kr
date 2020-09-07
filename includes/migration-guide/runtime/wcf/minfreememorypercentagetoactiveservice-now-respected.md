---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496995"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="3a853-101">MinFreeMemoryPercentageToActiveService가 지금 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a853-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="3a853-102">설명</span><span class="sxs-lookup"><span data-stu-id="3a853-102">Details</span></span>

<span data-ttu-id="3a853-103">이 설정은 WCF 서비스 활성화를 위해 서버에서 사용할 수 있는 최소 메모리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a853-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="3a853-104">또한 이 설정은 <xref:System.OutOfMemoryException?displayProperty=fullName> 예외가 발생되지 않도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a853-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="3a853-105">.NET Framework 4.5에서 이 설정은 영향을 주지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3a853-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="3a853-106">.NET Framework 4.5.1에서 해당 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a853-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3a853-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="3a853-107">Suggestion</span></span>

<span data-ttu-id="3a853-108">웹 서버의 사용 가능한 메모리가 구성 설정에서 정의된 백분율보다 적은 경우 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3a853-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="3a853-109">성공적으로 시작되었지만 제한된 메모리 환경에서 실행되는 일부 WCF 서비스의 경우 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a853-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="3a853-110">이름</span><span class="sxs-lookup"><span data-stu-id="3a853-110">Name</span></span>    | <span data-ttu-id="3a853-111">값</span><span class="sxs-lookup"><span data-stu-id="3a853-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3a853-112">Scope</span><span class="sxs-lookup"><span data-stu-id="3a853-112">Scope</span></span>   |<span data-ttu-id="3a853-113">부</span><span class="sxs-lookup"><span data-stu-id="3a853-113">Minor</span></span>|
|<span data-ttu-id="3a853-114">버전</span><span class="sxs-lookup"><span data-stu-id="3a853-114">Version</span></span>|<span data-ttu-id="3a853-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="3a853-115">4.5.1</span></span>|
|<span data-ttu-id="3a853-116">형식</span><span class="sxs-lookup"><span data-stu-id="3a853-116">Type</span></span>|<span data-ttu-id="3a853-117">런타임</span><span class="sxs-lookup"><span data-stu-id="3a853-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3a853-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3a853-118">Affected APIs</span></span>

<span data-ttu-id="3a853-119">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a853-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
