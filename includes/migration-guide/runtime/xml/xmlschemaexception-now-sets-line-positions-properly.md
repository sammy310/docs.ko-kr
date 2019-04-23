---
ms.openlocfilehash: a5b3e325c13d2f56532ebc6ebb5c259d565a4952
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804521"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="a35c8-101">XmlSchemaException이 줄 위치를 제대로 설정</span><span class="sxs-lookup"><span data-stu-id="a35c8-101">XmlSchemaException now sets line positions properly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a35c8-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a35c8-102">Details</span></span>|<span data-ttu-id="a35c8-103"><xref:System.Xml.Linq.LoadOptions.SetLineInfo> 값을 Load 메서드에 전달하고 유효성 검사 오류가 발생한 경우 <xref:System.Xml.Schema.XmlSchemaException.LineNumber> 및 <xref:System.Xml.Schema.XmlSchemaException.LinePosition> 속성은 이제 줄 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a35c8-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>|
|<span data-ttu-id="a35c8-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a35c8-104">Suggestion</span></span>|<span data-ttu-id="a35c8-105">XML을 로드하는 동안 SetLineInfo를 사용할 때 이러한 속성이 이제 제대로 설정되므로 <xref:System.Xml.Schema.XmlSchemaException.LineNumber> 및 <xref:System.Xml.Schema.XmlSchemaException.LinePosition>이 설정되지 않는다고 가정하는 예외 처리 코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a35c8-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>|
|<span data-ttu-id="a35c8-106">범위</span><span class="sxs-lookup"><span data-stu-id="a35c8-106">Scope</span></span>|<span data-ttu-id="a35c8-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a35c8-107">Edge</span></span>|
|<span data-ttu-id="a35c8-108">버전</span><span class="sxs-lookup"><span data-stu-id="a35c8-108">Version</span></span>|<span data-ttu-id="a35c8-109">4.5</span><span class="sxs-lookup"><span data-stu-id="a35c8-109">4.5</span></span>|
|<span data-ttu-id="a35c8-110">형식</span><span class="sxs-lookup"><span data-stu-id="a35c8-110">Type</span></span>|<span data-ttu-id="a35c8-111">런타임</span><span class="sxs-lookup"><span data-stu-id="a35c8-111">Runtime</span></span>|
|<span data-ttu-id="a35c8-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a35c8-112">Affected APIs</span></span>|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
