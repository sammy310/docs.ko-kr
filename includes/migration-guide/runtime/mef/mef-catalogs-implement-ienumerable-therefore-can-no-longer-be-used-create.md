---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235575"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="81081-101">MEF 카탈로그는 IEnumerable을 구현하므로 더 이상 직렬 변환기를 만드는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81081-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

|   |   |
|---|---|
|<span data-ttu-id="81081-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="81081-102">Details</span></span>|<span data-ttu-id="81081-103">.NET Framework 4.5부터 MEF 카탈로그는 IEnumerable을 구현하므로 더 이상 직렬 변환기(<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> 개체)를 만드는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81081-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> object).</span></span> <span data-ttu-id="81081-104">MEF 카탈로그를 serialize하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="81081-104">Trying to serialize a MEF catalog throws an exception.</span></span>|
|<span data-ttu-id="81081-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="81081-105">Suggestion</span></span>|<span data-ttu-id="81081-106">직렬 변환기를 만드는데 MEF를 더 이상 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="81081-106">Can no longer use MEF to create a serializer</span></span>|
|<span data-ttu-id="81081-107">범위</span><span class="sxs-lookup"><span data-stu-id="81081-107">Scope</span></span>|<span data-ttu-id="81081-108">주요함</span><span class="sxs-lookup"><span data-stu-id="81081-108">Major</span></span>|
|<span data-ttu-id="81081-109">버전</span><span class="sxs-lookup"><span data-stu-id="81081-109">Version</span></span>|<span data-ttu-id="81081-110">4.5</span><span class="sxs-lookup"><span data-stu-id="81081-110">4.5</span></span>|
|<span data-ttu-id="81081-111">형식</span><span class="sxs-lookup"><span data-stu-id="81081-111">Type</span></span>|<span data-ttu-id="81081-112">런타임</span><span class="sxs-lookup"><span data-stu-id="81081-112">Runtime</span></span>|
