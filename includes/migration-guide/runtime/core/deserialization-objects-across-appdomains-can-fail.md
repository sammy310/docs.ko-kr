---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235463"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="8cddc-101">앱 도메인 간의 개체 역직렬화가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cddc-101">Deserialization of objects across appdomains can fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8cddc-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8cddc-102">Details</span></span>|<span data-ttu-id="8cddc-103">경우에 따라, 애플리케이션 기반이 다른 둘 이상의 앱 도메인이 앱에서 사용되는 경우 앱 도메인 간에 논리 호출 컨텍스트의 개체를 deserialize하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cddc-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>|
|<span data-ttu-id="8cddc-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="8cddc-104">Suggestion</span></span>|<span data-ttu-id="8cddc-105">[완화: 앱 도메인 간 개체의 deserialization](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8cddc-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>|
|<span data-ttu-id="8cddc-106">범위</span><span class="sxs-lookup"><span data-stu-id="8cddc-106">Scope</span></span>|<span data-ttu-id="8cddc-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8cddc-107">Edge</span></span>|
|<span data-ttu-id="8cddc-108">버전</span><span class="sxs-lookup"><span data-stu-id="8cddc-108">Version</span></span>|<span data-ttu-id="8cddc-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="8cddc-109">4.5.1</span></span>|
|<span data-ttu-id="8cddc-110">형식</span><span class="sxs-lookup"><span data-stu-id="8cddc-110">Type</span></span>|<span data-ttu-id="8cddc-111">런타임</span><span class="sxs-lookup"><span data-stu-id="8cddc-111">Runtime</span></span>|
