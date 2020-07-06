---
ms.openlocfilehash: 4a22d78f2308aab544d7a7d2e4d05ddc1ad5457d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617236"
---
### <a name="xml-schema-validation-is-stricter"></a><span data-ttu-id="861b5-101">XML 스키마 유효성 검사가 더 엄격합니다.</span><span class="sxs-lookup"><span data-stu-id="861b5-101">XML schema validation is stricter</span></span>

#### <a name="details"></a><span data-ttu-id="861b5-102">설명</span><span class="sxs-lookup"><span data-stu-id="861b5-102">Details</span></span>

<span data-ttu-id="861b5-103">.NET Framework 4.5에서는 XML 스키마 유효성 검사가 더 엄격합니다.</span><span class="sxs-lookup"><span data-stu-id="861b5-103">In the .NET Framework 4.5, XML schema validation is more strict.</span></span> <span data-ttu-id="861b5-104">mailto 프로토콜과 같이 URI의 유효성을 검사하기 위해 xsd:anyURI을 사용하는 경우 URI에 공백이 있으면 유효성 검사에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="861b5-104">If you use xsd:anyURI to validate a URI such as a mailto protocol, validation fails if there are spaces in the URI.</span></span> <span data-ttu-id="861b5-105">이전 버전의 .NET Framework에서는 유효성 검사에 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="861b5-105">In previous versions of the .NET Framework, validation succeeded.</span></span> <span data-ttu-id="861b5-106">해당 변경 내용은 .NET Framework 4.5를 대상으로 하는 애플리케이션에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="861b5-106">The change affects only applications that target the .NET Framework 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="861b5-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="861b5-107">Suggestion</span></span>

<span data-ttu-id="861b5-108">완화된 .NET Framework 4.0 유효성 검사가 필요한 경우 유효성 검사 애플리케이션은 .NET Framework 4.0 버전을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="861b5-108">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.0 of the .NET Framework.</span></span> <span data-ttu-id="861b5-109">하지만 .NET Framework 4.5로 대상을 변경할 때는 anyURI 데이터 형식을 사용하는 잘못된 URI(공백 포함)가 특성 값으로 요구되지 않도록 코드 검토를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="861b5-109">When retargeting to .NET Framework 4.5, however, code review should be done to be sure that invalid URIs (with spaces) are not expected as attribute values with the anyURI data type.</span></span>

| <span data-ttu-id="861b5-110">이름</span><span class="sxs-lookup"><span data-stu-id="861b5-110">Name</span></span>    | <span data-ttu-id="861b5-111">값</span><span class="sxs-lookup"><span data-stu-id="861b5-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="861b5-112">Scope</span><span class="sxs-lookup"><span data-stu-id="861b5-112">Scope</span></span>   | <span data-ttu-id="861b5-113">부</span><span class="sxs-lookup"><span data-stu-id="861b5-113">Minor</span></span>       |
| <span data-ttu-id="861b5-114">버전</span><span class="sxs-lookup"><span data-stu-id="861b5-114">Version</span></span> | <span data-ttu-id="861b5-115">4.5</span><span class="sxs-lookup"><span data-stu-id="861b5-115">4.5</span></span>         |
| <span data-ttu-id="861b5-116">형식</span><span class="sxs-lookup"><span data-stu-id="861b5-116">Type</span></span>    | <span data-ttu-id="861b5-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="861b5-117">Retargeting</span></span> |
