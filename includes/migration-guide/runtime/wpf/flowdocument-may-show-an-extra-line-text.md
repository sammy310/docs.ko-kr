---
ms.openlocfilehash: 0470cefc05fb5da6a6195ee0a96f04feef01fd10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620432"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="0503c-101">FlowDocument는 텍스트의 추가 줄을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0503c-101">FlowDocument may show an extra line of text</span></span>

#### <a name="details"></a><span data-ttu-id="0503c-102">설명</span><span class="sxs-lookup"><span data-stu-id="0503c-102">Details</span></span>

<span data-ttu-id="0503c-103">일부 경우에는 <xref:System.Windows.Documents.FlowDocument> 요소가 .NET Framework 4.0에서 실행 중에 표시되는 방법과 비교하여 .NET Framework 4.5에서 실행 중에 텍스트의 추가 줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0503c-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="0503c-104">변경 사항으로 인해 텍스트가 제대로 표시되지 않거나 불명확하게 표시되는 경우는 없지만 이전에 <xref:System.Windows.Documents.FlowDocument>의 보기에서 누락되었던 텍스트가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0503c-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0503c-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="0503c-105">Suggestion</span></span>

<span data-ttu-id="0503c-106">일부 경우에는 디스플레이 요소의 PageHeight 속성을 하나씩 줄이면 이전에 표시된 줄 수를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0503c-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>

| <span data-ttu-id="0503c-107">이름</span><span class="sxs-lookup"><span data-stu-id="0503c-107">Name</span></span>    | <span data-ttu-id="0503c-108">값</span><span class="sxs-lookup"><span data-stu-id="0503c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0503c-109">Scope</span><span class="sxs-lookup"><span data-stu-id="0503c-109">Scope</span></span>   |<span data-ttu-id="0503c-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0503c-110">Edge</span></span>|
|<span data-ttu-id="0503c-111">버전</span><span class="sxs-lookup"><span data-stu-id="0503c-111">Version</span></span>|<span data-ttu-id="0503c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="0503c-112">4.5</span></span>|
|<span data-ttu-id="0503c-113">형식</span><span class="sxs-lookup"><span data-stu-id="0503c-113">Type</span></span>|<span data-ttu-id="0503c-114">런타임</span><span class="sxs-lookup"><span data-stu-id="0503c-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0503c-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0503c-115">Affected APIs</span></span>

-<xref:System.Windows.Documents.FlowDocument.%23ctor></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor></li></ul>|
