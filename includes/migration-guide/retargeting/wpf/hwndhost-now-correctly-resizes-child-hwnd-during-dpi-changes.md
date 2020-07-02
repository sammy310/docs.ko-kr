---
ms.openlocfilehash: 3d1dc8dec18212afd815aa3de7fc82c8a1f680dc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616283"
---
### <a name="hwndhost-now-correctly-resizes-child-hwnd-during-dpi-changes"></a><span data-ttu-id="65414-101">HwndHost는 이제 DPI 변경 중에 자식 HWND의 크기를 올바르게 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="65414-101">HwndHost now correctly resizes child-HWND during DPI changes</span></span>

#### <a name="details"></a><span data-ttu-id="65414-102">설명</span><span class="sxs-lookup"><span data-stu-id="65414-102">Details</span></span>

<span data-ttu-id="65414-103">.NET Framework 4.7.2 이하 버전에서 WPF가 모니터별 인식 모드로 실행될 때 애플리케이션을 모니터 간에 이동할 때와 같이 DPI 변경 후 <xref:System.Windows.Interop.HwndHost> 내에 호스팅되는 컨트롤의 크기가 올바르게 조정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="65414-103">In .NET Framework 4.7.2 and earlier versions, when WPF was run in Per-Monitor Aware mode, controls hosted within <xref:System.Windows.Interop.HwndHost> were not sized correctly after DPI changes, such as when moving applications from one monitor to another.</span></span> <span data-ttu-id="65414-104">이 수정을 통해 호스팅된 컨트롤의 크기가 적절하게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="65414-104">This fix ensures that hosted controls are sized appropriately.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="65414-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="65414-105">Suggestion</span></span>

<span data-ttu-id="65414-106">애플리케이션이 이러한 변경에서 이점을 활용하려면 .NET Framework 4.7.2 이상에서 실행해야 하며, 다음 예제와 같이 앱 구성 파일의 `<runtime>` 섹션에 있는 다음 [AppContext 스위치](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)를 `false`로 설정하여 이 동작을 옵트인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65414-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later, and it must opt-in to this behavior by setting the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) in the `<runtime>` section of the app config file to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="65414-107">이름</span><span class="sxs-lookup"><span data-stu-id="65414-107">Name</span></span>    | <span data-ttu-id="65414-108">값</span><span class="sxs-lookup"><span data-stu-id="65414-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65414-109">Scope</span><span class="sxs-lookup"><span data-stu-id="65414-109">Scope</span></span>   | <span data-ttu-id="65414-110">주요함</span><span class="sxs-lookup"><span data-stu-id="65414-110">Major</span></span>       |
| <span data-ttu-id="65414-111">버전</span><span class="sxs-lookup"><span data-stu-id="65414-111">Version</span></span> | <span data-ttu-id="65414-112">4.8</span><span class="sxs-lookup"><span data-stu-id="65414-112">4.8</span></span>         |
| <span data-ttu-id="65414-113">형식</span><span class="sxs-lookup"><span data-stu-id="65414-113">Type</span></span>    | <span data-ttu-id="65414-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="65414-114">Retargeting</span></span> |
