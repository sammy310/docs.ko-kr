---
ms.openlocfilehash: 811b1a91169eeebfa056d9ecdb07d342d3b32d85
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615713"
---
### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a><span data-ttu-id="b5d2e-101">Icon.ToBitmap은 PNG 프레임이 있는 아이콘을 Bitmap 개체로 성공적으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b5d2e-101">Icon.ToBitmap successfully converts icons with PNG frames into Bitmap objects</span></span>

#### <a name="details"></a><span data-ttu-id="b5d2e-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="b5d2e-102">Details</span></span>

<span data-ttu-id="b5d2e-103">.NET Framework 4.6을 대상으로 하는 앱부터는 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 메서드가 PNG 프레임이 있는 아이콘을 Bitmap 개체로 올바르게 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b5d2e-103">Starting with the apps that target the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into Bitmap objects.</span></span><p/><span data-ttu-id="b5d2e-104">.NET Framework 4.5.2 및 이전 버전을 대상으로 하는 앱에서는 Icon 개체에 PNG 프레임이 있는 경우 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 메서드가 <xref:System.ArgumentOutOfRangeException> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b5d2e-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the  <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the Icon object has PNG frames.</span></span><p/><span data-ttu-id="b5d2e-105">이 변경은 Icon 개체에 PNG 프레임이 있을 때 throw되는 <xref:System.ArgumentOutOfRangeException>에 대해 특수 처리를 구현하고 .NET Framework 4.6을 대상으로 다시 컴파일되는 앱에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5d2e-105">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an Icon object has PNG frames.</span></span> <span data-ttu-id="b5d2e-106">.NET Framework 4.6에서 실행되는 경우 변환이 성공하고 <xref:System.ArgumentOutOfRangeException> 이 더 이상 throw되지 않습니다. 따라서 예외 처리기가 더 이상 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5d2e-106">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b5d2e-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="b5d2e-107">Suggestion</span></span>

<span data-ttu-id="b5d2e-108">이 동작이 필요 없는 경우 app.config 파일의 `<runtime>` 섹션에 다음 요소를 추가하여 이전 동작을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5d2e-108">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the `<runtime>` section of your app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>

<span data-ttu-id="b5d2e-109">App.config 파일에 이미 `AppContextSwitchOverrides` 요소가 포함되어 있는 경우 새 값은 다음과 같이 값 특성과 병합되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5d2e-109">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the value attribute like this:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="b5d2e-110">이름</span><span class="sxs-lookup"><span data-stu-id="b5d2e-110">Name</span></span>    | <span data-ttu-id="b5d2e-111">값</span><span class="sxs-lookup"><span data-stu-id="b5d2e-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b5d2e-112">Scope</span><span class="sxs-lookup"><span data-stu-id="b5d2e-112">Scope</span></span>   | <span data-ttu-id="b5d2e-113">부</span><span class="sxs-lookup"><span data-stu-id="b5d2e-113">Minor</span></span>       |
| <span data-ttu-id="b5d2e-114">버전</span><span class="sxs-lookup"><span data-stu-id="b5d2e-114">Version</span></span> | <span data-ttu-id="b5d2e-115">4.6</span><span class="sxs-lookup"><span data-stu-id="b5d2e-115">4.6</span></span>         |
| <span data-ttu-id="b5d2e-116">형식</span><span class="sxs-lookup"><span data-stu-id="b5d2e-116">Type</span></span>    | <span data-ttu-id="b5d2e-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="b5d2e-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b5d2e-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b5d2e-118">Affected APIs</span></span>

- <xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType>
