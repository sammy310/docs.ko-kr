---
title: 시작
description: 이 샘플 코드를 사용 하 여 메모리 내 컬렉션에 액세스 하는 것과 마찬가지로 LINQ 기술을 사용 하 여 SQL 데이터베이스에 액세스 하는 LINQ to SQL 사용을 시작 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: a46c42e917bdab0d32ee594bbcd604ee9e3d26bc
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286419"
---
# <a name="getting-started"></a><span data-ttu-id="b38de-103">시작하기</span><span class="sxs-lookup"><span data-stu-id="b38de-103">Getting Started</span></span>
<span data-ttu-id="b38de-104">를 사용 하 여 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 메모리 내 컬렉션에 액세스 하는 것과 마찬가지로 LINQ 기술을 사용 하 여 SQL 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b38de-104">By using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you can use the LINQ technology to access SQL databases just as you would access an in-memory collection.</span></span>  
  
 <span data-ttu-id="b38de-105">예를 들어 다음 코드에서 `nw` 개체는 `Northwind` 데이터베이스를 나타내기 위해 만든 것으로 `Customers` 테이블을 대상으로 열은 `Customers`에서 `London`가 필터링되고 `CompanyName`에 대한 문자열은 검색용으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="b38de-105">For example, the `nw` object in the following code is created to represent the `Northwind` database, the `Customers` table is targeted, the rows are filtered for `Customers` from `London`, and a string for `CompanyName` is selected for retrieval.</span></span>  
  
 <span data-ttu-id="b38de-106">루프가 실행되면 `CompanyName` 값의 컬렉션이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="b38de-106">When the loop is executed, the collection of `CompanyName` values is retrieved.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="b38de-107">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b38de-107">Next Steps</span></span>  
 <span data-ttu-id="b38de-108">삽입 및 업데이트를 비롯 한 몇 가지 추가 예는 [LINQ to SQL에서 수행할 수 있는 작업](what-you-can-do-with-linq-to-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b38de-108">For some additional examples, including inserting and updating, see [What You Can Do With LINQ to SQL](what-you-can-do-with-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="b38de-109">그런 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 실제 경험을 가지는 연습과 자습서를 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b38de-109">Next, try some walkthroughs and tutorials to have a hands-on experience of using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="b38de-110">[연습 별 학습](learning-by-walkthroughs.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b38de-110">See [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>  
  
 <span data-ttu-id="b38de-111">마지막으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] [LINQ to SQL 사용에 대 한 일반적인 단계](typical-steps-for-using-linq-to-sql.md)를 참조 하 여 고유한 프로젝트를 시작 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b38de-111">Finally, learn how to get started on your own [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project by reading [Typical Steps for Using LINQ to SQL](typical-steps-for-using-linq-to-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b38de-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b38de-112">See also</span></span>

- [<span data-ttu-id="b38de-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b38de-113">LINQ to SQL</span></span>](index.md)
- [<span data-ttu-id="b38de-114">LINQ 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="b38de-114">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="b38de-115">LINQ 소개(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b38de-115">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="b38de-116">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="b38de-116">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
