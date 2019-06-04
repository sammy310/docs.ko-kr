---
title: 지원되지 않는 식(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: af0e00f470584883b6a65b63f2650c1c359b404c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489863"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="02037-102">지원 되지 않는 식</span><span class="sxs-lookup"><span data-stu-id="02037-102">Unsupported expressions</span></span>

<span data-ttu-id="02037-103">이 항목에서는 TRANSACT-SQL 식에서 지원 되지 않는 설명 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="02037-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="02037-104">자세한 내용은 [Entity SQL 차이점 TRANSACT-SQL에서](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02037-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="02037-105">정량화 된 조건자</span><span class="sxs-lookup"><span data-stu-id="02037-105">Quantified predicates</span></span>

<span data-ttu-id="02037-106">TRANSACT-SQL을 사용 하면 다음 형태의 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02037-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="02037-107">이와 달리 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 이러한 생성이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02037-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="02037-108">대신 이와 동등한 식을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 다음과 같이 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02037-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="02037-109">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="02037-109">\* operator</span></span>

<span data-ttu-id="02037-110">TRANSACT-SQL 사용을 지원 합니다 \*는 모든 열이 프로젝션 되어야 나타내려면 SELECT 절의 연산자. 이는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02037-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="02037-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="02037-111">See also</span></span>

- [<span data-ttu-id="02037-112">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="02037-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="02037-113">Entity SQL과 Transact-SQL의 차이점</span><span class="sxs-lookup"><span data-stu-id="02037-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
