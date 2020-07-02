---
ms.openlocfilehash: f8e5dee9e97956cea78b7c8ec999af1afe9ac66b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620366"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="4c5a7-101">MinFreeMemoryPercentageToActiveService가 지금 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a7-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="4c5a7-102">설명</span><span class="sxs-lookup"><span data-stu-id="4c5a7-102">Details</span></span>

<span data-ttu-id="4c5a7-103">이 설정은 WCF 서비스 활성화를 위해 서버에서 사용할 수 있는 최소 메모리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a7-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="4c5a7-104">또한 이 설정은 <xref:System.OutOfMemoryException?displayProperty=fullName> 예외가 발생되지 않도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a7-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="4c5a7-105">.NET Framework 4.5에서 이 설정은 영향을 주지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a7-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="4c5a7-106">.NET Framework 4.5.1에서 해당 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a7-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4c5a7-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="4c5a7-107">Suggestion</span></span>

<span data-ttu-id="4c5a7-108">웹 서버의 사용 가능한 메모리가 구성 설정에서 정의된 백분율보다 적은 경우 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a7-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="4c5a7-109">성공적으로 시작되었지만 제한된 메모리 환경에서 실행되는 일부 WCF 서비스의 경우 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a7-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="4c5a7-110">이름</span><span class="sxs-lookup"><span data-stu-id="4c5a7-110">Name</span></span>    | <span data-ttu-id="4c5a7-111">값</span><span class="sxs-lookup"><span data-stu-id="4c5a7-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4c5a7-112">Scope</span><span class="sxs-lookup"><span data-stu-id="4c5a7-112">Scope</span></span>   |<span data-ttu-id="4c5a7-113">부</span><span class="sxs-lookup"><span data-stu-id="4c5a7-113">Minor</span></span>|
|<span data-ttu-id="4c5a7-114">버전</span><span class="sxs-lookup"><span data-stu-id="4c5a7-114">Version</span></span>|<span data-ttu-id="4c5a7-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="4c5a7-115">4.5.1</span></span>|
|<span data-ttu-id="4c5a7-116">형식</span><span class="sxs-lookup"><span data-stu-id="4c5a7-116">Type</span></span>|<span data-ttu-id="4c5a7-117">런타임</span><span class="sxs-lookup"><span data-stu-id="4c5a7-117">Runtime</span></span>|
