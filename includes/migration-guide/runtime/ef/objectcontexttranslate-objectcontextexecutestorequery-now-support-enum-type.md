---
ms.openlocfilehash: 6af8e97423c04abca25feb8d77ea9ab6e198a4f0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620329"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="4157c-101">이제 ObjectContext.Translate와 ObjectContext.ExecuteStoreQuery가 열거형 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4157c-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

#### <a name="details"></a><span data-ttu-id="4157c-102">설명</span><span class="sxs-lookup"><span data-stu-id="4157c-102">Details</span></span>

<span data-ttu-id="4157c-103">.NET Framework 4.0에서는 <code>ObjectContext.Translate</code> 및 <code>ObjectContext.ExecuteStoreQuery</code> 메서드의 제네릭 매개 변수 <code>T</code>가 열거형일 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="4157c-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="4157c-104">이제 이 시나리오가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4157c-104">That scenario is now supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4157c-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="4157c-105">Suggestion</span></span>

<span data-ttu-id="4157c-106">.NET Framework 4.0의 열거형 형식에서 좌표 이동 또는 ExecuteStoreQuery가 호출되면 ‘0’이 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4157c-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="4157c-107">해당 동작이 필요한 경우 호출은 상수 0(또는 열거형 해당 항목)으로 대체되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4157c-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>

| <span data-ttu-id="4157c-108">이름</span><span class="sxs-lookup"><span data-stu-id="4157c-108">Name</span></span>    | <span data-ttu-id="4157c-109">값</span><span class="sxs-lookup"><span data-stu-id="4157c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4157c-110">Scope</span><span class="sxs-lookup"><span data-stu-id="4157c-110">Scope</span></span>   |<span data-ttu-id="4157c-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4157c-111">Edge</span></span>|
|<span data-ttu-id="4157c-112">버전</span><span class="sxs-lookup"><span data-stu-id="4157c-112">Version</span></span>|<span data-ttu-id="4157c-113">4.5</span><span class="sxs-lookup"><span data-stu-id="4157c-113">4.5</span></span>|
|<span data-ttu-id="4157c-114">형식</span><span class="sxs-lookup"><span data-stu-id="4157c-114">Type</span></span>|<span data-ttu-id="4157c-115">런타임</span><span class="sxs-lookup"><span data-stu-id="4157c-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4157c-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="4157c-116">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
