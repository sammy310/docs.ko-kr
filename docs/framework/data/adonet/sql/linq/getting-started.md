---
title: 시작
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 3bff4e9f268e9eac84c244cb58eed8b4384e717d
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634694"
---
# <a name="getting-started"></a><span data-ttu-id="fc353-102">시작</span><span class="sxs-lookup"><span data-stu-id="fc353-102">Getting Started</span></span>
<span data-ttu-id="fc353-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 사용 하 여 메모리 내 컬렉션에 액세스 하는 것과 마찬가지로 LINQ 기술을 사용 하 여 SQL database에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc353-103">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the LINQ technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="fc353-104">예를 들어 다음 코드에서 `nw` 개체는 `Northwind` 데이터베이스를 나타내기 위해 만든 것으로 `Customers` 테이블을 대상으로 열은 `Customers`에서 `London`가 필터링되고 `CompanyName`에 대한 문자열은 검색용으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc353-104">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="fc353-105">루프가 실행되면 `CompanyName` 값의 컬렉션이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc353-105">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="fc353-106">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fc353-106">Next Steps</span></span>  
 <span data-ttu-id="fc353-107">삽입 및 업데이트를 비롯 한 몇 가지 추가 예는 [LINQ to SQL에서 수행할 수 있는 작업](what-you-can-do-with-linq-to-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc353-107">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="fc353-108">그런 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 실제 경험을 가지는 연습과 자습서를 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="fc353-108">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="fc353-109">[연습 별 학습](learning-by-walkthroughs.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc353-109">See [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="fc353-110">마지막으로 [LINQ to SQL 사용에 대 한 일반적인 단계](typical-steps-for-using-linq-to-sql.md)를 참조 하 여 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트를 시작 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fc353-110">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc353-111">참조</span><span class="sxs-lookup"><span data-stu-id="fc353-111">See also</span></span>

- [<span data-ttu-id="fc353-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fc353-112">LINQ to SQL</span></span>](index.md)
- [<span data-ttu-id="fc353-113">LINQ 소개 (C#)</span><span class="sxs-lookup"><span data-stu-id="fc353-113">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="fc353-114">LINQ 소개(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc353-114">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="fc353-115">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="fc353-115">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
