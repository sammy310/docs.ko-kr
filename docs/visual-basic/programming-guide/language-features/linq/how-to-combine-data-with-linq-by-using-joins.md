---
title: '방법: 조인을 사용 하 여 데이터를 LINQ와 결합'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: 7279908c5d262b65f4c4da9cd9b6c1b4117bc402
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344998"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="cf9b5-102">방법: 조인을 사용하여 데이터와 LINQ 결합(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf9b5-102">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>
<span data-ttu-id="cf9b5-103">Visual Basic는 컬렉션 간의 공통 값을 기준으로 여러 컬렉션의 내용을 결합할 수 있도록 `Join` 및 `Group Join` 쿼리 절을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-103">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="cf9b5-104">이러한 값을 *키* 값 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-104">These values are known as *key* values.</span></span> <span data-ttu-id="cf9b5-105">관계형 데이터베이스 개념에 익숙한 개발자는 `Join` 절을 내부 조인으로 인식 하 고 `Group Join` 절을 효과적으로 왼쪽 우선 외부 조인으로 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-105">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="cf9b5-106">이 항목의 예에서는 `Join` 및 `Group Join` 쿼리 절을 사용 하 여 데이터를 결합 하는 몇 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-106">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="cf9b5-107">프로젝트 만들기 및 샘플 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="cf9b5-107">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="cf9b5-108">샘플 데이터 및 형식을 포함 하는 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf9b5-108">To create a project that contains sample data and types</span></span>  
  
1. <span data-ttu-id="cf9b5-109">이 항목의 예제를 실행 하려면 Visual Studio를 열고 새 Visual Basic 콘솔 응용 프로그램 프로젝트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-109">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="cf9b5-110">Visual Basic에서 만든 module1.vb 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-110">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2. <span data-ttu-id="cf9b5-111">이 항목의 샘플에서는 다음 코드 예제의 `Person` 및 `Pet` 형식과 데이터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-111">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="cf9b5-112">Visual Basic에서 만든 기본 `Module1` 모듈에이 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-112">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="cf9b5-113">Join 절을 사용 하 여 내부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="cf9b5-113">Perform an Inner Join by Using the Join Clause</span></span>  
 <span data-ttu-id="cf9b5-114">내부 조인은 두 컬렉션의 데이터를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-114">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="cf9b5-115">지정 된 키 값이 일치 하는 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-115">Items for which the specified key values match are included.</span></span> <span data-ttu-id="cf9b5-116">다른 컬렉션에 일치 하는 항목이 없는 컬렉션 중 하나의 항목은 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-116">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="cf9b5-117">Visual Basic에서 LINQ는 내부 조인을 수행 하기 위한 두 가지 옵션, 즉 암시적 조인과 명시적 조인을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-117">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="cf9b5-118">암시적 조인은 `From` 절에 조인할 컬렉션을 지정 하 고 `Where` 절에서 일치 하는 키 필드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-118">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="cf9b5-119">Visual Basic는 지정 된 키 필드에 따라 두 컬렉션을 암시적으로 조인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-119">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="cf9b5-120">조인에서 사용할 키 필드에 대해 구체적으로 지정 하려는 경우 `Join` 절을 사용 하 여 명시적 조인을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-120">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="cf9b5-121">이 경우에도 `Where` 절을 사용 하 여 쿼리 결과를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-121">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="cf9b5-122">Join 절을 사용 하 여 내부 조인을 수행 하려면</span><span class="sxs-lookup"><span data-stu-id="cf9b5-122">To perform an Inner Join by using the Join clause</span></span>  
  
