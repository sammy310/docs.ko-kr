---
ms.openlocfilehash: 0fe07ac21effacffc56d37ccb46a121f443acd20
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620174"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="71c88-101">Asp.Net StateServer와 세션 상태를 공유하려면 웹 팜의 모든 서버가 동일한 .NET Framework 버전을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c88-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="71c88-102">설명</span><span class="sxs-lookup"><span data-stu-id="71c88-102">Details</span></span>

<span data-ttu-id="71c88-103"><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> 세션 상태를 활성화할 때 상태를 올바르게 공유하려면 지정된 웹 팜의 모든 서버가 동일한 .NET Framework 버전을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c88-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="71c88-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="71c88-104">Suggestion</span></span>

<span data-ttu-id="71c88-105">동시에 상태를 공유하는 웹 서버에서 .NET Framework 버전을 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c88-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="71c88-106">이름</span><span class="sxs-lookup"><span data-stu-id="71c88-106">Name</span></span>    | <span data-ttu-id="71c88-107">값</span><span class="sxs-lookup"><span data-stu-id="71c88-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="71c88-108">Scope</span><span class="sxs-lookup"><span data-stu-id="71c88-108">Scope</span></span>   |<span data-ttu-id="71c88-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="71c88-109">Edge</span></span>|
|<span data-ttu-id="71c88-110">버전</span><span class="sxs-lookup"><span data-stu-id="71c88-110">Version</span></span>|<span data-ttu-id="71c88-111">4.5</span><span class="sxs-lookup"><span data-stu-id="71c88-111">4.5</span></span>|
|<span data-ttu-id="71c88-112">형식</span><span class="sxs-lookup"><span data-stu-id="71c88-112">Type</span></span>|<span data-ttu-id="71c88-113">런타임</span><span class="sxs-lookup"><span data-stu-id="71c88-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="71c88-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="71c88-114">Affected APIs</span></span>

-<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
