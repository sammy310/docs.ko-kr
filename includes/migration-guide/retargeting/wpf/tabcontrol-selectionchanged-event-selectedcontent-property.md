---
ms.openlocfilehash: dfdb62e8dd6db67d4fd12aba93928f4615e3f284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614949"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a><span data-ttu-id="2eb13-101">TabControl SelectionChanged 이벤트 및 SelectedContent 속성</span><span class="sxs-lookup"><span data-stu-id="2eb13-101">TabControl SelectionChanged event and SelectedContent property</span></span>

#### <a name="details"></a><span data-ttu-id="2eb13-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="2eb13-102">Details</span></span>

<span data-ttu-id="2eb13-103">4.7.1,.NET Framework부터는 선택 항목이 변경될 때 <xref:System.Windows.Controls.TabControl>이 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트를 발생시키기 전에 <xref:System.Windows.Controls.TabControl.SelectedContent> 속성 값을 업데이트합니다. .NET Framework 4.7 및 이전 버전에서는 SelectedContent에 대한 업데이트가 이벤트 이후에 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="2eb13-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.TabControl> updates the value of its <xref:System.Windows.Controls.TabControl.SelectedContent> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.In the .NET Framework 4.7 and earlier versions, the update to SelectedContent happened after the event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2eb13-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="2eb13-104">Suggestion</span></span>

<span data-ttu-id="2eb13-105">.NET Framework 4.7.1 이상을 대상으로 하는 앱은 애플리케이션 구성 파일의 `<runtime>` 섹션에 다음을 추가하여 이 변경을 옵트아웃하고 레거시 동작을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eb13-105">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="2eb13-106">.NET Framework 4.7 이하를 대상으로 하지만 .NET Framework 4.7.1 이상에서 실행되는 앱은 애플리케이션 .configuration 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 새 동작을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eb13-106">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="2eb13-107">이름</span><span class="sxs-lookup"><span data-stu-id="2eb13-107">Name</span></span>    | <span data-ttu-id="2eb13-108">값</span><span class="sxs-lookup"><span data-stu-id="2eb13-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2eb13-109">Scope</span><span class="sxs-lookup"><span data-stu-id="2eb13-109">Scope</span></span>   | <span data-ttu-id="2eb13-110">부</span><span class="sxs-lookup"><span data-stu-id="2eb13-110">Minor</span></span>       |
| <span data-ttu-id="2eb13-111">버전</span><span class="sxs-lookup"><span data-stu-id="2eb13-111">Version</span></span> | <span data-ttu-id="2eb13-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="2eb13-112">4.7.1</span></span>       |
| <span data-ttu-id="2eb13-113">형식</span><span class="sxs-lookup"><span data-stu-id="2eb13-113">Type</span></span>    | <span data-ttu-id="2eb13-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="2eb13-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2eb13-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2eb13-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
