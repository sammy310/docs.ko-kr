---
ms.openlocfilehash: d9e1624bbeb91db63bc284b8eb52643938eb42e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497761"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a><span data-ttu-id="13c06-101">.NET Framework 4.5부터 GlyphRun.ComputeInkBoundingBox() 및 FormattedText.Extent는 다른 값 반환</span><span class="sxs-lookup"><span data-stu-id="13c06-101">GlyphRun.ComputeInkBoundingBox() and FormattedText.Extent return different values beginning in .NET Framework 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="13c06-102">설명</span><span class="sxs-lookup"><span data-stu-id="13c06-102">Details</span></span>

<span data-ttu-id="13c06-103">.NET Framework 4.0의 일부 경우에서 포함된 문자 모양에 대해 상자가 너무 작은 문제를 해결하기 위해 .NET Framework 4.5에서 <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> 및 <xref:System.Windows.Media.FormattedText.Extent>를 개선하였습니다.</span><span class="sxs-lookup"><span data-stu-id="13c06-103">Improvements were made to <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> and <xref:System.Windows.Media.FormattedText.Extent> in the .NET Framework 4.5 to address issues where the boxes were too small for the contained glyphs in some cases in the .NET Framework 4.0.</span></span> <span data-ttu-id="13c06-104">결과적으로 .NET Framework 4.5부터 일부 경계 상자가 커져 UI 레이아웃에 미묘한 차이가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="13c06-104">As a result of this, some bounding boxes will be larger beginning in the .NET Framework 4.5, resulting in subtle differences in UI layout.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="13c06-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="13c06-105">Suggestion</span></span>

<span data-ttu-id="13c06-106">일부 문자 모양 경계 상자의 크기가 커졌습니다.</span><span class="sxs-lookup"><span data-stu-id="13c06-106">Be aware that some glyph bounding box sizes have increased.</span></span> <span data-ttu-id="13c06-107">이러한 변경은 일반적으로 프레젠테이션 및 적중 상자 테스트를 향상시키지만 이전 동작(.NET 4.5 전)이 필요할 경우 app.config 파일에 다음의 항목을 추가하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13c06-107">These changes will usually improve presentation and hit box testing, but if the older (pre-.NET 4.5) behavior is desired, it can be opted into by adding the following entry to the app.config file:</span></span><pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="13c06-108">이름</span><span class="sxs-lookup"><span data-stu-id="13c06-108">Name</span></span>    | <span data-ttu-id="13c06-109">값</span><span class="sxs-lookup"><span data-stu-id="13c06-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="13c06-110">Scope</span><span class="sxs-lookup"><span data-stu-id="13c06-110">Scope</span></span>   |<span data-ttu-id="13c06-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="13c06-111">Edge</span></span>|
|<span data-ttu-id="13c06-112">버전</span><span class="sxs-lookup"><span data-stu-id="13c06-112">Version</span></span>|<span data-ttu-id="13c06-113">4.5</span><span class="sxs-lookup"><span data-stu-id="13c06-113">4.5</span></span>|
|<span data-ttu-id="13c06-114">형식</span><span class="sxs-lookup"><span data-stu-id="13c06-114">Type</span></span>|<span data-ttu-id="13c06-115">런타임</span><span class="sxs-lookup"><span data-stu-id="13c06-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="13c06-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="13c06-116">Affected APIs</span></span>

- <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType>
- <xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Media.GlyphRun.ComputeInkBoundingBox`
- `P:System.Windows.Media.FormattedText.Extent`

-->
