---
ms.openlocfilehash: 86169b5c9a20678647153c951550e590a5bce588
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622261"
---
### <a name="resizing-a-grid-can-hang"></a><span data-ttu-id="c25c8-101">눈금 크기 조정이 중지될 수 있음</span><span class="sxs-lookup"><span data-stu-id="c25c8-101">Resizing a Grid can hang</span></span>

#### <a name="details"></a><span data-ttu-id="c25c8-102">설명</span><span class="sxs-lookup"><span data-stu-id="c25c8-102">Details</span></span>

<span data-ttu-id="c25c8-103">다음과 같은 경우 <code>T:System.Windows.Controls.Grid</code>의 레이아웃 중에 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c25c8-103">An infinite loop can occur during layout of a <code>T:System.Windows.Controls.Grid</code> under the following circumstances:</span></span><ul><li><span data-ttu-id="c25c8-104">행 정의는 MinHeight 및 MaxHeight를 선언하는 두 개의 \* 행을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c25c8-104">Row definitions contain two \*-rows, both declaring a MinHeight and a MaxHeight.</span></span></li><li><span data-ttu-id="c25c8-105">\* 행의 콘텐츠가 해당 MaxHeight를 초과하지 않음</span><span class="sxs-lookup"><span data-stu-id="c25c8-105">Content of the \*-rows doesn't exceed the corresponding MaxHeight</span></span></li><li><span data-ttu-id="c25c8-106">눈금의 사용 가능한 높이가 첫 번째 MinHeight(및 모든 고정 또는 자동 행)를 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="c25c8-106">The Grid's available height is exceeded by the first MinHeight (plus any other fixed or Auto rows)</span></span></li><li><span data-ttu-id="c25c8-107">앱이 .Net Framework 4.7을 대상으로 하거나 <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code>를 설정하여 4.7 할당 알고리즘으로 옵트인합니다.</span><span class="sxs-lookup"><span data-stu-id="c25c8-107">The app targets .NET Framework 4.7, or opts in to the 4.7 allocation algorithm by setting <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></span></span></li></ul><span data-ttu-id="c25c8-108">루프는 두 개가 넘는 행 또는 열의 유사한 경우에도 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c25c8-108">The loop would also happen with more than two rows, or in the analogous case for columns.</span></span> <span data-ttu-id="c25c8-109">이 문제는 .NET Framework 4.7.1에서 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="c25c8-109">The issue is fixed in .NET Framework 4.7.1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c25c8-110">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c25c8-110">Suggestion</span></span>

<span data-ttu-id="c25c8-111">.NET Framework 4.7.1로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="c25c8-111">Upgrade to .NET Framework 4.7.1.</span></span>  <span data-ttu-id="c25c8-112">또는 4.7 할당 알고리즘이 필요하지 않은 경우, 다음 구성 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c25c8-112">Alternatively, if you don't need the 4.7 allocation algorithm you can use the following configuration setting:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="c25c8-113">이름</span><span class="sxs-lookup"><span data-stu-id="c25c8-113">Name</span></span>    | <span data-ttu-id="c25c8-114">값</span><span class="sxs-lookup"><span data-stu-id="c25c8-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c25c8-115">Scope</span><span class="sxs-lookup"><span data-stu-id="c25c8-115">Scope</span></span>   |<span data-ttu-id="c25c8-116">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c25c8-116">Edge</span></span>|
|<span data-ttu-id="c25c8-117">버전</span><span class="sxs-lookup"><span data-stu-id="c25c8-117">Version</span></span>|<span data-ttu-id="c25c8-118">4.7</span><span class="sxs-lookup"><span data-stu-id="c25c8-118">4.7</span></span>|
|<span data-ttu-id="c25c8-119">형식</span><span class="sxs-lookup"><span data-stu-id="c25c8-119">Type</span></span>|<span data-ttu-id="c25c8-120">런타임</span><span class="sxs-lookup"><span data-stu-id="c25c8-120">Runtime</span></span>|
