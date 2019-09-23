---
title: 두 시퀀스의 합집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 058856243b2a8daaecd653a9b5999013de5407a8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182519"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="2cbea-102">두 시퀀스의 합집합 반환</span><span class="sxs-lookup"><span data-stu-id="2cbea-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="2cbea-103"><xref:System.Linq.Queryable.Union%2A> 연산자를 사용하여 두 시퀀스의 합집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbea-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cbea-104">예제</span><span class="sxs-lookup"><span data-stu-id="2cbea-104">Example</span></span>  
 <span data-ttu-id="2cbea-105">이 예에서는 <xref:System.Linq.Queryable.Union%2A> 를 사용 하 여 `Customers` 또는 `Employees`가 있는 모든 국가/지역의 시퀀스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbea-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries/regions in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="2cbea-106">에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]연산자는 <xref:System.Linq.Queryable.Union%2A> 다중 집합에 대해 순서가 지정 되지 않은 다중 집합의 연결 (SQL의 [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) 절 결과 효과적)으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cbea-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) clause in SQL).</span></span>

<span data-ttu-id="2cbea-107">자세한 내용과 예제는를 참조 <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>하세요.</span><span class="sxs-lookup"><span data-stu-id="2cbea-107">For more info and examples, see <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2cbea-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cbea-108">See also</span></span>

- [<span data-ttu-id="2cbea-109">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="2cbea-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="2cbea-110">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="2cbea-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
