---
title: '완화: WPF 창 렌더링'
ms.date: 03/30/2017
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
ms.openlocfilehash: 42d6abf1ba6ed7c17a5a5604e98b5ee46d0c3ac2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457773"
---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="9a29c-102">완화: WPF 창 렌더링</span><span class="sxs-lookup"><span data-stu-id="9a29c-102">Mitigation: WPF Window Rendering</span></span>

<span data-ttu-id="9a29c-103">Windows 8 이상에서 실행되는 .NET Framework 4.6에서, 다중 모니터 시나리오에서 전체 창이 단일 디스플레이를 벗어나 확장되는 경우 잘림 없이 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>

## <a name="impact"></a><span data-ttu-id="9a29c-104">영향</span><span class="sxs-lookup"><span data-stu-id="9a29c-104">Impact</span></span>

<span data-ttu-id="9a29c-105">일반적으로 다중 모니터에서 클리핑 없이 전체 창이 렌더링되는 것은 예상된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-105">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="9a29c-106">그러나 Windows 7 및 이전 버전에서 WPF 창이 단일 디스플레이를 벗어나 확장되면 두 번째 모니터 창의 일부를 렌더링할 때 성능에 큰 영향을 주기 때문에 WPF 창이 클리핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-106">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>

<span data-ttu-id="9a29c-107">Windows 8 이상에서 모니터 간의 WPF 창을 렌더링하는 작업에 미치는 영향은 수많은 요인에 따라 달라질 수 있으므로 정확하게 측정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-107">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="9a29c-108">경우에 따라서, 특히 그래픽 위주 애플리케이션을 실행하고 여러 모니터에 걸친 창을 사용하는 경우 성능에 원하지 않는 영향이 계속 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-108">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="9a29c-109">다른 경우에는 여러 .NET Framework 버전에서 일관된 동작이 발생하기를 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-109">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>

## <a name="mitigation"></a><span data-ttu-id="9a29c-110">완화</span><span class="sxs-lookup"><span data-stu-id="9a29c-110">Mitigation</span></span>

<span data-ttu-id="9a29c-111">이 변경을 사용하지 않도록 설정하고 단일 디스플레이를 벗어나 확장될 때 WPF 창을 클리핑하는 이전 동작으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-111">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="9a29c-112">이때 다음과 같은 두 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-112">There are two ways to do this:</span></span>

- <span data-ttu-id="9a29c-113">애플리케이션 구성 파일의 `<appSettings>` 섹션에 `<EnableMultiMonitorDisplayClipping>` 요소를 추가하여 Windows 8 이상에서 실행되는 앱에서 이 동작을 사용하지 않거나 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-113">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="9a29c-114">예를 들어 다음 구성 섹션은 클리핑 없이 렌더링을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-114">For example, the following configuration section disables rendering without clipping:</span></span>

  ```xml
  <appSettings>
      <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    </appSettings>
  ```

  <span data-ttu-id="9a29c-115">`<EnableMultiMonitorDisplayClipping>` 구성 설정에 다음 두 값 중 하나를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-115">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>

  - <span data-ttu-id="9a29c-116">`true`, 렌더링하는 동안 창의 클리핑이 범위를 모니터링하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-116">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>

  - <span data-ttu-id="9a29c-117">`false`, 렌더링하는 동안 창의 클리핑이 범위를 모니터링하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-117">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>

- <span data-ttu-id="9a29c-118">앱을 시작할 때 <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a29c-118">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a29c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a29c-119">See also</span></span>

- [<span data-ttu-id="9a29c-120">애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="9a29c-120">Application compatibility</span></span>](application-compatibility.md)
