---
ms.openlocfilehash: fb339fb35cdcbba4f1c860fae9c17162c4cff596
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497452"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a><span data-ttu-id="f06da-101">Sql_variant 데이터는 데이터베이스 데이터 정렬 대신 sql_variant 데이터 정렬을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f06da-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

#### <a name="details"></a><span data-ttu-id="f06da-102">설명</span><span class="sxs-lookup"><span data-stu-id="f06da-102">Details</span></span>

<span data-ttu-id="f06da-103"><code>sql_variant</code> 데이터는 데이터베이스 데이터 정렬 대신 <code>sql_variant</code> 데이터 정렬을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f06da-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f06da-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f06da-104">Suggestion</span></span>

<span data-ttu-id="f06da-105">이러한 변경을 통해 데이터베이스 데이터 정렬이 <code>sql_variant</code> 데이터 정렬과 다른 경우 데이터 손상 가능성을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="f06da-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="f06da-106">손상된 데이터를 사용하는 애플리케이션은 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f06da-106">Applications that rely on the corrupted data may experience failure.</span></span>

| <span data-ttu-id="f06da-107">이름</span><span class="sxs-lookup"><span data-stu-id="f06da-107">Name</span></span>    | <span data-ttu-id="f06da-108">값</span><span class="sxs-lookup"><span data-stu-id="f06da-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f06da-109">Scope</span><span class="sxs-lookup"><span data-stu-id="f06da-109">Scope</span></span>   |<span data-ttu-id="f06da-110">투명</span><span class="sxs-lookup"><span data-stu-id="f06da-110">Transparent</span></span>|
|<span data-ttu-id="f06da-111">버전</span><span class="sxs-lookup"><span data-stu-id="f06da-111">Version</span></span>|<span data-ttu-id="f06da-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f06da-112">4.5</span></span>|
|<span data-ttu-id="f06da-113">형식</span><span class="sxs-lookup"><span data-stu-id="f06da-113">Type</span></span>|<span data-ttu-id="f06da-114">런타임</span><span class="sxs-lookup"><span data-stu-id="f06da-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f06da-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f06da-115">Affected APIs</span></span>

<span data-ttu-id="f06da-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f06da-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
