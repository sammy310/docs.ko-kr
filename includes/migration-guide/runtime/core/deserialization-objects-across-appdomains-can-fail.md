---
ms.openlocfilehash: 3f82a4daac3b5d8981532f0c82e9a76f13c68b6e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497709"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="d23a8-101">앱 도메인 간의 개체 역직렬화가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d23a8-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="d23a8-102">설명</span><span class="sxs-lookup"><span data-stu-id="d23a8-102">Details</span></span>

<span data-ttu-id="d23a8-103">경우에 따라, 애플리케이션 기반이 다른 둘 이상의 앱 도메인이 앱에서 사용되는 경우 앱 도메인 간에 논리 호출 컨텍스트의 개체를 역직렬화하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d23a8-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d23a8-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d23a8-104">Suggestion</span></span>

<span data-ttu-id="d23a8-105">[완화: 앱 도메인 간 개체의 deserialization](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d23a8-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="d23a8-106">이름</span><span class="sxs-lookup"><span data-stu-id="d23a8-106">Name</span></span>    | <span data-ttu-id="d23a8-107">값</span><span class="sxs-lookup"><span data-stu-id="d23a8-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d23a8-108">Scope</span><span class="sxs-lookup"><span data-stu-id="d23a8-108">Scope</span></span>   |<span data-ttu-id="d23a8-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d23a8-109">Edge</span></span>|
|<span data-ttu-id="d23a8-110">버전</span><span class="sxs-lookup"><span data-stu-id="d23a8-110">Version</span></span>|<span data-ttu-id="d23a8-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d23a8-111">4.5.1</span></span>|
|<span data-ttu-id="d23a8-112">형식</span><span class="sxs-lookup"><span data-stu-id="d23a8-112">Type</span></span>|<span data-ttu-id="d23a8-113">런타임</span><span class="sxs-lookup"><span data-stu-id="d23a8-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d23a8-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d23a8-114">Affected APIs</span></span>

<span data-ttu-id="d23a8-115">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d23a8-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
