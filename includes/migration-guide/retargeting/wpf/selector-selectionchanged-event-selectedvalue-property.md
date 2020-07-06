---
ms.openlocfilehash: 0ef39d67cd4335658658f5772b5bce49d827cad0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614935"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a><span data-ttu-id="b2281-101">선택기 SelectionChanged 이벤트 및 SelectedValue 속성</span><span class="sxs-lookup"><span data-stu-id="b2281-101">Selector SelectionChanged event and SelectedValue property</span></span>

#### <a name="details"></a><span data-ttu-id="b2281-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="b2281-102">Details</span></span>

<span data-ttu-id="b2281-103">.NET Framework 4.7.1부터 <xref:System.Windows.Controls.Primitives.Selector>는 해당 선택 항목이 변경될 때 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트를 발생시키기 전에 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 속성의 값을 항상 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b2281-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.Primitives.Selector> always updates the value of its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.</span></span> <span data-ttu-id="b2281-104">이렇게 하면 SelectedValue 속성은 이벤트를 발생시키기 전에 업데이트되는 다른 선택 속성(<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> 및 <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>)과 일치하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2281-104">This makes the SelectedValue property consistent with the other selection properties (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> and <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), which are updated before raising the event.</span></span><p/><span data-ttu-id="b2281-105">.NET Framework 4.7 및 이전 버전에서 대부분의 경우 이벤트 이전에 SelectedValue에 대한 업데이트가 발생했지만 선택 항목 변경이 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 속성 변경으로 인해 발생한 경우 이벤트 이후에 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="b2281-105">In the .NET Framework 4.7 and earlier versions, the update to SelectedValue happened before the event in most cases, but it happened after the event if the selection change was caused by changing the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b2281-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="b2281-106">Suggestion</span></span>

<span data-ttu-id="b2281-107">.NET Framework 4.7.1 이상을 대상으로 하는 앱은 애플리케이션 구성 파일의 `<runtime>` 섹션에 다음을 추가하여 이 변경을 옵트아웃하고 레거시 동작을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2281-107">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="b2281-108">.NET Framework 4.7 이하를 대상으로 하지만 .NET Framework 4.7.1 이상에서 실행되는 앱은 애플리케이션 .configuration 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 새 동작을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2281-108">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="b2281-109">이름</span><span class="sxs-lookup"><span data-stu-id="b2281-109">Name</span></span>    | <span data-ttu-id="b2281-110">값</span><span class="sxs-lookup"><span data-stu-id="b2281-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b2281-111">Scope</span><span class="sxs-lookup"><span data-stu-id="b2281-111">Scope</span></span>   | <span data-ttu-id="b2281-112">부</span><span class="sxs-lookup"><span data-stu-id="b2281-112">Minor</span></span>       |
| <span data-ttu-id="b2281-113">버전</span><span class="sxs-lookup"><span data-stu-id="b2281-113">Version</span></span> | <span data-ttu-id="b2281-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b2281-114">4.7.1</span></span>       |
| <span data-ttu-id="b2281-115">형식</span><span class="sxs-lookup"><span data-stu-id="b2281-115">Type</span></span>    | <span data-ttu-id="b2281-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="b2281-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b2281-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b2281-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
