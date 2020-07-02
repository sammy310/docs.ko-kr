---
ms.openlocfilehash: 8f03e5166e7f1f598e9bba7fb8c550809f287b82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615647"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="fdb08-101">HtmlTextWriter가 `<br/>` 요소를 올바르게 렌더링하지 않음</span><span class="sxs-lookup"><span data-stu-id="fdb08-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

#### <a name="details"></a><span data-ttu-id="fdb08-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="fdb08-102">Details</span></span>

<span data-ttu-id="fdb08-103">.NET Framework 4.6부터 `<BR />` 요소로 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> 및 <xref:System.Web.UI.HtmlTextWriter.RenderEndTag>를 호출하면 (두 개가 아닌) 단 하나의 `<BR />`만 올바르게 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb08-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a `<BR />` element will correctly insert only one `<BR />` (instead of two)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fdb08-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="fdb08-104">Suggestion</span></span>

<span data-ttu-id="fdb08-105">응용 프로그램이 추가 `<BR />` 태그에 종속된 경우 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)>를 두 번째로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdb08-105">If an app depended on the extra `<BR />` tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="fdb08-106">이 동작 변경은 .NET Framework 4.6 이상을 대상으로 하는 응용 프로그램에만 영향을 주므로 다른 옵션은 이전 버전의 .NET Framework를 대상으로 하여 이전 동작을 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fdb08-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>

| <span data-ttu-id="fdb08-107">이름</span><span class="sxs-lookup"><span data-stu-id="fdb08-107">Name</span></span>    | <span data-ttu-id="fdb08-108">값</span><span class="sxs-lookup"><span data-stu-id="fdb08-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fdb08-109">Scope</span><span class="sxs-lookup"><span data-stu-id="fdb08-109">Scope</span></span>   | <span data-ttu-id="fdb08-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fdb08-110">Edge</span></span>        |
| <span data-ttu-id="fdb08-111">버전</span><span class="sxs-lookup"><span data-stu-id="fdb08-111">Version</span></span> | <span data-ttu-id="fdb08-112">4.6</span><span class="sxs-lookup"><span data-stu-id="fdb08-112">4.6</span></span>         |
| <span data-ttu-id="fdb08-113">형식</span><span class="sxs-lookup"><span data-stu-id="fdb08-113">Type</span></span>    | <span data-ttu-id="fdb08-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="fdb08-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="fdb08-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="fdb08-115">Affected APIs</span></span>

- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType>
- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType>
