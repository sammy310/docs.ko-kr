---
ms.openlocfilehash: 7a7ecf052276fe8e62463498b83230d466630c79
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616279"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a><span data-ttu-id="af1ae-101">워크플로 XOML 정의 및 SqlTrackingService 캐시 키가 MD5에서 SHA256으로 변경됨</span><span class="sxs-lookup"><span data-stu-id="af1ae-101">Workflow XOML definition and SqlTrackingService cache keys changed from MD5 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="af1ae-102">설명</span><span class="sxs-lookup"><span data-stu-id="af1ae-102">Details</span></span>

<span data-ttu-id="af1ae-103">워크플로 런타임은 XOML에 정의된 워크플로 정의의 캐시를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="af1ae-103">The Workflow Runtime in keeps a cache of workflow definitions defined in XOML.</span></span> <span data-ttu-id="af1ae-104">또한 SqlTrackingService는 문자열에 의해 키가 지정된 캐시를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="af1ae-104">The SqlTrackingService also keeps a cache that is keyed by strings.</span></span> <span data-ttu-id="af1ae-105">이러한 캐시는 체크섬 해시 값을 포함하는 값에 의해 키가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="af1ae-105">These caches are keyed by values that include checksum hash value.</span></span> <span data-ttu-id="af1ae-106">.NET Framework 4.7.2 이전 버전에서 이 체크섬 해시는 MD5 알고리즘을 사용하여 FIPS 지원 시스템에 문제가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="af1ae-106">In the .NET Framework 4.7.2 and earlier versions, this checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="af1ae-107">.NET Framework 4.8부터 SHA256 알고리즘이 사용됩니다. 워크플로 런타임 및 SqlTrackingService를 시작할 때마다 값이 다시 계산되기 때문에 이 변경 내용과 호환성 문제가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af1ae-107">Starting with the .NET Framework 4.8, the algorithm used is SHA256.There shouldn't be a compatibility issue with this change because the values are recalculated each time the Workflow Runtime and SqlTrackingService is started.</span></span> <span data-ttu-id="af1ae-108">그러나 고객이 필요한 경우 레거시 해싱 알고리즘의 사용량으로 되돌릴 수 있는 쿼크를 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="af1ae-108">However, we have provided quirks to allow customers to revert back to usage of the legacy hashing algorithm, if necessary.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="af1ae-109">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="af1ae-109">Suggestion</span></span>

<span data-ttu-id="af1ae-110">워크플로를 실행할 때 이 변경으로 인해 문제가 발생하는 경우 `AppContext` 스위치 중 하나 또는 둘 다를 설정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="af1ae-110">If this change presents a problem when executing workflows, try setting one or both of the `AppContext` switches:</span></span>

- <span data-ttu-id="af1ae-111">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;를 true로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af1ae-111">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; to true.</span></span>
- <span data-ttu-id="af1ae-112">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;를 true로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af1ae-112">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; to true.</span></span>
<span data-ttu-id="af1ae-113">코드</span><span class="sxs-lookup"><span data-stu-id="af1ae-113">In code:</span></span>

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>

<span data-ttu-id="af1ae-114">또는 구성 파일(<xref:System.Workflow.Runtime.WorkflowRuntime> 개체를 만드는 애플리케이션의 구성 파일에 있어야 함):</span><span class="sxs-lookup"><span data-stu-id="af1ae-114">Or in the configuration file (this needs to be in the config file for the application that is creating the <xref:System.Workflow.Runtime.WorkflowRuntime> object):</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="af1ae-115">이름</span><span class="sxs-lookup"><span data-stu-id="af1ae-115">Name</span></span>    | <span data-ttu-id="af1ae-116">값</span><span class="sxs-lookup"><span data-stu-id="af1ae-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="af1ae-117">Scope</span><span class="sxs-lookup"><span data-stu-id="af1ae-117">Scope</span></span>   | <span data-ttu-id="af1ae-118">부</span><span class="sxs-lookup"><span data-stu-id="af1ae-118">Minor</span></span>       |
| <span data-ttu-id="af1ae-119">버전</span><span class="sxs-lookup"><span data-stu-id="af1ae-119">Version</span></span> | <span data-ttu-id="af1ae-120">4.8</span><span class="sxs-lookup"><span data-stu-id="af1ae-120">4.8</span></span>         |
| <span data-ttu-id="af1ae-121">형식</span><span class="sxs-lookup"><span data-stu-id="af1ae-121">Type</span></span>    | <span data-ttu-id="af1ae-122">대상 변경</span><span class="sxs-lookup"><span data-stu-id="af1ae-122">Retargeting</span></span> |
