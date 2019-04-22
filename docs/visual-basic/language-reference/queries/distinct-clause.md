---
title: Distinct 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: fbca9fa8aa227d8d5b6488bef179f4bda08bb38c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830060"
---
# <a name="distinct-clause-visual-basic"></a><span data-ttu-id="88b7e-102">Distinct 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88b7e-102">Distinct Clause (Visual Basic)</span></span>
<span data-ttu-id="88b7e-103">후속 쿼리 절에 중복 값을 제거 하려면 현재 범위 변수 값을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="88b7e-103">Restricts the values of the current range variable to eliminate duplicate values in subsequent query clauses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88b7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="88b7e-104">Syntax</span></span>  
  
```  
Distinct  
```  
  
## <a name="remarks"></a><span data-ttu-id="88b7e-105">설명</span><span class="sxs-lookup"><span data-stu-id="88b7e-105">Remarks</span></span>  
 <span data-ttu-id="88b7e-106">사용할 수는 `Distinct` 절 고유 항목의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88b7e-106">You can use the `Distinct` clause to return a list of unique items.</span></span> <span data-ttu-id="88b7e-107">`Distinct` 절로 인해 쿼리는 중복 되는 쿼리 결과 무시 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="88b7e-107">The `Distinct` clause causes the query to ignore duplicate query results.</span></span> <span data-ttu-id="88b7e-108">`Distinct` 절에서 지정 된 필드를 반환 하는 모든 중복 값에 적용 된 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="88b7e-108">The `Distinct` clause applies to duplicate values for all return fields specified by the `Select` clause.</span></span> <span data-ttu-id="88b7e-109">없으면 `Select` 절을 지정 합니다 `Distinct` 절에서 식별 된 쿼리에 대 한 범위 변수에 적용 되는 `From` 절.</span><span class="sxs-lookup"><span data-stu-id="88b7e-109">If no `Select` clause is specified, the `Distinct` clause is applied to the range variable for the query identified in the `From` clause.</span></span> <span data-ttu-id="88b7e-110">범위 변수는 변경할 수 없는 형식이 없는 경우 형식의 모든 멤버는 기존 쿼리 결과 일치 하는 경우 쿼리는 쿼리 결과 무시만 합니다.</span><span class="sxs-lookup"><span data-stu-id="88b7e-110">If the range variable is not an immutable type, the query will only ignore a query result if all members of the type match an existing query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88b7e-111">예제</span><span class="sxs-lookup"><span data-stu-id="88b7e-111">Example</span></span>  
 <span data-ttu-id="88b7e-112">다음 쿼리 식은 고객 주문 목록과 고객 목록에 조인합니다.</span><span class="sxs-lookup"><span data-stu-id="88b7e-112">The following query expression joins a list of customers and a list of customer orders.</span></span> <span data-ttu-id="88b7e-113">`Distinct` 절이 고유한 고객 이름 목록을 반환 하 고 주문 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="88b7e-113">The `Distinct` clause is included to return a list of unique customer names and order dates.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a><span data-ttu-id="88b7e-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="88b7e-114">See also</span></span>

- [<span data-ttu-id="88b7e-115">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="88b7e-115">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="88b7e-116">쿼리</span><span class="sxs-lookup"><span data-stu-id="88b7e-116">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="88b7e-117">From 절</span><span class="sxs-lookup"><span data-stu-id="88b7e-117">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="88b7e-118">Select 절</span><span class="sxs-lookup"><span data-stu-id="88b7e-118">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="88b7e-119">Where 절</span><span class="sxs-lookup"><span data-stu-id="88b7e-119">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
