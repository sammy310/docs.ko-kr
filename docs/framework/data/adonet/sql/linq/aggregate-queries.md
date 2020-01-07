---
title: 집계 쿼리
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 8defefb39974bea150fed84b0e7404b43882c41c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634744"
---
# <a name="aggregate-queries"></a><span data-ttu-id="ad332-102">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="ad332-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ad332-103">에서는 `Average`, `Count`, `Max`, `Min` 및 `Sum` 집계 연산자가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="ad332-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 집계 연산자의 다음과 같은 특징에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="ad332-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="ad332-105">집계 쿼리는 즉시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="ad332-106">자세한 내용은 [LINQ 쿼리 소개(C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad332-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="ad332-107">집계 쿼리는 일반적으로 컬렉션 대신 숫자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="ad332-108">자세한 내용은 [집계 작업](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad332-108">For more information, see [Aggregation Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="ad332-109">익명 형식에 대해서 집계를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="ad332-110">다음 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="ad332-111">자세한 내용은 [샘플 데이터베이스 다운로드](downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad332-111">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad332-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ad332-112">In This Section</span></span>  
 [<span data-ttu-id="ad332-113">숫자 시퀀스에서 평균 값 반환</span><span class="sxs-lookup"><span data-stu-id="ad332-113">Return the Average Value From a Numeric Sequence</span></span>](return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="ad332-114"><xref:System.Linq.Enumerable.Average%2A> 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="ad332-115">시퀀스의 요소 수 계산</span><span class="sxs-lookup"><span data-stu-id="ad332-115">Count the Number of Elements in a Sequence</span></span>](count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="ad332-116"><xref:System.Linq.Enumerable.Count%2A> 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="ad332-117">숫자 시퀀스에서 최대값 찾기</span><span class="sxs-lookup"><span data-stu-id="ad332-117">Find the Maximum Value in a Numeric Sequence</span></span>](find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="ad332-118"><xref:System.Linq.Enumerable.Max%2A> 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="ad332-119">숫자 시퀀스에서 최소값 찾기</span><span class="sxs-lookup"><span data-stu-id="ad332-119">Find the Minimum Value in a Numeric Sequence</span></span>](find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="ad332-120"><xref:System.Linq.Enumerable.Min%2A> 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="ad332-121">숫자 시퀀스에서 값의 합계 컴퓨팅</span><span class="sxs-lookup"><span data-stu-id="ad332-121">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="ad332-122"><xref:System.Linq.Enumerable.Sum%2A> 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ad332-123">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="ad332-123">Related Sections</span></span>  
 [<span data-ttu-id="ad332-124">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="ad332-124">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="ad332-125">Visual Basic 및 C#의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="ad332-126">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="ad332-126">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="ad332-127">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 LINQ 쿼리를 디자인 하는 개념을 설명 하는 항목에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-127">Provides links to topics that explain concepts for designing LINQ queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="ad332-128">LINQ 쿼리 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="ad332-128">Introduction to LINQ Queries (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="ad332-129">LINQ에서 쿼리를 작동 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad332-129">Explains how queries work in LINQ.</span></span>
