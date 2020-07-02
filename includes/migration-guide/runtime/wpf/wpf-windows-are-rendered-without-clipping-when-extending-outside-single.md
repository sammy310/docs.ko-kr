---
ms.openlocfilehash: d276e2bbf24c8b2389a0a8078c62c327c3729d50
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621357"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="e3a8e-101">WPF 창이 단일 모니터 외부로 확장될 때 잘림 없이 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3a8e-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

#### <a name="details"></a><span data-ttu-id="e3a8e-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e3a8e-102">Details</span></span>

<span data-ttu-id="e3a8e-103">Windows 8 이상에서 실행되는 .NET Framework 4.6에서, 다중 모니터 시나리오에서 전체 창이 단일 디스플레이를 벗어나 확장되는 경우 잘림 없이 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3a8e-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="e3a8e-104">이는 단일 디스플레이를 벗어나 확장된 WPF 창을 잘라 냈던 이전 버전의 .NET Framework와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e3a8e-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e3a8e-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e3a8e-105">Suggestion</span></span>

<span data-ttu-id="e3a8e-106">이 동작(잘라 내는지 여부)은 애플리케이션 구성 파일의 <code>&lt;appSettings&gt;</code>에 있는 <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> 요소를 사용하거나 앱 시작 시 <code>EnableMultiMonitorDisplayClipping</code> 속성을 설정하여 명시적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3a8e-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>

| <span data-ttu-id="e3a8e-107">이름</span><span class="sxs-lookup"><span data-stu-id="e3a8e-107">Name</span></span>    | <span data-ttu-id="e3a8e-108">값</span><span class="sxs-lookup"><span data-stu-id="e3a8e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e3a8e-109">Scope</span><span class="sxs-lookup"><span data-stu-id="e3a8e-109">Scope</span></span>   |<span data-ttu-id="e3a8e-110">부</span><span class="sxs-lookup"><span data-stu-id="e3a8e-110">Minor</span></span>|
|<span data-ttu-id="e3a8e-111">버전</span><span class="sxs-lookup"><span data-stu-id="e3a8e-111">Version</span></span>|<span data-ttu-id="e3a8e-112">4.6</span><span class="sxs-lookup"><span data-stu-id="e3a8e-112">4.6</span></span>|
|<span data-ttu-id="e3a8e-113">형식</span><span class="sxs-lookup"><span data-stu-id="e3a8e-113">Type</span></span>|<span data-ttu-id="e3a8e-114">런타임</span><span class="sxs-lookup"><span data-stu-id="e3a8e-114">Runtime</span></span>|
