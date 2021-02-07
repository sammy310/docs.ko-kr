---
description: '자세히 알아보기: Distinct 절 (Visual Basic)'
title: Distinct 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: df1cdc58f7af406533e67a396a958a26b0c79635
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700652"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="72c41-103">Distinct 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72c41-103">Distinct Clause (Visual Basic)</span></span>

<span data-ttu-id="72c41-104">후속 쿼리 절에서 중복 값을 제거 하도록 현재 범위 변수의 값을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="72c41-104">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c41-105">구문</span><span class="sxs-lookup"><span data-stu-id="72c41-105">Syntax</span></span>  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="72c41-106">설명</span><span class="sxs-lookup"><span data-stu-id="72c41-106">Remarks</span></span>  

 <span data-ttu-id="72c41-107">절을 사용 `Distinct` 하 여 고유한 항목의 목록을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72c41-107">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="72c41-108">`Distinct`절이 있으면 쿼리에서 중복 쿼리 결과가 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72c41-108">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="72c41-109">절은 `Distinct` 절에 지정 된 모든 반환 필드의 중복 값에 적용 됩니다 `Select` .</span><span class="sxs-lookup"><span data-stu-id="72c41-109">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="72c41-110">`Select`절이 지정 되지 않은 경우 절 `Distinct` 에서 식별 된 쿼리의 범위 변수에 절이 적용 됩니다 `From` .</span><span class="sxs-lookup"><span data-stu-id="72c41-110">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="72c41-111">범위 변수가 변경할 수 없는 형식이 아닌 경우에는 해당 형식의 모든 멤버가 기존 쿼리 결과와 일치 하는 경우에만 쿼리 결과가 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72c41-111">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72c41-112">예제</span><span class="sxs-lookup"><span data-stu-id="72c41-112">Example</span></span>  

 <span data-ttu-id="72c41-113">다음 쿼리 식은 고객 목록과 고객 주문 목록을 조인 합니다.</span><span class="sxs-lookup"><span data-stu-id="72c41-113">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="72c41-114">`Distinct`고유한 고객 이름 및 주문 날짜 목록을 반환 하는 절이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72c41-114">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="72c41-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72c41-115">See also</span></span>

- [<span data-ttu-id="72c41-116">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="72c41-116">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="72c41-117">쿼리</span><span class="sxs-lookup"><span data-stu-id="72c41-117">Queries</span></span>](index.md)
- [<span data-ttu-id="72c41-118">From 절</span><span class="sxs-lookup"><span data-stu-id="72c41-118">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="72c41-119">Select 절</span><span class="sxs-lookup"><span data-stu-id="72c41-119">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="72c41-120">Where 절</span><span class="sxs-lookup"><span data-stu-id="72c41-120">Where Clause</span></span>](where-clause.md)
