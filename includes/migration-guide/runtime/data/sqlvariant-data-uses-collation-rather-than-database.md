---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235534"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a><span data-ttu-id="a404e-101">Sql_variant 데이터는 데이터베이스 데이터 정렬 대신 sql_variant 데이터 정렬을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a404e-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a404e-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a404e-102">Details</span></span>|<span data-ttu-id="a404e-103"><code>sql_variant</code> 데이터는 데이터베이스 데이터 정렬 대신 <code>sql_variant</code> 데이터 정렬을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a404e-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>|
|<span data-ttu-id="a404e-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a404e-104">Suggestion</span></span>|<span data-ttu-id="a404e-105">이러한 변경을 통해 데이터베이스 데이터 정렬이 <code>sql_variant</code> 데이터 정렬과 다른 경우 데이터 손상 가능성을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="a404e-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="a404e-106">손상된 데이터를 사용하는 애플리케이션은 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a404e-106">Applications that rely on the corrupted data may experience failure.</span></span>|
|<span data-ttu-id="a404e-107">범위</span><span class="sxs-lookup"><span data-stu-id="a404e-107">Scope</span></span>|<span data-ttu-id="a404e-108">투명</span><span class="sxs-lookup"><span data-stu-id="a404e-108">Transparent</span></span>|
|<span data-ttu-id="a404e-109">버전</span><span class="sxs-lookup"><span data-stu-id="a404e-109">Version</span></span>|<span data-ttu-id="a404e-110">4.5</span><span class="sxs-lookup"><span data-stu-id="a404e-110">4.5</span></span>|
|<span data-ttu-id="a404e-111">형식</span><span class="sxs-lookup"><span data-stu-id="a404e-111">Type</span></span>|<span data-ttu-id="a404e-112">런타임</span><span class="sxs-lookup"><span data-stu-id="a404e-112">Runtime</span></span>|
