---
ms.openlocfilehash: e600b8249096eecb13f63ea00343a771a8c12b60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804440"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="e0842-101">HtmlTextWriter가 `<br/>` 요소를 올바르게 렌더링하지 않음</span><span class="sxs-lookup"><span data-stu-id="e0842-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e0842-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e0842-102">Details</span></span>|<span data-ttu-id="e0842-103">.NET Framework 4.6부터 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> 요소로 <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> 및 <code>&lt;BR /&gt;</code>를 호출하면 (두 개가 아닌) 단 하나의 <code>&lt;BR /&gt;</code>만 올바르게 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="e0842-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a <code>&lt;BR /&gt;</code> element will correctly insert only one <code>&lt;BR /&gt;</code> (instead of two)</span></span>|
|<span data-ttu-id="e0842-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e0842-104">Suggestion</span></span>|<span data-ttu-id="e0842-105">응용 프로그램이 추가 <code>&lt;BR /&gt;</code> 태그에 종속된 경우 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)>를 두 번째로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0842-105">If an app depended on the extra <code>&lt;BR /&gt;</code> tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="e0842-106">이 동작 변경은 .NET Framework 4.6 이상을 대상으로 하는 응용 프로그램에만 영향을 주므로 다른 옵션은 이전 버전의 .NET Framework를 대상으로 하여 이전 동작을 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0842-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>|
|<span data-ttu-id="e0842-107">범위</span><span class="sxs-lookup"><span data-stu-id="e0842-107">Scope</span></span>|<span data-ttu-id="e0842-108">가장자리</span><span class="sxs-lookup"><span data-stu-id="e0842-108">Edge</span></span>|
|<span data-ttu-id="e0842-109">Version</span><span class="sxs-lookup"><span data-stu-id="e0842-109">Version</span></span>|<span data-ttu-id="e0842-110">4.6</span><span class="sxs-lookup"><span data-stu-id="e0842-110">4.6</span></span>|
|<span data-ttu-id="e0842-111">형식</span><span class="sxs-lookup"><span data-stu-id="e0842-111">Type</span></span>|<span data-ttu-id="e0842-112">대상 변경</span><span class="sxs-lookup"><span data-stu-id="e0842-112">Retargeting</span></span>|
|<span data-ttu-id="e0842-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e0842-113">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|
