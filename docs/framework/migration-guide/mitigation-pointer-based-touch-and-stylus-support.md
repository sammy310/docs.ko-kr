---
title: '완화: 포인터 기반 터치 및 스타일러스 지원'
description: .NET Framework 4.7을 대상으로 하는 WPF 앱에 대한 선택적 WPF 터치/스타일러스 스택을 사용하도록 설정하는 효과에 대해 알아봅니다.
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: d0c0effeaa727c615dddc3b92cdd34aafde65705
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475426"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="8cddf-103">완화: 포인터 기반 터치 및 스타일러스 지원</span><span class="sxs-lookup"><span data-stu-id="8cddf-103">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="8cddf-104">.NET Framework 4.7을 대상으로 하고 Windows 10 크리에이터 업데이트 버전 이상의 Windows에서 실행되는 WPF 애플리케이션은 선택적 `WM_POINTER` 기반 WPF 터치/스타일러스 스택을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-104">WPF applications that target the .NET Framework 4.7 and are running on Windows starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="8cddf-105">영향</span><span class="sxs-lookup"><span data-stu-id="8cddf-105">Impact</span></span>

<span data-ttu-id="8cddf-106">포인터 기반 터치/스타일러스 지원을 명시적으로 사용하지 않도록 하는 개발자는 WPF 터치/스타일러스 동작이 달라지지 않는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-106">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="8cddf-107">다음은 현재 선택적 `WM_POINTER` 기반 터치/스타일러스 스택의 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-107">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="8cddf-108">실시간 잉크 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-108">No support for real-time inking.</span></span>

   <span data-ttu-id="8cddf-109">잉크 입력 및 스타일러스 플러그 인은 계속 작동하지만 UI 스레드에서 처리되므로 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-109">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="8cddf-110">터치/스타일러스 이벤트에서 마우스 이벤트로 전환하는 방식의 변경으로 인해 동작이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-110">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="8cddf-111">조작이 다르게 동작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-111">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="8cddf-112">끌어서 놓기 작업이 터치 입력에 대해 적절한 피드백을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-112">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="8cddf-113">(이러한 문제가 스타일러스 입력에는 영향을 주지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="8cddf-113">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="8cddf-114">끌어서 놓기가 더 이상 터치/스타일러스 이벤트에서 시작될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-114">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="8cddf-115">이로 인해 마우스 입력이 감지될 때까지 애플리케이션이 응답하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-115">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="8cddf-116">대신, 개발자는 마우스 이벤트에서 끌어서 놓기를 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-116">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="8cddf-117">WM_POINTER 기반 터치/스타일러스 지원 옵트인(opt in)</span><span class="sxs-lookup"><span data-stu-id="8cddf-117">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="8cddf-118">이 스택을 사용하도록 설정하려는 개발자는 애플리케이션의 ‘app.config’ 파일에 다음을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-118">Developers who wish to enable this stack can add the following to their application's *app.config* file.</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="8cddf-119">이 항목을 제거하거나 해당 값을 `false`로 설정하면 이 선택적 스택이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cddf-119">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cddf-120">참조</span><span class="sxs-lookup"><span data-stu-id="8cddf-120">See also</span></span>

- [<span data-ttu-id="8cddf-121">애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="8cddf-121">Application compatibility</span></span>](application-compatibility.md)
