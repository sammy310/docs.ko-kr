---
ms.openlocfilehash: 6f22d6211ec9238fd1c7786643ca95db02bfca64
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496794"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="d6056-101">MEF 카탈로그는 IEnumerable을 구현하므로 더 이상 직렬 변환기를 만드는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6056-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="d6056-102">설명</span><span class="sxs-lookup"><span data-stu-id="d6056-102">Details</span></span>

<span data-ttu-id="d6056-103">.NET Framework 4.5부터 MEF 카탈로그는 IEnumerable을 구현하므로 더 이상 직렬 변환기(<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 개체)를 만드는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6056-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="d6056-104">MEF 카탈로그를 serialize하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6056-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d6056-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d6056-105">Suggestion</span></span>

<span data-ttu-id="d6056-106">직렬 변환기를 만드는데 MEF를 더 이상 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d6056-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="d6056-107">이름</span><span class="sxs-lookup"><span data-stu-id="d6056-107">Name</span></span>    | <span data-ttu-id="d6056-108">값</span><span class="sxs-lookup"><span data-stu-id="d6056-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d6056-109">Scope</span><span class="sxs-lookup"><span data-stu-id="d6056-109">Scope</span></span>   |<span data-ttu-id="d6056-110">주요함</span><span class="sxs-lookup"><span data-stu-id="d6056-110">Major</span></span>|
|<span data-ttu-id="d6056-111">버전</span><span class="sxs-lookup"><span data-stu-id="d6056-111">Version</span></span>|<span data-ttu-id="d6056-112">4.5</span><span class="sxs-lookup"><span data-stu-id="d6056-112">4.5</span></span>|
|<span data-ttu-id="d6056-113">형식</span><span class="sxs-lookup"><span data-stu-id="d6056-113">Type</span></span>|<span data-ttu-id="d6056-114">런타임</span><span class="sxs-lookup"><span data-stu-id="d6056-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d6056-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d6056-115">Affected APIs</span></span>

<span data-ttu-id="d6056-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6056-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
