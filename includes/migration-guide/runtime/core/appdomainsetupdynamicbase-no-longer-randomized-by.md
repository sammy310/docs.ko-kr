---
ms.openlocfilehash: 08ad6fd4ccb6d5ddbbb4fa7ef1b325ce30689748
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621290"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a><span data-ttu-id="176f3-101">AppDomainSetup.DynamicBase는 더 이상 UseRandomizedStringHashAlgorithm에 의해 무작위화되지 않음</span><span class="sxs-lookup"><span data-stu-id="176f3-101">AppDomainSetup.DynamicBase is no longer randomized by UseRandomizedStringHashAlgorithm</span></span>

#### <a name="details"></a><span data-ttu-id="176f3-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="176f3-102">Details</span></span>

<span data-ttu-id="176f3-103">.NET Framework 4.6 이전에는, UseRandomizedStringHashAlgorithm이 앱의 구성 파일에서 활성화된 경우 애플리케이션 도메인 간 또는 프로세스 간에 <xref:System.AppDomainSetup.DynamicBase> 값이 무작위화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="176f3-103">Prior to the .NET Framework 4.6, the value of <xref:System.AppDomainSetup.DynamicBase> would be randomized between application domains, or between processes, if UseRandomizedStringHashAlgorithm was enabled in the app's config file.</span></span> <span data-ttu-id="176f3-104">.NET Framework 4.6부터 <xref:System.AppDomainSetup.DynamicBase>가 실행 중인 앱의 여러 인스턴스와 다른 앱 도메인 간에 안정적인 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="176f3-104">Beginning in the .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> will return a stable result between different instances of an app running, and between different app domains.</span></span> <span data-ttu-id="176f3-105">동적 기반은 여전히 앱에 따라 다릅니다. 이 변경은 동일한 앱의 다른 인스턴스에 대한 임의의 이름 지정 요소만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="176f3-105">Dynamic bases will still differ for different apps; this change only removes the random naming element for different instances of the same app.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="176f3-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="176f3-106">Suggestion</span></span>

<span data-ttu-id="176f3-107"><code>UseRandomizedStringHashAlgorithm</code>을 사용하도록 설정해도 <xref:System.AppDomainSetup.DynamicBase>가 무작위화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="176f3-107">Be aware that enabling <code>UseRandomizedStringHashAlgorithm</code> will not result in <xref:System.AppDomainSetup.DynamicBase> being randomized.</span></span> <span data-ttu-id="176f3-108">임의 기반이 필요한 경우 이 API를 통하지 않고 앱의 코드에서 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="176f3-108">If a random base is needed, it must be produced in your app's code rather than via this API.</span></span>

| <span data-ttu-id="176f3-109">이름</span><span class="sxs-lookup"><span data-stu-id="176f3-109">Name</span></span>    | <span data-ttu-id="176f3-110">값</span><span class="sxs-lookup"><span data-stu-id="176f3-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="176f3-111">Scope</span><span class="sxs-lookup"><span data-stu-id="176f3-111">Scope</span></span>   |<span data-ttu-id="176f3-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="176f3-112">Edge</span></span>|
|<span data-ttu-id="176f3-113">버전</span><span class="sxs-lookup"><span data-stu-id="176f3-113">Version</span></span>|<span data-ttu-id="176f3-114">4.6</span><span class="sxs-lookup"><span data-stu-id="176f3-114">4.6</span></span>|
|<span data-ttu-id="176f3-115">형식</span><span class="sxs-lookup"><span data-stu-id="176f3-115">Type</span></span>|<span data-ttu-id="176f3-116">런타임</span><span class="sxs-lookup"><span data-stu-id="176f3-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="176f3-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="176f3-117">Affected APIs</span></span>

-<xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
