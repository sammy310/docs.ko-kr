---
ms.openlocfilehash: ef0381dc2ce4373b2a62e8ebefa44152059ca332
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234698"
---
### <a name="xml-schema-validation-is-stricter"></a><span data-ttu-id="01150-101">XML 스키마 유효성 검사가 더 엄격합니다.</span><span class="sxs-lookup"><span data-stu-id="01150-101">XML schema validation is stricter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="01150-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="01150-102">Details</span></span>|<span data-ttu-id="01150-103">.NET Framework 4.5에서는 XML 스키마 유효성 검사가 더 엄격합니다.</span><span class="sxs-lookup"><span data-stu-id="01150-103">In the .NET Framework 4.5, XML schema validation is more strict.</span></span> <span data-ttu-id="01150-104">mailto 프로토콜과 같이 URI의 유효성을 검사하기 위해 xsd:anyURI을 사용하는 경우 URI에 공백이 있으면 유효성 검사에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="01150-104">If you use xsd:anyURI to validate a URI such as a mailto protocol, validation fails if there are spaces in the URI.</span></span> <span data-ttu-id="01150-105">이전 버전의 .NET Framework에서는 유효성 검사에 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="01150-105">In previous versions of the .NET Framework, validation succeeded.</span></span> <span data-ttu-id="01150-106">해당 변경 내용은 .NET Framework 4.5를 대상으로 하는 애플리케이션에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01150-106">The change affects only applications that target the .NET Framework 4.5.</span></span>|
|<span data-ttu-id="01150-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="01150-107">Suggestion</span></span>|<span data-ttu-id="01150-108">완화된 .NET Framework 4.0 유효성 검사가 필요한 경우 유효성 검사 애플리케이션은 .NET Framework 4.0 버전을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01150-108">If looser .NET Framework 4.0 validation is needed, the validating application can target version 4.0 of the .NET Framework.</span></span> <span data-ttu-id="01150-109">하지만 .NET Framework 4.5로 대상을 변경할 때는 anyURI 데이터 형식을 사용하는 잘못된 URI(공백 포함)가 특성 값으로 요구되지 않도록 코드 검토를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01150-109">When retargeting to .NET Framework 4.5, however, code review should be done to be sure that invalid URIs (with spaces) are not expected as attribute values with the anyURI data type.</span></span>|
|<span data-ttu-id="01150-110">범위</span><span class="sxs-lookup"><span data-stu-id="01150-110">Scope</span></span>|<span data-ttu-id="01150-111">부</span><span class="sxs-lookup"><span data-stu-id="01150-111">Minor</span></span>|
|<span data-ttu-id="01150-112">버전</span><span class="sxs-lookup"><span data-stu-id="01150-112">Version</span></span>|<span data-ttu-id="01150-113">4.5</span><span class="sxs-lookup"><span data-stu-id="01150-113">4.5</span></span>|
|<span data-ttu-id="01150-114">형식</span><span class="sxs-lookup"><span data-stu-id="01150-114">Type</span></span>|<span data-ttu-id="01150-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="01150-115">Retargeting</span></span>|
