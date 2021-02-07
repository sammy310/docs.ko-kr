---
description: 다음에 대해 자세히 알아보세요.--(주석) (Entity SQL)
title: -- (주석)(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 793649177d9e64bead7b8755f35bdb51f53f4dd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724975"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="f4552-103">-- (주석)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f4552-103">-- (Comment) (Entity SQL)</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="f4552-104">쿼리에는 주석이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4552-104">queries can contain comments.</span></span> <span data-ttu-id="f4552-105">주석 줄은 대시 두 개(`--`)로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4552-105">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4552-106">구문</span><span class="sxs-lookup"><span data-stu-id="f4552-106">Syntax</span></span>  
  
```csharp  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="f4552-107">인수</span><span class="sxs-lookup"><span data-stu-id="f4552-107">Arguments</span></span>  

 `text_of_comment`  
 <span data-ttu-id="f4552-108">주석의 텍스트를 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f4552-108">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4552-109">예제</span><span class="sxs-lookup"><span data-stu-id="f4552-109">Example</span></span>  

 <span data-ttu-id="f4552-110">다음 Entity SQL 쿼리에서는 주석을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4552-110">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="f4552-111">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4552-111">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f4552-112">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="f4552-112">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f4552-113">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f4552-113">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f4552-114">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f4552-114">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="f4552-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4552-115">See also</span></span>

- [<span data-ttu-id="f4552-116">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="f4552-116">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="f4552-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="f4552-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
