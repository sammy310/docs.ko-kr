---
ms.openlocfilehash: c3e39e49747be709977d7fba3c39b59f5575c40d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620504"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="19b4d-101">XmlSchemaException이 줄 위치를 제대로 설정</span><span class="sxs-lookup"><span data-stu-id="19b4d-101">XmlSchemaException now sets line positions properly</span></span>

#### <a name="details"></a><span data-ttu-id="19b4d-102">설명</span><span class="sxs-lookup"><span data-stu-id="19b4d-102">Details</span></span>

<span data-ttu-id="19b4d-103"><xref:System.Xml.Linq.LoadOptions.SetLineInfo> 값을 Load 메서드에 전달하고 유효성 검사 오류가 발생한 경우 <xref:System.Xml.Schema.XmlSchemaException.LineNumber> 및 <xref:System.Xml.Schema.XmlSchemaException.LinePosition> 속성은 이제 줄 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="19b4d-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="19b4d-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="19b4d-104">Suggestion</span></span>

<span data-ttu-id="19b4d-105">XML을 로드하는 동안 SetLineInfo를 사용할 때 이러한 속성이 이제 제대로 설정되므로 <xref:System.Xml.Schema.XmlSchemaException.LineNumber> 및 <xref:System.Xml.Schema.XmlSchemaException.LinePosition>이 설정되지 않는다고 가정하는 예외 처리 코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19b4d-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>

| <span data-ttu-id="19b4d-106">이름</span><span class="sxs-lookup"><span data-stu-id="19b4d-106">Name</span></span>    | <span data-ttu-id="19b4d-107">값</span><span class="sxs-lookup"><span data-stu-id="19b4d-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="19b4d-108">Scope</span><span class="sxs-lookup"><span data-stu-id="19b4d-108">Scope</span></span>   |<span data-ttu-id="19b4d-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="19b4d-109">Edge</span></span>|
|<span data-ttu-id="19b4d-110">버전</span><span class="sxs-lookup"><span data-stu-id="19b4d-110">Version</span></span>|<span data-ttu-id="19b4d-111">4.5</span><span class="sxs-lookup"><span data-stu-id="19b4d-111">4.5</span></span>|
|<span data-ttu-id="19b4d-112">형식</span><span class="sxs-lookup"><span data-stu-id="19b4d-112">Type</span></span>|<span data-ttu-id="19b4d-113">런타임</span><span class="sxs-lookup"><span data-stu-id="19b4d-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="19b4d-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="19b4d-114">Affected APIs</span></span>

-<xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
