---
ms.openlocfilehash: eb89cbc72d8b09fd1aa5bc775a6c539eb208fa70
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614893"
---
### <a name="wpf-pointer-based-touch-stack"></a><span data-ttu-id="792f8-101">WPF 포인터 기반 터치 스택</span><span class="sxs-lookup"><span data-stu-id="792f8-101">WPF Pointer-Based Touch Stack</span></span>

#### <a name="details"></a><span data-ttu-id="792f8-102">설명</span><span class="sxs-lookup"><span data-stu-id="792f8-102">Details</span></span>

<span data-ttu-id="792f8-103">이러한 변경은 WM_POINTER 기반의 WPF 터치/스타일러스 스택 옵션을 사용할 수 있는 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-103">This change adds the ability to enable an optional WM_POINTER based WPF touch/stylus stack.</span></span>  <span data-ttu-id="792f8-104">이 기능을 명시적으로 활성화하지 않은 개발자는 WPF 터치/스타일러스 동작을 변경하지 않아야 합니다. WM_POINTER 기반 터치/스타일러스 스택 옵션과 관련하여 현재 알려진 문제점:</span><span class="sxs-lookup"><span data-stu-id="792f8-104">Developers that do not explicitly enable this should see no change in WPF touch/stylus behavior.Current Known Issues With optional WM_POINTER based touch/stylus stack:</span></span>

- <span data-ttu-id="792f8-105">실시간 잉크 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-105">No support for real-time inking.</span></span>
- <span data-ttu-id="792f8-106">수동 입력 및 StylusPlugins는 계속 작동하지만 UI 스레드에서 처리되므로 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-106">While inking and StylusPlugins will still work, they will be processed on the UI Thread which can lead to poor performance.</span></span>
- <span data-ttu-id="792f8-107">터치/스타일러스 이벤트에서 마우스 이벤트로 전환하는 방식의 변경으로 인해 동작 변경</span><span class="sxs-lookup"><span data-stu-id="792f8-107">Behavioral changes due to changes in promotion from touch/stylus events to mouse events</span></span>
- <span data-ttu-id="792f8-108">조작이 다르게 동작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-108">Manipulation may behave differently</span></span>
- <span data-ttu-id="792f8-109">끌어서 놓기 작업이 터치 입력에 대해 적절한 피드백을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-109">Drag/Drop will not show appropriate feedback for touch input</span></span>
- <span data-ttu-id="792f8-110">이러한 문제가 스타일러스 입력에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-110">This does not affect stylus input</span></span>
- <span data-ttu-id="792f8-111">끌어서 놓기가 더 이상 터치/스타일러스 이벤트에서 시작될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-111">Drag/Drop can no longer be initiated on touch/stylus events</span></span>
- <span data-ttu-id="792f8-112">이로 인해 마우스 입력이 감지될 때까지 애플리케이션이 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-112">This can potentially hang the application until mouse input is detected.</span></span>
- <span data-ttu-id="792f8-113">대신, 개발자는 마우스 이벤트에서 끌어서 놓기를 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-113">Instead, developers should initiate drag and drop from mouse events.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="792f8-114">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="792f8-114">Suggestion</span></span>

<span data-ttu-id="792f8-115">이 스택을 사용하도록 설정하려는 개발자는 애플리케이션의 App.config 파일에 다음을 추가/병합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-115">Developers who wish to enable this stack can add/merge the following to their application's App.config file:</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="792f8-116">이것을 제거하거나 값을 false로 설정하면 이 스택 옵션이 꺼집니다. 이 스택은 Windows 10 크리에이터스 이상에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="792f8-116">Removing this or setting the value to false will turn this optional stack off.Note that this stack is available only on Windows 10 Creators Update and above.</span></span>

| <span data-ttu-id="792f8-117">이름</span><span class="sxs-lookup"><span data-stu-id="792f8-117">Name</span></span>    | <span data-ttu-id="792f8-118">값</span><span class="sxs-lookup"><span data-stu-id="792f8-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="792f8-119">Scope</span><span class="sxs-lookup"><span data-stu-id="792f8-119">Scope</span></span>   | <span data-ttu-id="792f8-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="792f8-120">Edge</span></span>        |
| <span data-ttu-id="792f8-121">버전</span><span class="sxs-lookup"><span data-stu-id="792f8-121">Version</span></span> | <span data-ttu-id="792f8-122">4.7</span><span class="sxs-lookup"><span data-stu-id="792f8-122">4.7</span></span>         |
| <span data-ttu-id="792f8-123">형식</span><span class="sxs-lookup"><span data-stu-id="792f8-123">Type</span></span>    | <span data-ttu-id="792f8-124">대상 변경</span><span class="sxs-lookup"><span data-stu-id="792f8-124">Retargeting</span></span> |
