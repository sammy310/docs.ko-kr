---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620339"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="914f3-101">MEF 카탈로그는 IEnumerable을 구현하므로 더 이상 직렬 변환기를 만드는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="914f3-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="914f3-102">설명</span><span class="sxs-lookup"><span data-stu-id="914f3-102">Details</span></span>

<span data-ttu-id="914f3-103">.NET Framework 4.5부터 MEF 카탈로그는 IEnumerable을 구현하므로 더 이상 직렬 변환기(<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 개체)를 만드는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="914f3-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="914f3-104">MEF 카탈로그를 serialize하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="914f3-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="914f3-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="914f3-105">Suggestion</span></span>

<span data-ttu-id="914f3-106">직렬 변환기를 만드는데 MEF를 더 이상 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="914f3-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="914f3-107">이름</span><span class="sxs-lookup"><span data-stu-id="914f3-107">Name</span></span>    | <span data-ttu-id="914f3-108">값</span><span class="sxs-lookup"><span data-stu-id="914f3-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="914f3-109">Scope</span><span class="sxs-lookup"><span data-stu-id="914f3-109">Scope</span></span>   |<span data-ttu-id="914f3-110">주요함</span><span class="sxs-lookup"><span data-stu-id="914f3-110">Major</span></span>|
|<span data-ttu-id="914f3-111">버전</span><span class="sxs-lookup"><span data-stu-id="914f3-111">Version</span></span>|<span data-ttu-id="914f3-112">4.5</span><span class="sxs-lookup"><span data-stu-id="914f3-112">4.5</span></span>|
|<span data-ttu-id="914f3-113">형식</span><span class="sxs-lookup"><span data-stu-id="914f3-113">Type</span></span>|<span data-ttu-id="914f3-114">런타임</span><span class="sxs-lookup"><span data-stu-id="914f3-114">Runtime</span></span>|
