---
description: '자세한 정보: 지원 되지 않는 식'
title: 지원되지 않는 식(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: ceb57dc78f9685a79de987d15f7fd57a583b75a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673299"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="29240-103">지원 되지 않는 식</span><span class="sxs-lookup"><span data-stu-id="29240-103">Unsupported expressions</span></span>

<span data-ttu-id="29240-104">이 항목에서는에서 지원 되지 않는 Transact-sql 식에 대해 설명 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="29240-104">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="29240-105">자세한 내용은 [Transact-sql과 Entity SQL 다른 방법](how-entity-sql-differs-from-transact-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29240-105">For more information, see [How Entity SQL Differs from Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="29240-106">정량화 된 조건자</span><span class="sxs-lookup"><span data-stu-id="29240-106">Quantified predicates</span></span>

<span data-ttu-id="29240-107">Transact-sql은 다음 형식의 구문을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="29240-107">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="29240-108">이와 달리 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 이러한 생성이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29240-108">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="29240-109">대신 이와 동등한 식을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 다음과 같이 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29240-109">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="29240-110">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="29240-110">\* operator</span></span>

<span data-ttu-id="29240-111">Transact-sql은 SELECT 절에서 \* 연산자를 사용 하 여 모든 열이 투영 되어야 함을 나타낼 수 있습니다. 이는에서 지원 되지 않습니다 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29240-111">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="29240-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29240-112">See also</span></span>

- [<span data-ttu-id="29240-113">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="29240-113">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="29240-114">Entity SQL과 Transact-SQL의 차이점</span><span class="sxs-lookup"><span data-stu-id="29240-114">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)