1. <span data-ttu-id="cf9b5-123">프로젝트의 `Module1` 모듈에 다음 코드를 추가 하 여 암시적 및 명시적 내부 조인의 예제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-123">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="cf9b5-124">Group Join 절을 사용 하 여 왼쪽 우선 외부 조인을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-124">Perform a Left Outer Join by Using the Group Join Clause</span></span>  
 <span data-ttu-id="cf9b5-125">왼쪽 우선 외부 조인은 조인의 왼쪽 컬렉션에 있는 모든 항목을 포함 하 고 조인의 오른쪽 컬렉션에서 일치 하는 값만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-125">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="cf9b5-126">왼쪽 컬렉션에 일치 하는 항목이 없는 조인의 오른쪽 컬렉션에 있는 항목은 쿼리 결과에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-126">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="cf9b5-127">`Group Join` 절은 왼쪽 우선 외부 조인을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-127">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="cf9b5-128">일반적으로 왼쪽 우선 외부 조인 이라고 하는 것과 `Group Join` 절에서 반환 되는 항목의 차이는 `Group Join` 절이 왼쪽 컬렉션의 각 항목에 대 한 조인의 오른쪽 컬렉션에서 결과를 그룹화 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-128">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="cf9b5-129">관계형 데이터베이스에서 왼쪽 우선 외부 조인은 쿼리 결과의 각 항목이 조인에 있는 두 컬렉션의 일치 하는 항목을 포함 하는 그룹화 되지 않은 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-129">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="cf9b5-130">이 경우 조인의 왼쪽 컬렉션의 항목이 오른쪽 컬렉션에서 일치 하는 각 항목에 대해 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-130">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="cf9b5-131">다음 절차를 완료 하면이 모양이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-131">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="cf9b5-132">그룹화 된 각 쿼리 결과에 대 한 항목을 반환 하도록 쿼리를 확장 하 여 `Group Join` 쿼리의 결과를 그룹화 되지 않은 결과로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-132">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="cf9b5-133">이렇게 하려면 그룹화 된 컬렉션의 `DefaultIfEmpty` 메서드를 쿼리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-133">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="cf9b5-134">이렇게 하면 조인의 왼쪽 컬렉션의 항목이 오른쪽 컬렉션에서 일치 하는 결과가 없더라도 쿼리 결과에 계속 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-134">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="cf9b5-135">조인의 오른쪽 컬렉션에서 일치 하는 값이 없는 경우 기본 결과 값을 제공 하기 위해 쿼리에 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-135">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="cf9b5-136">Group Join 절을 사용 하 여 왼쪽 우선 외부 조인을 수행 하려면</span><span class="sxs-lookup"><span data-stu-id="cf9b5-136">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1. <span data-ttu-id="cf9b5-137">프로젝트의 `Module1` 모듈에 다음 코드를 추가 하 여 그룹화 된 왼쪽 우선 외부 조인과 그룹화 되지 않은 왼쪽 우선 외부 조인의 예를 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-137">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="cf9b5-138">복합 키를 사용 하 여 조인 수행</span><span class="sxs-lookup"><span data-stu-id="cf9b5-138">Perform a Join by Using a Composite Key</span></span>  
 <span data-ttu-id="cf9b5-139">`Join` 또는 `Group Join` 절에서 `And` 키워드를 사용 하 여 조인 되는 컬렉션의 값을 일치 시킬 때 사용할 여러 키 필드를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-139">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="cf9b5-140">`And` 키워드는 지정 된 모든 키 필드가 조인할 항목에 대해 일치 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-140">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="cf9b5-141">복합 키를 사용 하 여 조인을 수행 하려면</span><span class="sxs-lookup"><span data-stu-id="cf9b5-141">To perform a Join by using a composite key</span></span>  
  
1. <span data-ttu-id="cf9b5-142">프로젝트의 `Module1` 모듈에 다음 코드를 추가 하 여 복합 키를 사용 하는 조인의 예를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-142">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a><span data-ttu-id="cf9b5-143">코드 실행</span><span class="sxs-lookup"><span data-stu-id="cf9b5-143">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="cf9b5-144">예제를 실행 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="cf9b5-144">To add code to run the examples</span></span>  
  
1. <span data-ttu-id="cf9b5-145">이 항목의 예제를 실행 하려면 프로젝트의 `Module1` 모듈에 있는 `Sub Main`를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-145">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. <span data-ttu-id="cf9b5-146">F5 키를 눌러 예제를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b5-146">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf9b5-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="cf9b5-147">See also</span></span>

- [<span data-ttu-id="cf9b5-148">LINQ</span><span class="sxs-lookup"><span data-stu-id="cf9b5-148">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="cf9b5-149">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="cf9b5-149">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="cf9b5-150">Join 절</span><span class="sxs-lookup"><span data-stu-id="cf9b5-150">Join Clause</span></span>](../../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="cf9b5-151">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="cf9b5-151">Group Join Clause</span></span>](../../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="cf9b5-152">From 절</span><span class="sxs-lookup"><span data-stu-id="cf9b5-152">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="cf9b5-153">Where 절</span><span class="sxs-lookup"><span data-stu-id="cf9b5-153">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="cf9b5-154">쿼리</span><span class="sxs-lookup"><span data-stu-id="cf9b5-154">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="cf9b5-155">LINQ를 통한 데이터 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="cf9b5-155">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
