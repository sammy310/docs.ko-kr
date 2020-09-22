---
title: Order By 절
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: 05fa720237f4b0185b5c07217362c99b5dbf4303
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869797"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="17925-102">Order By 절 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17925-102">Order By Clause (Visual Basic)</span></span>

<span data-ttu-id="17925-103">쿼리 결과의 정렬 순서를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="17925-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17925-104">구문</span><span class="sxs-lookup"><span data-stu-id="17925-104">Syntax</span></span>  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="17925-105">부분</span><span class="sxs-lookup"><span data-stu-id="17925-105">Parts</span></span>  

 `orderExp1`  
 <span data-ttu-id="17925-106">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="17925-106">Required.</span></span> <span data-ttu-id="17925-107">반환 된 값의 순서를 지정 하는 방법을 식별 하는 현재 쿼리 결과에서 하나 이상의 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="17925-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="17925-108">필드 이름은 쉼표 (,)로 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17925-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="17925-109">또는 키워드를 사용 하 여 각 필드를 오름차순 또는 내림차순으로 정렬 하 여 식별할 수 있습니다 `Ascending` `Descending` .</span><span class="sxs-lookup"><span data-stu-id="17925-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="17925-110">`Ascending`또는 키워드가 지정 되지 않은 경우 `Descending` 기본 정렬 순서는 오름차순입니다.</span><span class="sxs-lookup"><span data-stu-id="17925-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="17925-111">정렬 순서 필드는 왼쪽에서 오른쪽으로 우선 순위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17925-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17925-112">설명</span><span class="sxs-lookup"><span data-stu-id="17925-112">Remarks</span></span>  

 <span data-ttu-id="17925-113">절을 사용 `Order By` 하 여 쿼리 결과를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17925-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="17925-114">`Order By`절은 현재 범위에 대 한 범위 변수에 따라 결과만 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17925-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="17925-115">예를 들어 `Select` 절은 쿼리 식에서 해당 범위에 대 한 새 반복 변수를 사용 하 여 새 범위를 도입 합니다.</span><span class="sxs-lookup"><span data-stu-id="17925-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="17925-116">쿼리에서 절 앞에 정의 된 범위 변수 `Select` 는 절 뒤에서 사용할 수 없습니다 `Select` .</span><span class="sxs-lookup"><span data-stu-id="17925-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="17925-117">따라서 절에서 사용할 수 없는 필드를 기준으로 결과를 정렬 하려면 절 `Select` 앞에 절을 추가 해야 합니다 `Order By` `Select` .</span><span class="sxs-lookup"><span data-stu-id="17925-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="17925-118">이 작업을 수행 해야 하는 한 가지 예는 결과의 일부로 반환 되지 않는 필드를 기준으로 쿼리를 정렬 하려는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="17925-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="17925-119">필드에 대 한 오름차순 및 내림차순은 <xref:System.IComparable> 필드의 데이터 형식에 대 한 인터페이스의 구현에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17925-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="17925-120">데이터 형식이 인터페이스를 구현 하지 않는 경우 <xref:System.IComparable> 정렬 순서는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17925-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17925-121">예제</span><span class="sxs-lookup"><span data-stu-id="17925-121">Example</span></span>  

 <span data-ttu-id="17925-122">다음 쿼리 식에서는 절을 사용 하 여 `From` `book` 컬렉션에 대 한 범위 변수를 선언 합니다 `books` .</span><span class="sxs-lookup"><span data-stu-id="17925-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="17925-123">`Order By`절은 가격을 기준으로 쿼리 결과를 오름차순 (기본값)으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="17925-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="17925-124">가격이 동일한 책은 제목으로 오름차순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17925-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="17925-125">`Select`절은 `Title` `Price` 쿼리에서 반환 된 값으로 및 속성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="17925-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="17925-126">예제</span><span class="sxs-lookup"><span data-stu-id="17925-126">Example</span></span>  

 <span data-ttu-id="17925-127">다음 쿼리 식에서는 절을 사용 하 여 `Order By` 가격 기준으로 쿼리 결과를 내림차순으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="17925-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="17925-128">가격이 동일한 책은 제목으로 오름차순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17925-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="17925-129">예제</span><span class="sxs-lookup"><span data-stu-id="17925-129">Example</span></span>  

 <span data-ttu-id="17925-130">다음 쿼리 식에서는 절을 사용 하 여 `Select` 책 제목, 가격, 게시 날짜 및 작성자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="17925-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="17925-131">그런 다음 `Title` `Price` `PublishDate` `Author` 새 범위에 대 한 범위 변수의,, 및 필드를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="17925-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="17925-132">`Order By`절은 새 범위 변수를 저자 이름, 책 제목 및 가격을 기준으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="17925-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="17925-133">각 열은 기본 순서 (오름차순)로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17925-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="17925-134">참조</span><span class="sxs-lookup"><span data-stu-id="17925-134">See also</span></span>

- [<span data-ttu-id="17925-135">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="17925-135">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="17925-136">쿼리</span><span class="sxs-lookup"><span data-stu-id="17925-136">Queries</span></span>](index.md)
- [<span data-ttu-id="17925-137">Select 절</span><span class="sxs-lookup"><span data-stu-id="17925-137">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="17925-138">From 절</span><span class="sxs-lookup"><span data-stu-id="17925-138">From Clause</span></span>](from-clause.md)
