---
description: '자세한 정보: 조인 및 외적 쿼리 작성'
title: '방법: 조인 및 교차곱 쿼리 작성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 1adee3576d7b30d6ec9a9c4e920befcd21dd9e85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739120"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="7bec0-103">방법: 조인 및 교차곱 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="7bec0-103">Formulate Joins and Cross-Product Queries</span></span>

<span data-ttu-id="7bec0-104">다음 예제에서는 여러 테이블의 결과를 결합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-104">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bec0-105">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-105">Example</span></span>  

 <span data-ttu-id="7bec0-106">다음 예제에서는 `From` Visual Basic (c #의 절)에 있는 절에서 외래 키 탐색 `from` 을 사용 하 여 런던의 고객에 대 한 모든 주문을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-106">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="7bec0-107">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-107">Example</span></span>  

 <span data-ttu-id="7bec0-108">다음 예제에서는 `Where` Visual Basic (c #의 절)에 있는 절에서 외래 키 탐색을 사용 하 여 `where` 가 미국에 있는 품절을 필터링 `Products` `Supplier` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-108">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="7bec0-109">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-109">Example</span></span>  

 <span data-ttu-id="7bec0-110">다음 예제에서는 `From` Visual Basic (c #의 절)에 있는 절에서 외래 키 탐색을 사용 하 여 `from` 시애틀의 직원을 필터링 하 고 지역을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-110">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="7bec0-111">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-111">Example</span></span>  

 <span data-ttu-id="7bec0-112">다음 예제에서는 `Select` Visual Basic (c #의 절)에 있는 절에서 외래 키 탐색을 사용 하 여 `select` 한 직원이 다른 직원에 게 보고 하 고 두 직원이 동일한 경우의 직원 쌍을 필터링 합니다 `City` .</span><span class="sxs-lookup"><span data-stu-id="7bec0-112">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="7bec0-113">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-113">Example</span></span>  

 <span data-ttu-id="7bec0-114">다음 Visual Basic 예제에서는 모든 고객과 주문을 찾고 주문이 고객과 일치 하도록 하며 해당 목록의 모든 고객에 대 한 연락처 이름이 제공 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-114">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="7bec0-115">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-115">Example</span></span>  

 <span data-ttu-id="7bec0-116">다음 예제에서는 두 테이블과 두 테이블에서 가져온 프로젝트 결과를 명시적으로 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-116">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="7bec0-117">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-117">Example</span></span>  

 <span data-ttu-id="7bec0-118">다음 예제에서는 세 테이블과 각 테이블에서 가져온 프로젝트 결과를 명시적으로 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-118">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="7bec0-119">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-119">Example</span></span>  

 <span data-ttu-id="7bec0-120">다음 예제에서는 `LEFT OUTER JOIN`를 사용하여 `DefaultIfEmpty()`을 얻는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-120">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="7bec0-121">`DefaultIfEmpty()`에 `Order`가 없는 경우 `Employee` 메서드는 null을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-121">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="7bec0-122">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-122">Example</span></span>  

 <span data-ttu-id="7bec0-123">다음 예제에서는 조인으로 인해 생성된 `let` 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-123">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="7bec0-124">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-124">Example</span></span>  

 <span data-ttu-id="7bec0-125">다음 예제에서는 복합 키와 함께 사용된 `join`을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-125">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="7bec0-126">예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-126">Example</span></span>  

 <span data-ttu-id="7bec0-127">다음 예제에서는 한 면이 nullable이고 다른 면은 nullable이 아닌 `join`을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-127">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="7bec0-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bec0-128">See also</span></span>

- [<span data-ttu-id="7bec0-129">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="7bec0-129">Query Examples</span></span>](query-examples.md)
