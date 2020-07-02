---
ms.openlocfilehash: 22b5abbe769733e8d5ca3e78dd9e6e13b2363737
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620309"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="80202-101">다른 4.5 SQL 생성에서 더 간단한 4.0 SQL 생성으로 되돌리는 옵트인 문제</span><span class="sxs-lookup"><span data-stu-id="80202-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

#### <a name="details"></a><span data-ttu-id="80202-102">설명</span><span class="sxs-lookup"><span data-stu-id="80202-102">Details</span></span>

<span data-ttu-id="80202-103">OrderBy를 먼저 사용하지 않고 JOIN 문을 생성하고 제한 작업에 대한 호출을 포함하는 쿼리가 이제 보다 단순한 SQL을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="80202-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="80202-104">.NET Framework 4.5로 업그레이드한 후 이러한 쿼리는 이전 버전보다 더욱 복잡한 SQL을 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="80202-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="80202-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="80202-105">Suggestion</span></span>

<span data-ttu-id="80202-106">이 기능은 기본적으로 비활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80202-106">This feature is disabled by default.</span></span> <span data-ttu-id="80202-107">Entity Framework가 성능 저하를 일으키는 추가 JOIN 문을 생성하는 경우 다음의 항목을 애플리케이션 구성 파일(app.config)의 <code>&lt;appSettings&gt;</code> 섹션에 추가하여 이 기능을 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80202-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="80202-108">이름</span><span class="sxs-lookup"><span data-stu-id="80202-108">Name</span></span>    | <span data-ttu-id="80202-109">값</span><span class="sxs-lookup"><span data-stu-id="80202-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="80202-110">Scope</span><span class="sxs-lookup"><span data-stu-id="80202-110">Scope</span></span>   |<span data-ttu-id="80202-111">투명</span><span class="sxs-lookup"><span data-stu-id="80202-111">Transparent</span></span>|
|<span data-ttu-id="80202-112">버전</span><span class="sxs-lookup"><span data-stu-id="80202-112">Version</span></span>|<span data-ttu-id="80202-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="80202-113">4.5.2</span></span>|
|<span data-ttu-id="80202-114">형식</span><span class="sxs-lookup"><span data-stu-id="80202-114">Type</span></span>|<span data-ttu-id="80202-115">런타임</span><span class="sxs-lookup"><span data-stu-id="80202-115">Runtime</span></span>|
