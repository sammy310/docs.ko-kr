---
title: -- (주석)(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 1ea1929b0e6f965f71fbb015ee6795affb3bce7c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251213"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="6cfbd-102">-- (주석)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6cfbd-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="6cfbd-103">쿼리에는 주석이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cfbd-103">queries can contain comments.</span></span> <span data-ttu-id="6cfbd-104">주석 줄은 대시 두 개(`--`)로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cfbd-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cfbd-105">구문</span><span class="sxs-lookup"><span data-stu-id="6cfbd-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="6cfbd-106">인수</span><span class="sxs-lookup"><span data-stu-id="6cfbd-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="6cfbd-107">주석의 텍스트를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6cfbd-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cfbd-108">예제</span><span class="sxs-lookup"><span data-stu-id="6cfbd-108">Example</span></span>  
 <span data-ttu-id="6cfbd-109">다음 Entity SQL 쿼리에서는 주석을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cfbd-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="6cfbd-110">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfbd-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6cfbd-111">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="6cfbd-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6cfbd-112">[방법: StructuralType 결과](../how-to-execute-a-query-that-returns-structuraltype-results.md)를 반환 하는 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfbd-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6cfbd-113">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfbd-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="6cfbd-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6cfbd-114">See also</span></span>

- [<span data-ttu-id="6cfbd-115">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="6cfbd-115">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="6cfbd-116">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="6cfbd-116">Entity SQL Reference</span></span>](entity-sql-reference.md)
