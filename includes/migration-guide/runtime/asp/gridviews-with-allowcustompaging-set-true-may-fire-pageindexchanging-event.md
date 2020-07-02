---
ms.openlocfilehash: 3b329bf5ba2af4d3ab9c3e203e99daba8ca0d0c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620138"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a>AllowCustomPaging이 true로 설정된 GridView는 보기의 마지막 페이지를 벗어날 때 PageIndexChanging 이벤트를 발생시킬 수 있습니다.

#### <a name="details"></a>설명

.NET Framework 4.5의 버그로 인해 <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>이 활성화된 <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>에 대해 <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName>이 발생하지 않는 경우가 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

이 문제는 .NET Framework 4.6에서 해결되었으며, 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다. 해결 방법으로, 앱은 이러한 조건을 만족하는 <code>Page_Load</code>에 대해 명시적 BindGrid를 수행할 수 있습니다(<xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>은 마지막 페이지에 있고 마지막 <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>은 <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>과 다름). 또는, 해당 시나리오는 문제를 보여주지 못하므로 (사용자 지정 페이징 대신) 페이징을 허용하도록 앱을 수정할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|
