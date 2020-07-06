---
ms.openlocfilehash: f907cb1939e111c586d68243e6b8a8e291974e36
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615724"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a><span data-ttu-id="792a4-101">여백의 WPF 레이아웃 반올림이 변경됨</span><span class="sxs-lookup"><span data-stu-id="792a4-101">WPF layout rounding of margins has changed</span></span>

#### <a name="details"></a><span data-ttu-id="792a4-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="792a4-102">Details</span></span>

<span data-ttu-id="792a4-103">여백이 반올림되는 방식과 그 안의 테두리 및 배경이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="792a4-103">The way in which margins are rounded and borders and the background inside of them has changed.</span></span> <span data-ttu-id="792a4-104">레이아웃을 변경한 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="792a4-104">As a result of this change:</span></span>

- <span data-ttu-id="792a4-105">요소의 너비나 높이가 최대 1픽셀씩 늘어나거나 줄어들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792a4-105">The width or height of elements may grow or shrink by at most one pixel.</span></span>
- <span data-ttu-id="792a4-106">개체의 배치가 최대 1픽셀씩 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792a4-106">The placement of an object can move by at most one pixel.</span></span>
- <span data-ttu-id="792a4-107">가운데 맞춤 요소가 가로 또는 세로로 최대 1픽셀씩 가운데에서 벗어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792a4-107">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>
<span data-ttu-id="792a4-108">기본적으로 이 새 레이아웃은 .NET Framework 4.6을 대상으로 하는 앱에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792a4-108">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="792a4-109">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="792a4-109">Suggestion</span></span>

<span data-ttu-id="792a4-110">이 수정은 높은 DPI에서 WPF 컨트롤의 오른쪽 또는 아래쪽의 클리핑을 제거하는 경향이 있으므로 이전 버전의 .NET Framework를 대상으로 하지만 NET Framework 4.6에서 실행되는 앱은 다음 줄을 app.config 파일의 `<runtime>` 섹션에 추가하여 이 새 동작을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792a4-110">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>

<span data-ttu-id="792a4-111">.NET Framework 4.6을 대상으로 하지만 이전 레이아웃 알고리즘을 사용하여 WPF 컨트롤을 렌더링하려는 앱은 다음 줄을 app.config 파일의 `<runtime>` 섹션에 추가하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792a4-111">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>

| <span data-ttu-id="792a4-112">이름</span><span class="sxs-lookup"><span data-stu-id="792a4-112">Name</span></span>    | <span data-ttu-id="792a4-113">값</span><span class="sxs-lookup"><span data-stu-id="792a4-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="792a4-114">Scope</span><span class="sxs-lookup"><span data-stu-id="792a4-114">Scope</span></span>   | <span data-ttu-id="792a4-115">부</span><span class="sxs-lookup"><span data-stu-id="792a4-115">Minor</span></span>       |
| <span data-ttu-id="792a4-116">버전</span><span class="sxs-lookup"><span data-stu-id="792a4-116">Version</span></span> | <span data-ttu-id="792a4-117">4.6</span><span class="sxs-lookup"><span data-stu-id="792a4-117">4.6</span></span>         |
| <span data-ttu-id="792a4-118">형식</span><span class="sxs-lookup"><span data-stu-id="792a4-118">Type</span></span>    | <span data-ttu-id="792a4-119">대상 변경</span><span class="sxs-lookup"><span data-stu-id="792a4-119">Retargeting</span></span> |
