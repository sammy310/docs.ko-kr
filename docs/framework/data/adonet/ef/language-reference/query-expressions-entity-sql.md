---
title: 쿼리 식(Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: ca6b79b4b3d3326a74780345decf58367596adb0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175605"
---
# <a name="query-expressions-entity-sql"></a><span data-ttu-id="ebdf2-102">쿼리 식(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ebdf2-102">Query Expressions (Entity SQL)</span></span>

<span data-ttu-id="ebdf2-103">쿼리 식은 다양한 쿼리 연산자를 단일 구문에 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdf2-103">A query expression combines many different query operators into a single syntax.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="ebdf2-104">는 [리터럴](literals-entity-sql.md), [매개 변수](parameters-entity-sql.md), [변수](variables-entity-sql.md), 연산자, [함수](functions-entity-sql.md), 집합 연산자 등을 비롯 한 다양 한 종류의 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdf2-104">provides various kinds of expressions, including the following: [literals](literals-entity-sql.md), [parameters](parameters-entity-sql.md), [variables](variables-entity-sql.md), operators, [functions](functions-entity-sql.md), set operators, and so on.</span></span> <span data-ttu-id="ebdf2-105">자세한 내용은 [Entity SQL 참조](entity-sql-reference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebdf2-105">For more information, see [Entity SQL Reference](entity-sql-reference.md).</span></span>  
  
## <a name="clauses"></a><span data-ttu-id="ebdf2-106">절</span><span class="sxs-lookup"><span data-stu-id="ebdf2-106">Clauses</span></span>  

 <span data-ttu-id="ebdf2-107">쿼리 식은 개체 컬렉션에 연속적인 연산을 적용하는 일련의 절로 구성되어 있으며,</span><span class="sxs-lookup"><span data-stu-id="ebdf2-107">A query expression is composed of a series of clauses that apply successive operations to a collection of objects.</span></span> <span data-ttu-id="ebdf2-108">[Select](select-entity-sql.md), [FROM](from-entity-sql.md), [WHERE](where-entity-sql.md), [GROUP by](group-by-entity-sql.md), [HAVING](having-entity-sql.md)및 [ORDER BY](order-by-entity-sql.md)표준의 SQL select 문에 있는 동일한 절을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdf2-108">They are based on the same clauses found in standard a SQL select statement: [SELECT](select-entity-sql.md), [FROM](from-entity-sql.md), [WHERE](where-entity-sql.md), [GROUP BY](group-by-entity-sql.md), [HAVING](having-entity-sql.md), and [ORDER BY](order-by-entity-sql.md).</span></span>  
  
## <a name="scope"></a><span data-ttu-id="ebdf2-109">Scope</span><span class="sxs-lookup"><span data-stu-id="ebdf2-109">Scope</span></span>  

 <span data-ttu-id="ebdf2-110">FROM 절에 정의된 이름이 나타나는 순서대로 왼쪽에서 오른쪽 순으로 FROM 범위에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebdf2-110">Names defined in the FROM clause are introduced into the FROM scope in order of appearance, left to right.</span></span> <span data-ttu-id="ebdf2-111">JOIN 목록에서 식은 목록에서 앞쪽에 정의된 이름을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebdf2-111">In the JOIN list, expressions can refer to names defined earlier in the list.</span></span> <span data-ttu-id="ebdf2-112">FROM 절에서 식별된 요소의 공용 속성은 FROM 범위에 추가되지 않으며 항상 정규화된 별칭 이름을 통해 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebdf2-112">Public properties of elements identified in the FROM clause are not added to the FROM scope: They must be always referenced through the alias-qualified name.</span></span> <span data-ttu-id="ebdf2-113">일반적으로 select 식의 모든 부분은 FROM 범위 내에 있는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebdf2-113">Normally, all parts of the select expression are considered within the FROM scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebdf2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebdf2-114">See also</span></span>

- [<span data-ttu-id="ebdf2-115">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="ebdf2-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
