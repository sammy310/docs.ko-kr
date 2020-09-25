---
title: 문제 해결
ms.date: 03/30/2017
ms.assetid: 8cd4401c-b12c-4116-a421-f3dcffa65670
ms.openlocfilehash: 0ac71d9a55e92161f24deb490b8df6148bfc840c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202190"
---
# <a name="troubleshooting"></a><span data-ttu-id="ca3be-102">문제 해결</span><span class="sxs-lookup"><span data-stu-id="ca3be-102">Troubleshooting</span></span>

<span data-ttu-id="ca3be-103">다음은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 애플리케이션에서 발생할 수 있는 문제와 이러한 문제를 방지하거나 문제의 영향을 줄일 수 있는 방법에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-103">The following information exposes some issues you might encounter in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications, and provides suggestions to avoid or otherwise reduce the effect of these issues.</span></span>  
  
 <span data-ttu-id="ca3be-104">추가 문제는 faq (질문과 [대답](frequently-asked-questions.md))로 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-104">Additional issues are addressed in [Frequently Asked Questions](frequently-asked-questions.md).</span></span>  
  
## <a name="unsupported-standard-query-operators"></a><span data-ttu-id="ca3be-105">지원되지 않는 표준 쿼리 연산자</span><span class="sxs-lookup"><span data-stu-id="ca3be-105">Unsupported Standard Query Operators</span></span>  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ca3be-106">에서는 모든 표준 쿼리 연산자 메서드(예: <xref:System.Linq.Enumerable.ElementAt%2A>)를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-106">does not support all standard query operator methods (for example, <xref:System.Linq.Enumerable.ElementAt%2A>).</span></span> <span data-ttu-id="ca3be-107">그 결과 프로젝트를 컴파일할 때 런타임 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-107">As a result, projects that compile can still produce run-time errors.</span></span> <span data-ttu-id="ca3be-108">자세한 내용은 [표준 쿼리 연산자 변환](standard-query-operator-translation.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca3be-108">For more information, see [Standard Query Operator Translation](standard-query-operator-translation.md).</span></span>  
  
## <a name="memory-issues"></a><span data-ttu-id="ca3be-109">메모리 문제</span><span class="sxs-lookup"><span data-stu-id="ca3be-109">Memory Issues</span></span>  

 <span data-ttu-id="ca3be-110">쿼리에 메모리 내 컬렉션과이 포함 된 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> 두 컬렉션을 지정한 순서에 따라 쿼리가 메모리에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-110">If a query involves an in-memory collection and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601>, the query might be executed in memory, depending on the order in which the two collections are specified.</span></span> <span data-ttu-id="ca3be-111">쿼리를 메모리 내에서 실행해야 할 경우에는 데이터베이스 테이블의 데이터를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-111">If the query must be executed in memory, then the data from the database table will need to be retrieved.</span></span>  
  
 <span data-ttu-id="ca3be-112">이 방법은 비효율적이며 메모리와 프로세서를 상당히 많이 사용할 수 있으므로</span><span class="sxs-lookup"><span data-stu-id="ca3be-112">This approach is inefficient and could result in significant memory and processor usage.</span></span> <span data-ttu-id="ca3be-113">가능하면 이와 같은 다중 도메인 쿼리를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ca3be-113">Try to avoid such multi-domain queries.</span></span>  
  
## <a name="file-names-and-sqlmetal"></a><span data-ttu-id="ca3be-114">파일 이름과 SQLMetal</span><span class="sxs-lookup"><span data-stu-id="ca3be-114">File Names and SQLMetal</span></span>  

 <span data-ttu-id="ca3be-115">입력 파일 이름을 지정하려면 이름을 명령줄에 입력 파일로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-115">To specify an input file name, add the name to the command line as the input file.</span></span> <span data-ttu-id="ca3be-116">**/conn** 옵션을 사용하여 연결 문자열에 파일 이름을 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-116">Including the file name in the connection string (using the **/conn** option) is not supported.</span></span> <span data-ttu-id="ca3be-117">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca3be-117">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="class-library-projects"></a><span data-ttu-id="ca3be-118">클래스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="ca3be-118">Class Library Projects</span></span>  

 <span data-ttu-id="ca3be-119">개체 관계형 디자이너는 프로젝트의 파일에 연결 문자열을 만듭니다 `app.config` .</span><span class="sxs-lookup"><span data-stu-id="ca3be-119">The Object Relational Designer creates a connection string in the `app.config` file of the project.</span></span> <span data-ttu-id="ca3be-120">클래스 라이브러리 프로젝트에는 `app.config` 파일이 사용되지 않으며</span><span class="sxs-lookup"><span data-stu-id="ca3be-120">In class library projects, the `app.config` file is not used.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ca3be-121">에서는 디자인 타임 파일에 제공되는 연결 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-121">uses the Connection String provided in the design-time files.</span></span> <span data-ttu-id="ca3be-122">따라서 `app.config`에서 값을 변경해도 애플리케이션에서 연결하는 데이터베이스가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-122">Changing the value in `app.config` does not change the database to which your application connects.</span></span>  
  
