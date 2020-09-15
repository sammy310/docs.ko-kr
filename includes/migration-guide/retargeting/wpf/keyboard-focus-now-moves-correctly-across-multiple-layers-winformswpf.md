---
ms.openlocfilehash: a82b720fd4e771481ea1142a88a095443afa0d5b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614946"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a><span data-ttu-id="22e46-101">키보드 포커스는 이제 WinForms/WPF 호스팅의 여러 계층에서 제대로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="22e46-101">Keyboard focus now moves correctly across multiple layers of WinForms/WPF hosting</span></span>

#### <a name="details"></a><span data-ttu-id="22e46-102">설명</span><span class="sxs-lookup"><span data-stu-id="22e46-102">Details</span></span>

<span data-ttu-id="22e46-103">차례로 WPF 컨트롤을 호스트하는 WinForms 컨트롤을 호스팅하는 WPF 애플리케이션을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="22e46-103">Consider a WPF application hosting a WinForms control which in turn hosts WPF controls.</span></span> <span data-ttu-id="22e46-104">사용자는 해당 계층의 첫 번째 또는 마지막 컨트롤이 WPF `System.Windows.Forms.Integration.ElementHost`이면 WinForms 계층에서 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22e46-104">Users may not be able to tab out of the WinForms layer if the first or last control in that layer is the WPF `System.Windows.Forms.Integration.ElementHost`.</span></span> <span data-ttu-id="22e46-105">이 변경 내용은 이 문제를 해결하고, 사용자는 이제 WinForms 계층에서 이동할 수 있습니다. WinForms 계층을 이스케이프하지 않는 포커스를 사용하는 자동화된 애플리케이션은 더 이상 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22e46-105">This change fixes this issue, and users are now able to tab out of the WinForms layer.Automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="22e46-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="22e46-106">Suggestion</span></span>

<span data-ttu-id="22e46-107">.NET 4.7.2 이전의 프레임워크 버전을 대상으로 하는 동안 이 변경 내용을 활용하려는 개발자는 변경 내용을 활성화하기 위해 false로 AppContext 플래그의 다음 집합을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22e46-107">A developer who wants to utilize this change while targeting a framework version below .NET 4.7.2 can set the following set of AppContext flags to false for the change to be enabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="22e46-108">WPF 애플리케이션은 최신 개선 사항을 가져오도록 모든 초기 접근성 개선 사항으로 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22e46-108">WPF applications must opt in to all early accessibility improvements to get the later improvements.</span></span> <span data-ttu-id="22e46-109">즉, `Switch.UseLegacyAccessibilityFeatures` 및 `Switch.UseLegacyAccessibilityFeatures.2` 스위치 모두는 .NET 4.7.2 이상을 대상으로 하는 동안 이전 기능을 필요로 하는 A 개발자가 변경 내용을 활성화하지 못하도록 다음 AppContext 플래그를 true로 설정할 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22e46-109">In other words, both the `Switch.UseLegacyAccessibilityFeatures` and the `Switch.UseLegacyAccessibilityFeatures.2` switches must be setA developer who requires the previous functionality while targeting .NET 4.7.2 or greater can set the following AppContext flag to true for the change to be disabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="22e46-110">이름</span><span class="sxs-lookup"><span data-stu-id="22e46-110">Name</span></span>    | <span data-ttu-id="22e46-111">값</span><span class="sxs-lookup"><span data-stu-id="22e46-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="22e46-112">Scope</span><span class="sxs-lookup"><span data-stu-id="22e46-112">Scope</span></span>   | <span data-ttu-id="22e46-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="22e46-113">Edge</span></span>        |
| <span data-ttu-id="22e46-114">버전</span><span class="sxs-lookup"><span data-stu-id="22e46-114">Version</span></span> | <span data-ttu-id="22e46-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="22e46-115">4.7.2</span></span>       |
| <span data-ttu-id="22e46-116">형식</span><span class="sxs-lookup"><span data-stu-id="22e46-116">Type</span></span>    | <span data-ttu-id="22e46-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="22e46-117">Retargeting</span></span> |
