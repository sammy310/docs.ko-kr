---
title: Entity Framework용 SqlClient 기능
ms.date: 03/30/2017
ms.assetid: 71a3613c-b94e-494c-8ad8-90cf86ae0b87
ms.openlocfilehash: f8e8ce44c1516171926ec71227e316586d02cc14
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156656"
---
# <a name="sqlclient-for-entity-framework-functions"></a><span data-ttu-id="9c60d-102">Entity Framework용 SqlClient 기능</span><span class="sxs-lookup"><span data-stu-id="9c60d-102">SqlClient for Entity Framework Functions</span></span>

<span data-ttu-id="9c60d-103">Entity Framework용 .NET Framework Data Provider for SQL Server(SqlClient)에서는 수치 및 집계 계산을 수행할 함수 집합과 `System.DateTime` 및 `string` 연산을 수행할 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9c60d-103">The .NET Framework Data Provider for SQL Server (SqlClient) for the Entity Framework provides a set of functions to perform mathematical and aggregation calculations, as well as functions to perform `System.DateTime` and `string` operations.</span></span> <span data-ttu-id="9c60d-104">이러한 함수는 `SQLServer` 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c60d-104">These functions are in the `SQLServer` namespace.</span></span>  
  
 <span data-ttu-id="9c60d-105">모든 공급자에서 작동 해야 하는 함수 목록은 [정식 함수](./language-reference/canonical-functions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c60d-105">For a list of functions that should work with any provider, see [Canonical Functions](./language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="9c60d-106">정식 함수가 SQL Server 함수에 매핑되는 방법에 대 한 자세한 내용은 [SQL Server 함수 매핑의 개념적 모델 정식](conceptual-model-canonical-to-sql-server-functions-mapping.md)항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c60d-106">For information about how canonical functions map to SQL Server functions, see [Conceptual Model Canonical to SQL Server Functions Mapping](conceptual-model-canonical-to-sql-server-functions-mapping.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9c60d-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9c60d-107">In This Section</span></span>  

 [<span data-ttu-id="9c60d-108">개념적 모델 정식 함수와 SQL Server 함수 매핑</span><span class="sxs-lookup"><span data-stu-id="9c60d-108">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](conceptual-model-canonical-to-sql-server-functions-mapping.md)  
  
 [<span data-ttu-id="9c60d-109">집계 함수</span><span class="sxs-lookup"><span data-stu-id="9c60d-109">Aggregate Functions</span></span>](aggregate-functions-sqlclient-for-entity-framework.md)  
  
 [<span data-ttu-id="9c60d-110">날짜 및 시간 함수</span><span class="sxs-lookup"><span data-stu-id="9c60d-110">Date and Time Functions</span></span>](date-and-time-functions.md)  
  
 [<span data-ttu-id="9c60d-111">수치 연산 함수</span><span class="sxs-lookup"><span data-stu-id="9c60d-111">Mathematical Functions</span></span>](mathematical-functions.md)  
  
 [<span data-ttu-id="9c60d-112">문자열 함수</span><span class="sxs-lookup"><span data-stu-id="9c60d-112">String Functions</span></span>](string-functions.md)  
  
 [<span data-ttu-id="9c60d-113">시스템 함수</span><span class="sxs-lookup"><span data-stu-id="9c60d-113">System Functions</span></span>](system-functions.md)  
  
## <a name="see-also"></a><span data-ttu-id="9c60d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c60d-114">See also</span></span>

- [<span data-ttu-id="9c60d-115">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="9c60d-115">Entity SQL Reference</span></span>](./language-reference/entity-sql-reference.md)
- [<span data-ttu-id="9c60d-116">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="9c60d-116">Entity SQL Overview</span></span>](./language-reference/entity-sql-overview.md)
