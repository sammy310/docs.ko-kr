---
ms.openlocfilehash: 4d210eeedd2f228017634d29f11554deb6ed8079
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496827"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a><span data-ttu-id="ee4d5-101">AllowCustomPaging이 true로 설정된 GridView는 보기의 마지막 페이지를 벗어날 때 PageIndexChanging 이벤트를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee4d5-101">GridViews with AllowCustomPaging set to true may fire the PageIndexChanging event when leaving the final page of the view</span></span>

#### <a name="details"></a><span data-ttu-id="ee4d5-102">설명</span><span class="sxs-lookup"><span data-stu-id="ee4d5-102">Details</span></span>

<span data-ttu-id="ee4d5-103">.NET Framework 4.5의 버그로 인해 <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>이 활성화된 <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>에 대해 <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName>이 발생하지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee4d5-103">A bug in the .NET Framework 4.5 causes <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> to sometimes not fire for <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>s that have enabled <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ee4d5-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="ee4d5-104">Suggestion</span></span>

<span data-ttu-id="ee4d5-105">이 문제는 .NET Framework 4.6에서 해결되었으며, 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee4d5-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span> <span data-ttu-id="ee4d5-106">해결 방법으로, 앱은 이러한 조건을 만족하는 <code>Page_Load</code>에 대해 명시적 BindGrid를 수행할 수 있습니다(<xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>은 마지막 페이지에 있고 마지막 <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>은 <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>과 다름).</span><span class="sxs-lookup"><span data-stu-id="ee4d5-106">As a work-around, the app can do an explicit BindGrid on any <code>Page_Load</code> that would hit these conditions (the <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> is on the last page and Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> is different from <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span></span> <span data-ttu-id="ee4d5-107">또는, 해당 시나리오는 문제를 보여주지 못하므로 (사용자 지정 페이징 대신) 페이징을 허용하도록 앱을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee4d5-107">Alternatively, the app can be modified to allow paging (instead of custom paging), as that scenario does not demonstrate the problem.</span></span>

| <span data-ttu-id="ee4d5-108">이름</span><span class="sxs-lookup"><span data-stu-id="ee4d5-108">Name</span></span>    | <span data-ttu-id="ee4d5-109">값</span><span class="sxs-lookup"><span data-stu-id="ee4d5-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ee4d5-110">Scope</span><span class="sxs-lookup"><span data-stu-id="ee4d5-110">Scope</span></span>   |<span data-ttu-id="ee4d5-111">부</span><span class="sxs-lookup"><span data-stu-id="ee4d5-111">Minor</span></span>|
|<span data-ttu-id="ee4d5-112">버전</span><span class="sxs-lookup"><span data-stu-id="ee4d5-112">Version</span></span>|<span data-ttu-id="ee4d5-113">4.5</span><span class="sxs-lookup"><span data-stu-id="ee4d5-113">4.5</span></span>|
|<span data-ttu-id="ee4d5-114">형식</span><span class="sxs-lookup"><span data-stu-id="ee4d5-114">Type</span></span>|<span data-ttu-id="ee4d5-115">런타임</span><span class="sxs-lookup"><span data-stu-id="ee4d5-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ee4d5-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ee4d5-116">Affected APIs</span></span>

- <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.UI.WebControls.GridView.AllowCustomPaging`

-->
