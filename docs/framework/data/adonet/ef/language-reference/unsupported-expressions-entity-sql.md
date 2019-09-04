---
title: 지원되지 않는 식(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: 956fe117eb0c59392c3999046bc70deaed268ac6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248777"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="f903a-102">지원 되지 않는 식</span><span class="sxs-lookup"><span data-stu-id="f903a-102">Unsupported expressions</span></span>

<span data-ttu-id="f903a-103">이 항목에서는에서 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]지원 되지 않는 transact-sql 식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f903a-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="f903a-104">자세한 내용은 [Transact-sql과 Entity SQL 다른 방법](how-entity-sql-differs-from-transact-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f903a-104">For more information, see [How Entity SQL Differs from Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="f903a-105">정량화 된 조건자</span><span class="sxs-lookup"><span data-stu-id="f903a-105">Quantified predicates</span></span>

<span data-ttu-id="f903a-106">Transact-sql은 다음 형식의 구문을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f903a-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="f903a-107">이와 달리 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 이러한 생성이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f903a-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="f903a-108">대신 이와 동등한 식을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 다음과 같이 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f903a-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="f903a-109">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="f903a-109">\* operator</span></span>

<span data-ttu-id="f903a-110">Transact-sql은 SELECT 절에서 \* 연산자를 사용 하 여 모든 열이 투영 되어야 함을 나타낼 수 있습니다. 이는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f903a-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="f903a-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="f903a-111">See also</span></span>

- [<span data-ttu-id="f903a-112">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="f903a-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="f903a-113">Entity SQL과 Transact-SQL의 차이점</span><span class="sxs-lookup"><span data-stu-id="f903a-113">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)
