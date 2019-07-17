---
ms.openlocfilehash: e605e0f2636d83745815ec4ed27bf72692f18d15
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802671"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="8b27e-101">WebForms CheckBox 컨트롤에 대한 InputAttributes 및 LabelAttributes의 ASP.NET Fix 처리</span><span class="sxs-lookup"><span data-stu-id="8b27e-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8b27e-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8b27e-102">Details</span></span>|<span data-ttu-id="8b27e-103">.NET Framework 4.7.2 이하 버전을 대상으로 하는 애플리케이션의 경우, WebForms <xref:System.Web.UI.WebControls.CheckBox> 컨트롤에 프로그래밍 방식으로 추가된 <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> 및 <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType>는 포스트백 후에 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b27e-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="8b27e-104">.NET Framework 4.8 이상 버전을 대상으로 하는 애플리케이션의 경우, 포스트백 후 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b27e-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>|
|<span data-ttu-id="8b27e-105">제안</span><span class="sxs-lookup"><span data-stu-id="8b27e-105">Suggestion</span></span>|<span data-ttu-id="8b27e-106">포스트백에서 특성을 복원하는 올바른 동작을 위해 <code>targetFrameworkVersion</code>를 4.8 이상으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b27e-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="8b27e-107">예:</span><span class="sxs-lookup"><span data-stu-id="8b27e-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="8b27e-108">더 낮게 설정하거나 전혀 설정되지 않으면 이전의 잘못된 동작이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b27e-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>|
|<span data-ttu-id="8b27e-109">범위</span><span class="sxs-lookup"><span data-stu-id="8b27e-109">Scope</span></span>|<span data-ttu-id="8b27e-110">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="8b27e-110">Unknown</span></span>|
|<span data-ttu-id="8b27e-111">버전</span><span class="sxs-lookup"><span data-stu-id="8b27e-111">Version</span></span>|<span data-ttu-id="8b27e-112">4.8</span><span class="sxs-lookup"><span data-stu-id="8b27e-112">4.8</span></span>|
|<span data-ttu-id="8b27e-113">Type</span><span class="sxs-lookup"><span data-stu-id="8b27e-113">Type</span></span>|<span data-ttu-id="8b27e-114">런타임</span><span class="sxs-lookup"><span data-stu-id="8b27e-114">Runtime</span></span>|
|<span data-ttu-id="8b27e-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="8b27e-115">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|