## <a name="cascade-delete"></a><span data-ttu-id="ca3be-123">하위 삭제</span><span class="sxs-lookup"><span data-stu-id="ca3be-123">Cascade Delete</span></span>  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ca3be-124">에서는 하위 삭제 작업을 지원 하거나 인식 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-124">does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="ca3be-125">제약 조건이 있는 테이블의 행을 삭제하려면 다음 작업 중 하나를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-125">If you want to delete a row in a table that has constraints against it, you must do either of the following:</span></span>  
  
- <span data-ttu-id="ca3be-126">데이터베이스의 외래 키 제약 조건에 `ON DELETE CASCADE` 규칙을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-126">Set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database.</span></span>  
  
- <span data-ttu-id="ca3be-127">사용자 고유의 코드를 사용하여 부모 개체를 삭제하는 데 방해가 되는 자식 개체를 먼저 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-127">Use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span>  
  
 <span data-ttu-id="ca3be-128"><xref:System.Data.SqlClient.SqlException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-128">Otherwise, a <xref:System.Data.SqlClient.SqlException> exception is thrown.</span></span>  
  
 <span data-ttu-id="ca3be-129">자세한 내용은 [방법: 데이터베이스에서 행 삭제](how-to-delete-rows-from-the-database.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca3be-129">For more information, see [How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md).</span></span>  
  
## <a name="expression-not-queryable"></a><span data-ttu-id="ca3be-130">쿼리할 수 없는 식</span><span class="sxs-lookup"><span data-stu-id="ca3be-130">Expression Not Queryable</span></span>  

 <span data-ttu-id="ca3be-131">"Expression [expression] 형식의 식은 쿼리할 수 없습니다. 어셈블리 참조가 있는지 확인하십시오." 오류가 나타나면</span><span class="sxs-lookup"><span data-stu-id="ca3be-131">If you get the "Expression [expression] is not queryable; are you missing an assembly reference?"</span></span> <span data-ttu-id="ca3be-132">다음 사항을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca3be-132">error, make sure of the following:</span></span>  
  
- <span data-ttu-id="ca3be-133">응용 프로그램은 .NET Compact Framework 3.5를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-133">Your application is targeting .NET Compact Framework 3.5.</span></span>  
  
- <span data-ttu-id="ca3be-134">`System.Core.dll` 및 `System.Data.Linq.dll`에 대한 참조가 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="ca3be-134">You have a reference to `System.Core.dll` and `System.Data.Linq.dll`.</span></span>  
  
- <span data-ttu-id="ca3be-135">`Imports` `using` 및에 대 한 (Visual Basic) 또는 (c #) 지시문이 있습니다 <xref:System.Linq> <xref:System.Data.Linq> .</span><span class="sxs-lookup"><span data-stu-id="ca3be-135">You have an `Imports` (Visual Basic) or `using` (C#) directive for <xref:System.Linq> and <xref:System.Data.Linq>.</span></span>  
  
## <a name="duplicatekeyexception"></a><span data-ttu-id="ca3be-136">DuplicateKeyException</span><span class="sxs-lookup"><span data-stu-id="ca3be-136">DuplicateKeyException</span></span>  

 <span data-ttu-id="ca3be-137">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트를 디버깅하는 동안 엔터티의 관계를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-137">In the course of debugging a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project, you might traverse an entity's relations.</span></span> <span data-ttu-id="ca3be-138">이렇게 하면 이러한 항목이 캐시에 들어 오고 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 이를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-138">Doing so brings these items into the cache, and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] becomes aware of their presence.</span></span> <span data-ttu-id="ca3be-139">이 상태에서 <xref:System.Data.Linq.Table%601.Attach%2A>나 <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>을 실행하거나 키가 동일한 여러 행을 생성하는 유사한 메서드를 실행하면 <xref:System.Data.Linq.DuplicateKeyException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-139">If you then try to execute <xref:System.Data.Linq.Table%601.Attach%2A> or <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> or a similar method that produces multiple rows that have the same key, a <xref:System.Data.Linq.DuplicateKeyException> is thrown.</span></span>  
  
## <a name="string-concatenation-exceptions"></a><span data-ttu-id="ca3be-140">문자열 연결 예외</span><span class="sxs-lookup"><span data-stu-id="ca3be-140">String Concatenation Exceptions</span></span>  

 <span data-ttu-id="ca3be-141">`[n]text`와 다른 `[n][var]char`에 매핑된 피연산자는 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-141">Concatenation on operands mapped to `[n]text` and other `[n][var]char` is not supported.</span></span> <span data-ttu-id="ca3be-142">서로 다른 두 형식 집합에 매핑된 문자열을 연결하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-142">An exception is thrown for concatenation of strings mapped to the two different sets of types.</span></span> <span data-ttu-id="ca3be-143">자세한 내용은 [System.string 메서드](system-string-methods.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca3be-143">For more information, see [System.String Methods](system-string-methods.md).</span></span>  
  
## <a name="skip-and-take-exceptions-in-sql-server-2000"></a><span data-ttu-id="ca3be-144">SQL Server 2000의 Skip 및 Take 예외</span><span class="sxs-lookup"><span data-stu-id="ca3be-144">Skip and Take Exceptions in SQL Server 2000</span></span>  

 <span data-ttu-id="ca3be-145">SQL Server 2000 데이터베이스에 대해 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 또는 <xref:System.Linq.Queryable.Take%2A>을 사용할 때는 ID 멤버(<xref:System.Linq.Queryable.Skip%2A>)를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-145">You must use identity members (<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>) when you use <xref:System.Linq.Queryable.Take%2A> or <xref:System.Linq.Queryable.Skip%2A> against a SQL Server 2000 database.</span></span> <span data-ttu-id="ca3be-146">조인이 아니라 단일 테이블에 대해 쿼리를 실행하거나, 쿼리가 <xref:System.Linq.Queryable.Distinct%2A>, <xref:System.Linq.Queryable.Except%2A>, <xref:System.Linq.Queryable.Intersect%2A> 또는 <xref:System.Linq.Queryable.Union%2A> 작업이어야 하며 쿼리에 <xref:System.Linq.Queryable.Concat%2A> 작업이 포함되면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-146">The query must be against a single table (that is, not a join), or be a <xref:System.Linq.Queryable.Distinct%2A>, <xref:System.Linq.Queryable.Except%2A>, <xref:System.Linq.Queryable.Intersect%2A>, or <xref:System.Linq.Queryable.Union%2A> operation, and must not include a <xref:System.Linq.Queryable.Concat%2A> operation.</span></span> <span data-ttu-id="ca3be-147">자세한 내용은 [표준 쿼리 연산자 변환](standard-query-operator-translation.md)에서 "SQL Server 2000 지원" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca3be-147">For more information, see the "SQL Server 2000 Support" section in [Standard Query Operator Translation](standard-query-operator-translation.md).</span></span>  
  
 <span data-ttu-id="ca3be-148">SQL Server 2005에는이 요구 사항이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-148">This requirement does not apply to SQL Server 2005.</span></span>  
  
## <a name="groupby-invalidoperationexception"></a><span data-ttu-id="ca3be-149">GroupBy InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="ca3be-149">GroupBy InvalidOperationException</span></span>  

 <span data-ttu-id="ca3be-150"><xref:System.Linq.Enumerable.GroupBy%2A>처럼 `boolean` 식을 사용하여 그룹화하는 `group x by (Phone==@phone)` 쿼리에서 열 값이 null이면 이 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-150">This exception is thrown when a column value is null in a <xref:System.Linq.Enumerable.GroupBy%2A> query that groups by a `boolean` expression, such as `group x by (Phone==@phone)`.</span></span> <span data-ttu-id="ca3be-151">식이 이므로 `boolean` 키는이 아니라로 유추 됩니다 `boolean` `nullable` `boolean` .</span><span class="sxs-lookup"><span data-stu-id="ca3be-151">Because the expression is a `boolean`, the key is inferred to be `boolean`, not `nullable` `boolean`.</span></span> <span data-ttu-id="ca3be-152">변환 된 비교가 null을 생성 하는 경우를에 할당 하려고 시도 하 `nullable` `boolean` `boolean` 고 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-152">When the translated comparison produces a null, an attempt is made to assign a `nullable` `boolean` to a `boolean`, and the exception is thrown.</span></span>  
  
 <span data-ttu-id="ca3be-153">null을 false로 처리하려는 경우에 이 문제를 해결하려면 다음과 같이 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca3be-153">To avoid this situation (assuming you want to treat nulls as false), use an approach such as the following:</span></span>  
  
 `GroupBy="(Phone != null) && (Phone=@Phone)"`  
  
## <a name="oncreated-partial-method"></a><span data-ttu-id="ca3be-154">OnCreated() 부분 메서드</span><span class="sxs-lookup"><span data-stu-id="ca3be-154">OnCreated() Partial Method</span></span>  

 <span data-ttu-id="ca3be-155">생성된 `OnCreated()` 메서드는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 원래 값의 복사본을 만들기 위해 생성자를 호출하는 시나리오를 포함하여, 개체 생성자가 호출될 때마다 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca3be-155">The generated method `OnCreated()` is called each time the object constructor is called, including the scenario in which [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] calls the constructor to make a copy for original values.</span></span> <span data-ttu-id="ca3be-156">고유한 부분 클래스에 `OnCreated()` 메서드를 구현할 때 이 동작을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="ca3be-156">Take this behavior into account if you implement the `OnCreated()` method in your own partial class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca3be-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca3be-157">See also</span></span>

- [<span data-ttu-id="ca3be-158">디버깅 지원</span><span class="sxs-lookup"><span data-stu-id="ca3be-158">Debugging Support</span></span>](debugging-support.md)
- [<span data-ttu-id="ca3be-159">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="ca3be-159">Frequently Asked Questions</span></span>](frequently-asked-questions.md)
