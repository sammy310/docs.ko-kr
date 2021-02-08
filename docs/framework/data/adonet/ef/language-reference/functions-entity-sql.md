---
description: '다음에 대 한 자세한 정보: 함수 (Entity SQL)'
title: 함수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: c557d264587a1d40194971d756e6b5c75a3856aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786305"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="e3442-103">함수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e3442-103">Functions (Entity SQL)</span></span>

<span data-ttu-id="e3442-104">Entity SQL에서는 사용자 정의 함수, 정식 함수 및 공급자 특정 함수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e3442-104">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="e3442-105">사용자 정의 함수는 개념적 모델에 지정되거나 쿼리에 인라인으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3442-105">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="e3442-106">자세한 내용은 [사용자 정의 함수](user-defined-functions-entity-sql.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3442-106">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="e3442-107">정식 함수는 Entity Framework에 미리 정의되어 있으며 데이터 공급자의 지원이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e3442-107">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="e3442-108">공급자가 지원하지 않는 함수를 사용자가 호출하는 경우 Entity SQL 명령은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e3442-108">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="e3442-109">따라서, 일반적으로 정식 함수는 공급자 특정 네임스페이스에 들어 있는 저장소 특정 함수의 경우에 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3442-109">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="e3442-110">자세한 내용은 [정식 함수](canonical-functions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3442-110">For more information, see [Canonical Functions](canonical-functions.md).</span></span>  
  
 <span data-ttu-id="e3442-111">Microsoft SQL 클라이언트 관리 공급자에서는 공급자 특정 함수 집합이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3442-111">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="e3442-112">자세한 내용은 [Entity Framework 함수에 대 한 SqlClient](../sqlclient-for-ef-functions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3442-112">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3442-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e3442-113">In This Section</span></span>  

 [<span data-ttu-id="e3442-114">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="e3442-114">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="e3442-115">함수 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="e3442-115">Function Overload Resolution</span></span>](function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="e3442-116">집계 함수</span><span class="sxs-lookup"><span data-stu-id="e3442-116">Aggregate Functions</span></span>](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="e3442-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3442-117">See also</span></span>

- [<span data-ttu-id="e3442-118">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="e3442-118">Entity SQL Overview</span></span>](entity-sql-overview.md)
