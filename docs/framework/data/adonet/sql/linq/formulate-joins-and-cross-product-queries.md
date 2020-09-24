---
title: '방법: 조인 및 교차곱 쿼리 작성'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 1527ad26524dbef3ac73b92e136cd22e33046483
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155889"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="eea48-102">방법: 조인 및 교차곱 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="eea48-102">Formulate Joins and Cross-Product Queries</span></span>

<span data-ttu-id="eea48-103">다음 예제에서는 여러 테이블의 결과를 결합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eea48-104">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-104">Example</span></span>  

 <span data-ttu-id="eea48-105">다음 예제에서는 `From` Visual Basic (c #의 절)에 있는 절에서 외래 키 탐색 `from` 을 사용 하 여 런던의 고객에 대 한 모든 주문을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="eea48-106">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-106">Example</span></span>  

 <span data-ttu-id="eea48-107">다음 예제에서는 `Where` Visual Basic (c #의 절)에 있는 절에서 외래 키 탐색을 사용 하 여 `where` 가 미국에 있는 품절을 필터링 `Products` `Supplier` 합니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="eea48-108">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-108">Example</span></span>  

 <span data-ttu-id="eea48-109">다음 예제에서는 `From` Visual Basic (c #의 절)에 있는 절에서 외래 키 탐색을 사용 하 여 `from` 시애틀의 직원을 필터링 하 고 지역을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="eea48-110">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-110">Example</span></span>  

 <span data-ttu-id="eea48-111">다음 예제에서는 `Select` Visual Basic (c #의 절)에 있는 절에서 외래 키 탐색을 사용 하 여 `select` 한 직원이 다른 직원에 게 보고 하 고 두 직원이 동일한 경우의 직원 쌍을 필터링 합니다 `City` .</span><span class="sxs-lookup"><span data-stu-id="eea48-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="eea48-112">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-112">Example</span></span>  

 <span data-ttu-id="eea48-113">다음 Visual Basic 예제에서는 모든 고객과 주문을 찾고 주문이 고객과 일치 하도록 하며 해당 목록의 모든 고객에 대 한 연락처 이름이 제공 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="eea48-114">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-114">Example</span></span>  

 <span data-ttu-id="eea48-115">다음 예제에서는 두 테이블과 두 테이블에서 가져온 프로젝트 결과를 명시적으로 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="eea48-116">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-116">Example</span></span>  

 <span data-ttu-id="eea48-117">다음 예제에서는 세 테이블과 각 테이블에서 가져온 프로젝트 결과를 명시적으로 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="eea48-118">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-118">Example</span></span>  

 <span data-ttu-id="eea48-119">다음 예제에서는 `LEFT OUTER JOIN`를 사용하여 `DefaultIfEmpty()`을 얻는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="eea48-120">`DefaultIfEmpty()`에 `Order`가 없는 경우 `Employee` 메서드는 null을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="eea48-121">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-121">Example</span></span>  

 <span data-ttu-id="eea48-122">다음 예제에서는 조인으로 인해 생성된 `let` 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="eea48-123">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-123">Example</span></span>  

 <span data-ttu-id="eea48-124">다음 예제에서는 복합 키와 함께 사용된 `join`을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="eea48-125">예제</span><span class="sxs-lookup"><span data-stu-id="eea48-125">Example</span></span>  

 <span data-ttu-id="eea48-126">다음 예제에서는 한 면이 nullable이고 다른 면은 nullable이 아닌 `join`을 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eea48-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="eea48-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eea48-127">See also</span></span>

- [<span data-ttu-id="eea48-128">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="eea48-128">Query Examples</span></span>](query-examples.md)
