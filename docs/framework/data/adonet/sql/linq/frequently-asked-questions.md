---
description: '자세히 알아보기: 질문과 대답'
title: 질문과 대답
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
ms.openlocfilehash: 476e9adc3dc88bce786b8b8423e05e800c821320
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739081"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="c0745-103">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="c0745-103">Frequently Asked Questions</span></span>

<span data-ttu-id="c0745-104">다음 섹션에서는 LINQ를 구현할 때 발생할 수 있는 몇 가지 일반적인 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-104">The following sections answer some common issues that you might encounter when you implement LINQ.</span></span>

<span data-ttu-id="c0745-105">[문제 해결](troubleshooting.md)에서는 추가 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-105">Additional issues are addressed in [Troubleshooting](troubleshooting.md).</span></span>

## <a name="cannot-connect"></a><span data-ttu-id="c0745-106">연결할 수 없음</span><span class="sxs-lookup"><span data-stu-id="c0745-106">Cannot Connect</span></span>

<span data-ttu-id="c0745-107">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-107">Q.</span></span> <span data-ttu-id="c0745-108">데이터베이스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-108">I cannot connect to my database.</span></span>

<span data-ttu-id="c0745-109">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-109">A.</span></span> <span data-ttu-id="c0745-110">연결 문자열이 올바르고 SQL Server 인스턴스가 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-110">Make sure your connection string is correct and that your SQL Server instance is running.</span></span> <span data-ttu-id="c0745-111">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하려면 명명된 파이프 프로토콜도 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-111">Note also that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requires the Named Pipes protocol to be enabled.</span></span> <span data-ttu-id="c0745-112">자세한 내용은 [연습 별 학습](learning-by-walkthroughs.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0745-112">For more information, see [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

## <a name="changes-to-database-lost"></a><span data-ttu-id="c0745-113">데이터베이스 변경 내용 손실</span><span class="sxs-lookup"><span data-stu-id="c0745-113">Changes to Database Lost</span></span>

<span data-ttu-id="c0745-114">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-114">Q.</span></span> <span data-ttu-id="c0745-115">데이터베이스의 데이터를 변경했는데 애플리케이션을 다시 실행했더니 변경 내용이 없어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-115">I made a change to data in the database, but when I reran my application, the change was no longer there.</span></span>

<span data-ttu-id="c0745-116">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-116">A.</span></span> <span data-ttu-id="c0745-117"><xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하여 결과를 데이터베이스에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-117">Make sure that you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> to save results to the database.</span></span>

## <a name="database-connection-open-how-long"></a><span data-ttu-id="c0745-118">데이터베이스 연결: 연결 시간</span><span class="sxs-lookup"><span data-stu-id="c0745-118">Database Connection: Open How Long?</span></span>

<span data-ttu-id="c0745-119">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-119">Q.</span></span> <span data-ttu-id="c0745-120">데이터베이스는 얼마 동안 연결된 상태로 유지됩니까?</span><span class="sxs-lookup"><span data-stu-id="c0745-120">How long does my database connection remain open?</span></span>

<span data-ttu-id="c0745-121">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-121">A.</span></span> <span data-ttu-id="c0745-122">일반적으로 연결은 쿼리 결과를 사용할 때까지 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-122">A connection typically remains open until you consume the query results.</span></span> <span data-ttu-id="c0745-123">모든 결과를 처리 하는 데 시간이 오래 걸리고 결과를 캐싱하는 것이 아닌 경우 <xref:System.Linq.Enumerable.ToList%2A> 쿼리에을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-123">If you expect to take time to process all the results and are not opposed to caching the results, apply <xref:System.Linq.Enumerable.ToList%2A> to the query.</span></span> <span data-ttu-id="c0745-124">각 개체를 한 번만 처리하는 일반적인 시나리오에서는 `DataReader` 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 모두에서 스트리밍 모델을 사용하는 것이 더 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-124">In common scenarios where each object is processed only one time, the streaming model is superior in both `DataReader` and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

<span data-ttu-id="c0745-125">세부적인 연결 사용은 다음에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-125">The exact details of connection usage depend on the following:</span></span>

- <span data-ttu-id="c0745-126">연결 개체를 사용하여 <xref:System.Data.Linq.DataContext>를 만든 경우의 연결 상태</span><span class="sxs-lookup"><span data-stu-id="c0745-126">Connection status if the <xref:System.Data.Linq.DataContext> is constructed with a connection object.</span></span>

- <span data-ttu-id="c0745-127">연결 문자열 설정(예: MARS(Multiple Active Result Sets) 사용).</span><span class="sxs-lookup"><span data-stu-id="c0745-127">Connection string settings (for example, enabling Multiple Active Result Sets (MARS).</span></span> <span data-ttu-id="c0745-128">자세한 내용은 [MARS(여러 활성 결과 집합)](../multiple-active-result-sets-mars.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0745-128">For more information, see [Multiple Active Result Sets (MARS)](../multiple-active-result-sets-mars.md).</span></span>

## <a name="updating-without-querying"></a><span data-ttu-id="c0745-129">쿼리하지 않고 업데이트</span><span class="sxs-lookup"><span data-stu-id="c0745-129">Updating Without Querying</span></span>

<span data-ttu-id="c0745-130">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-130">Q.</span></span> <span data-ttu-id="c0745-131">데이터베이스를 먼저 쿼리하지 않고 테이블 데이터를 업데이트할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="c0745-131">Can I update table data without first querying the database?</span></span>

<span data-ttu-id="c0745-132">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-132">A.</span></span> <span data-ttu-id="c0745-133">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에는 설정 기반의 업데이트 명령이 없지만 다음 기술 중 하나를 사용하여 쿼리 없이 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-133">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not have set-based update commands, you can use either of the following techniques to update without first querying:</span></span>

- <span data-ttu-id="c0745-134"><xref:System.Data.Linq.DataContext.ExecuteCommand%2A>를 사용하여 SQL 코드를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-134">Use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to send SQL code.</span></span>

- <span data-ttu-id="c0745-135">개체의 새 인스턴스를 만든 후 업데이트에 영향을 주는 현재 값(필드)을 모두 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-135">Create a new instance of the object and initialize all the current values (fields) that affect the update.</span></span> <span data-ttu-id="c0745-136">그런 다음 <xref:System.Data.Linq.DataContext>를 사용하여 개체를 <xref:System.Data.Linq.Table%601.Attach%2A>에 연결하고 변경할 필드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-136">Then attach the object to the <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.Table%601.Attach%2A> and modify the field you want to change.</span></span>

## <a name="unexpected-query-results"></a><span data-ttu-id="c0745-137">예기치 않은 쿼리 결과</span><span class="sxs-lookup"><span data-stu-id="c0745-137">Unexpected Query Results</span></span>

<span data-ttu-id="c0745-138">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-138">Q.</span></span> <span data-ttu-id="c0745-139">쿼리가 예기치 않은 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-139">My query is returning unexpected results.</span></span> <span data-ttu-id="c0745-140">무슨 문제가 있는지 어떻게 확인합니까?</span><span class="sxs-lookup"><span data-stu-id="c0745-140">How can I inspect what is occurring?</span></span>

<span data-ttu-id="c0745-141">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-141">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="c0745-142">에는 생성된 SQL 코드를 검사할 수 있는 도구가 여러 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-142">provides several tools for inspecting the SQL code it generates.</span></span> <span data-ttu-id="c0745-143">그 중에서도 <xref:System.Data.Linq.DataContext.Log%2A>가 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-143">One of the most important is <xref:System.Data.Linq.DataContext.Log%2A>.</span></span> <span data-ttu-id="c0745-144">자세한 내용은 [디버깅 지원](debugging-support.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0745-144">For more information, see [Debugging Support](debugging-support.md).</span></span>

## <a name="unexpected-stored-procedure-results"></a><span data-ttu-id="c0745-145">예기치 않은 저장 프로시저 결과</span><span class="sxs-lookup"><span data-stu-id="c0745-145">Unexpected Stored Procedure Results</span></span>

<span data-ttu-id="c0745-146">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-146">Q.</span></span> <span data-ttu-id="c0745-147">`MAX()`를 사용하여 반환 값을 계산하는 저장 프로시저를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-147">I have a stored procedure whose return value is calculated by `MAX()`.</span></span> <span data-ttu-id="c0745-148">저장 프로시저를 O/R 디자이너 화면으로 끌면 반환 값이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-148">When I drag the stored procedure to the O/R Designer surface, the return value is not correct.</span></span>

<span data-ttu-id="c0745-149">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-149">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="c0745-150">에서는 다음과 같은 두 가지 방법으로 데이터베이스에서 생성된 값을 저장 프로시저를 통해 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-150">provides two ways to return database-generated values by way of stored procedures:</span></span>

- <span data-ttu-id="c0745-151">출력 결과에 이름을 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="c0745-151">By naming the output result.</span></span>

- <span data-ttu-id="c0745-152">출력 매개 변수를 명시적으로 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="c0745-152">By explicitly specifying an output parameter.</span></span>

<span data-ttu-id="c0745-153">다음은 잘못된 출력의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-153">The following is an example of incorrect output.</span></span> <span data-ttu-id="c0745-154">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 결과를 매핑할 수 없기 때문에 항상 0을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-154">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot map the results, it always returns 0:</span></span>

```sql
create procedure proc2

as

begin

select max(i) from t where name like 'hello'

end
```

<span data-ttu-id="c0745-155">다음은 출력 매개 변수를 사용하여 얻은 올바른 출력의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-155">The following is an example of correct output by using an output parameter:</span></span>

```sql
create procedure proc2

@result int OUTPUT

as

select @result = MAX(i) from t where name like 'hello'

go
```

<span data-ttu-id="c0745-156">다음은 출력 결과에 이름을 지정하여 얻은 올바른 출력의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-156">The following is an example of correct output by naming the output result:</span></span>

```sql
create procedure proc2

as

begin

select nax(i) AS MaxResult from t where name like 'hello'

end
```

<span data-ttu-id="c0745-157">자세한 내용은 [저장 프로시저를 사용 하 여 작업 사용자 지정](customizing-operations-by-using-stored-procedures.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0745-157">For more information, see [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md).</span></span>

## <a name="serialization-errors"></a><span data-ttu-id="c0745-158">Serialization 오류</span><span class="sxs-lookup"><span data-stu-id="c0745-158">Serialization Errors</span></span>

<span data-ttu-id="c0745-159">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-159">Q.</span></span> <span data-ttu-id="c0745-160">Serialize 하려고 하면 다음과 같은 오류가 발생 합니다. "Type ' ChangeTracker + StandardChangeTracker ' ... serializable로 표시 되어 있지 않습니다. "</span><span class="sxs-lookup"><span data-stu-id="c0745-160">When I try to serialize, I get the following error: "Type 'System.Data.Linq.ChangeTracker+StandardChangeTracker' ... is not marked as serializable."</span></span>

<span data-ttu-id="c0745-161">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-161">A.</span></span> <span data-ttu-id="c0745-162">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 코드 생성은 <xref:System.Runtime.Serialization.DataContractSerializer> serialization을 지원하지만</span><span class="sxs-lookup"><span data-stu-id="c0745-162">Code generation in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports <xref:System.Runtime.Serialization.DataContractSerializer> serialization.</span></span> <span data-ttu-id="c0745-163"><xref:System.Xml.Serialization.XmlSerializer> 또는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-163">It does not support <xref:System.Xml.Serialization.XmlSerializer> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="c0745-164">자세한 내용은 [Serialization](serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0745-164">For more information, see [Serialization](serialization.md).</span></span>

## <a name="multiple-dbml-files"></a><span data-ttu-id="c0745-165">여러 DBML 파일</span><span class="sxs-lookup"><span data-stu-id="c0745-165">Multiple DBML Files</span></span>

<span data-ttu-id="c0745-166">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-166">Q.</span></span> <span data-ttu-id="c0745-167">여러 DBML 파일에서 일부 테이블을 공유할 경우 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-167">When I have multiple DBML files that share some tables in common, I get a compiler error.</span></span>

<span data-ttu-id="c0745-168">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-168">A.</span></span> <span data-ttu-id="c0745-169">개체 관계형 디자이너의 **컨텍스트 네임 스페이스** 및 **엔터티 네임 스페이스** 속성을 각 DBML 파일에 대 한 고유 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-169">Set the **Context Namespace** and **Entity Namespace** properties from the Object Relational Designer to a distinct value for each DBML file.</span></span> <span data-ttu-id="c0745-170">이렇게 하면 이름/네임스페이스 충돌이 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-170">This approach eliminates the name/namespace collision.</span></span>

## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a><span data-ttu-id="c0745-171">삽입 또는 업데이트 시 데이터베이스에서 생성된 값을 명시적으로 설정해야 하는 문제 방지</span><span class="sxs-lookup"><span data-stu-id="c0745-171">Avoiding Explicit Setting of Database-Generated Values on Insert or Update</span></span>

<span data-ttu-id="c0745-172">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-172">Q.</span></span> <span data-ttu-id="c0745-173">데이터베이스 테이블에 SQL `DateCreated`를 기본값으로 사용하는 `Getdate()` 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-173">I have a database table with a `DateCreated` column that defaults to SQL `Getdate()`.</span></span> <span data-ttu-id="c0745-174">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하여 새 레코드를 삽입하려고 하면 값이 `NULL`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-174">When I try to insert a new record by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the value gets set to `NULL`.</span></span> <span data-ttu-id="c0745-175">데이터베이스의 기본값이 설정되어야 하지 않나요?</span><span class="sxs-lookup"><span data-stu-id="c0745-175">I would expect it to be set to the database default.</span></span>

<span data-ttu-id="c0745-176">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-176">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="c0745-177">은 ID(자동 증분)와 rowguidcol(데이터베이스에서 생성된 GUID) 및 타임스탬프 열에 대해서만 이와 같이 기본값을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-177">handles this situation automatically for identity (auto-increment) and rowguidcol (database-generated GUID) and timestamp columns.</span></span> <span data-ttu-id="c0745-178">및 속성을 수동으로 설정 해야 하는 경우도 있습니다 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> = `true` <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> = <xref:System.Data.Linq.Mapping.AutoSync.Always> / <xref:System.Data.Linq.Mapping.AutoSync.OnInsert> / <xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> .</span><span class="sxs-lookup"><span data-stu-id="c0745-178">In other cases, you should manually set <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` and <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> properties.</span></span>

## <a name="multiple-dataloadoptions"></a><span data-ttu-id="c0745-179">여러 DataLoadOptions</span><span class="sxs-lookup"><span data-stu-id="c0745-179">Multiple DataLoadOptions</span></span>

<span data-ttu-id="c0745-180">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-180">Q.</span></span> <span data-ttu-id="c0745-181">첫 번째 로드 옵션을 덮어쓰지 않고 다른 로드 옵션을 지정할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="c0745-181">Can I specify additional load options without overwriting the first?</span></span>

<span data-ttu-id="c0745-182">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-182">A.</span></span> <span data-ttu-id="c0745-183">예.</span><span class="sxs-lookup"><span data-stu-id="c0745-183">Yes.</span></span> <span data-ttu-id="c0745-184">다음 예제에서처럼 첫 번째 로드 옵션을 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-184">The first is not overwritten, as in the following example:</span></span>

```vb
Dim dlo As New DataLoadOptions()
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)
```

```csharp
DataLoadOptions dlo = new DataLoadOptions();
dlo.LoadWith<Order>(o => o.Customer);
dlo.LoadWith<Order>(o => o.OrderDetails);
```

## <a name="errors-using-sql-compact-35"></a><span data-ttu-id="c0745-185">SQL Compact 3.5 사용 오류</span><span class="sxs-lookup"><span data-stu-id="c0745-185">Errors Using SQL Compact 3.5</span></span>

<span data-ttu-id="c0745-186">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-186">Q.</span></span> <span data-ttu-id="c0745-187">SQL Server Compact 3.5 데이터베이스에서 테이블을 끌어올 때 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-187">I get an error when I drag tables out of a SQL Server Compact 3.5 database.</span></span>

<span data-ttu-id="c0745-188">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-188">A.</span></span> <span data-ttu-id="c0745-189">개체 관계형 디자이너는 SQL Server Compact 3.5를 지원 하지 않습니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0745-189">The Object Relational Designer does not support SQL Server Compact 3.5, although the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime does.</span></span> <span data-ttu-id="c0745-190">이 경우에는 고유 엔터티 클래스를 만들어 적절한 특성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-190">In this situation, you must create your own entity classes and add the appropriate attributes.</span></span>

## <a name="errors-in-inheritance-relationships"></a><span data-ttu-id="c0745-191">상속 관계 오류</span><span class="sxs-lookup"><span data-stu-id="c0745-191">Errors in Inheritance Relationships</span></span>

<span data-ttu-id="c0745-192">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-192">Q.</span></span> <span data-ttu-id="c0745-193">개체 관계형 디자이너에서 도구 상자 상속 셰이프를 사용 하 여 두 엔터티를 연결 했지만 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-193">I used the toolbox inheritance shape in the Object Relational Designer to connect two entities, but I get errors.</span></span>

<span data-ttu-id="c0745-194">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-194">A.</span></span> <span data-ttu-id="c0745-195">관계를 만드는 것만으로는 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-195">Creating the relationship is not enough.</span></span> <span data-ttu-id="c0745-196">판별자 열, 기본 클래스 판별자 값 및 파생 클래스 판별자 값 등의 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-196">You must provide information such as the discriminator column, base class discriminator value, and derived class discriminator value.</span></span>

## <a name="provider-model"></a><span data-ttu-id="c0745-197">공급자 모델</span><span class="sxs-lookup"><span data-stu-id="c0745-197">Provider Model</span></span>

<span data-ttu-id="c0745-198">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-198">Q.</span></span> <span data-ttu-id="c0745-199">사용할 수 있는 공용 공급자 모델이 있습니까?</span><span class="sxs-lookup"><span data-stu-id="c0745-199">Is a public provider model available?</span></span>

<span data-ttu-id="c0745-200">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-200">A.</span></span> <span data-ttu-id="c0745-201">아니요, 사용할 수 있는 공용 공급자 모델은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-201">No public provider model is available.</span></span> <span data-ttu-id="c0745-202">지금은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] SQL Server 및 SQL Server Compact 3.5만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-202">At this time, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports SQL Server and SQL Server Compact 3.5 only.</span></span>

## <a name="sql-injection-attacks"></a><span data-ttu-id="c0745-203">SQL 삽입 공격</span><span class="sxs-lookup"><span data-stu-id="c0745-203">SQL-Injection Attacks</span></span>

<span data-ttu-id="c0745-204">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-204">Q.</span></span> <span data-ttu-id="c0745-205">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 SQL 삽입 공격으로부터 어떻게 보호됩니까?</span><span class="sxs-lookup"><span data-stu-id="c0745-205">How is [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] protected from SQL-injection attacks?</span></span>

<span data-ttu-id="c0745-206">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-206">A.</span></span> <span data-ttu-id="c0745-207">사용자 입력을 연결하여 만든 기존 SQL 쿼리의 경우에는 SQL 삽입 공격이 상당히 큰 위협 요소였습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-207">SQL injection has been a significant risk for traditional SQL queries formed by concatenating user input.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="c0745-208">에서는 쿼리에 <xref:System.Data.SqlClient.SqlParameter>를 사용하여 이러한 삽입 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-208">avoids such injection by using <xref:System.Data.SqlClient.SqlParameter> in queries.</span></span> <span data-ttu-id="c0745-209">즉, 사용자 입력은 매개 변수 값으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-209">User input is turned into parameter values.</span></span> <span data-ttu-id="c0745-210">이 방법을 사용하면 사용자 입력을 통해 악의적인 명령이 사용되는 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-210">This approach prevents malicious commands from being used from customer input.</span></span>

## <a name="changing-read-only-flag-in-dbml-files"></a><span data-ttu-id="c0745-211">DBML 파일에서 읽기 전용 플래그 변경</span><span class="sxs-lookup"><span data-stu-id="c0745-211">Changing Read-only Flag in DBML Files</span></span>

<span data-ttu-id="c0745-212">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-212">Q.</span></span> <span data-ttu-id="c0745-213">DBML 파일에서 개체 모델을 만들 때 일부 속성의 setter를 어떻게 제거합니까?</span><span class="sxs-lookup"><span data-stu-id="c0745-213">How do I eliminate setters from some properties when I create an object model from a DBML file?</span></span>

<span data-ttu-id="c0745-214">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-214">A.</span></span> <span data-ttu-id="c0745-215">이와 같은 고급 시나리오에서는 다음과 같은 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c0745-215">Take the following steps for this advanced scenario:</span></span>

1. <span data-ttu-id="c0745-216">.dbml 파일에서 <xref:System.Data.Linq.ITable.IsReadOnly%2A> 플래그를 `True`로 변경하여 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-216">In the .dbml file, modify the property by changing the <xref:System.Data.Linq.ITable.IsReadOnly%2A> flag to `True`.</span></span>

2. <span data-ttu-id="c0745-217">부분 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-217">Add a partial class.</span></span> <span data-ttu-id="c0745-218">읽기 전용 멤버에 대해 매개 변수가 있는 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-218">Create a constructor with parameters for the read-only members.</span></span>

3. <span data-ttu-id="c0745-219">기본 <xref:System.Data.Linq.Mapping.UpdateCheck> 값(<xref:System.Data.Linq.Mapping.UpdateCheck.Never>)을 검토하여 애플리케이션에 사용할 수 있는 올바른 값인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-219">Review the default <xref:System.Data.Linq.Mapping.UpdateCheck> value (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) to determine whether that is the correct value for your application.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="c0745-220">Visual Studio에서 개체 관계형 디자이너를 사용 하는 경우 변경 내용을 덮어쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-220">If you are using the Object Relational Designer in Visual Studio, your changes might be overwritten.</span></span>

## <a name="aptca"></a><span data-ttu-id="c0745-221">APTCA</span><span class="sxs-lookup"><span data-stu-id="c0745-221">APTCA</span></span>

<span data-ttu-id="c0745-222">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-222">Q.</span></span> <span data-ttu-id="c0745-223">부분적으로 신뢰할 수 있는 코드에서 System.Data.Linq를 사용할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="c0745-223">Is System.Data.Linq marked for use by partially trusted code?</span></span>

<span data-ttu-id="c0745-224">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-224">A.</span></span> <span data-ttu-id="c0745-225">예, System.Data.Linq.dll 어셈블리는 특성으로 표시 된 .NET Framework 어셈블리 사이에 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-225">Yes, the System.Data.Linq.dll assembly is among those .NET Framework assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="c0745-226">이 표시가 없으면 .NET Framework의 어셈블리는 완전히 신뢰할 수 있는 코드 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-226">Without this marking, assemblies in the .NET Framework are intended for use only by fully trusted code.</span></span>

<span data-ttu-id="c0745-227">에서 부분적으로 신뢰할 수 있는 호출자를 허용 하는 주요 시나리오는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 웹 응용 프로그램에서 어셈블리에 액세스할 수 있도록 설정 하는 것입니다. 여기서 *트러스트* 구성은 Medium입니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-227">The principal scenario in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] for allowing partially trusted callers is to enable the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly to be accessed from Web applications, where the *trust* configuration is Medium.</span></span>

## <a name="mapping-data-from-multiple-tables"></a><span data-ttu-id="c0745-228">여러 테이블의 데이터 매핑</span><span class="sxs-lookup"><span data-stu-id="c0745-228">Mapping Data from Multiple Tables</span></span>

<span data-ttu-id="c0745-229">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-229">Q.</span></span> <span data-ttu-id="c0745-230">사용하는 엔터티의 데이터를 여러 테이블에서 가져오는데</span><span class="sxs-lookup"><span data-stu-id="c0745-230">The data in my entity comes from multiple tables.</span></span> <span data-ttu-id="c0745-231">이러한 데이터를 어떻게 매핑합니까?</span><span class="sxs-lookup"><span data-stu-id="c0745-231">How do I map it?</span></span>

<span data-ttu-id="c0745-232">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-232">A.</span></span> <span data-ttu-id="c0745-233">데이터베이스에 뷰를 만들어 엔터티를 해당 뷰에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-233">You can create a view in a database and map the entity to the view.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="c0745-234">에서는 테이블과 마찬가지로 뷰에 대해서도 동일한 SQL을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-234">generates the same SQL for views as it does for tables.</span></span>

> [!NOTE]
> <span data-ttu-id="c0745-235">그러나 이 시나리오에서는 뷰 사용이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-235">The use of views in this scenario has limitations.</span></span> <span data-ttu-id="c0745-236">이 방법은 기본 뷰에서 <xref:System.Data.Linq.Table%601>에 대해 수행되는 작업을 지원하는 경우에 가장 안전하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-236">This approach works most safely when the operations performed on <xref:System.Data.Linq.Table%601> are supported by the underlying view.</span></span> <span data-ttu-id="c0745-237">수행하려는 작업은 사용자 자신만이 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-237">Only you know which operations are intended.</span></span> <span data-ttu-id="c0745-238">예를 들어 대부분의 응용 프로그램은 읽기 전용 이며 다른 큰 숫자는 `Create` / `Update` / `Delete` 뷰에 대해 저장 프로시저만 사용 하 여 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-238">For example, most applications are read-only, and another sizeable number perform `Create`/`Update`/`Delete` operations only by using stored procedures against views.</span></span>

## <a name="connection-pooling"></a><span data-ttu-id="c0745-239">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="c0745-239">Connection Pooling</span></span>

<span data-ttu-id="c0745-240">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-240">Q.</span></span> <span data-ttu-id="c0745-241"><xref:System.Data.Linq.DataContext> 풀링에 도움이 되는 생성자가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="c0745-241">Is there a construct that can help with <xref:System.Data.Linq.DataContext> pooling?</span></span>

<span data-ttu-id="c0745-242">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-242">A.</span></span> <span data-ttu-id="c0745-243"><xref:System.Data.Linq.DataContext>의 인스턴스는 다시 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c0745-243">Do not try to reuse instances of <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="c0745-244">각 <xref:System.Data.Linq.DataContext>는 하나의 특정 편집/쿼리 세션에 대한 상태(ID 캐시 포함)를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-244">Each <xref:System.Data.Linq.DataContext> maintains state (including an identity cache) for one particular edit/query session.</span></span> <span data-ttu-id="c0745-245">데이터베이스의 현재 상태를 기반으로 새 인스턴스를 사용하려면 새 <xref:System.Data.Linq.DataContext>를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c0745-245">To obtain new instances based on the current state of the database, use a new <xref:System.Data.Linq.DataContext>.</span></span>

<span data-ttu-id="c0745-246">여전히 기본 ADO.NET 연결 풀링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-246">You can still use underlying ADO.NET connection pooling.</span></span> <span data-ttu-id="c0745-247">자세한 내용은 [SQL Server 연결 풀링(ADO.NET)](../../sql-server-connection-pooling.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0745-247">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../sql-server-connection-pooling.md).</span></span>

## <a name="second-datacontext-is-not-updated"></a><span data-ttu-id="c0745-248">두 번째 DataContext가 업데이트되지 않음</span><span class="sxs-lookup"><span data-stu-id="c0745-248">Second DataContext Is Not Updated</span></span>

<span data-ttu-id="c0745-249">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-249">Q.</span></span> <span data-ttu-id="c0745-250"><xref:System.Data.Linq.DataContext>의 인스턴스 하나를 사용하여 데이터베이스에 값을 저장했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-250">I used one instance of <xref:System.Data.Linq.DataContext> to store values in the database.</span></span> <span data-ttu-id="c0745-251">그런데 동일한 데이터베이스에 대한 두 번째 <xref:System.Data.Linq.DataContext>에 업데이트된 값이 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-251">However, a second <xref:System.Data.Linq.DataContext> on the same database does not reflect the updated values.</span></span> <span data-ttu-id="c0745-252">두 번째 <xref:System.Data.Linq.DataContext> 인스턴스가 캐시된 값을 반환하는 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-252">The second <xref:System.Data.Linq.DataContext> instance seems to return cached values.</span></span>

<span data-ttu-id="c0745-253">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-253">A.</span></span> <span data-ttu-id="c0745-254">이 동작은 의도된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-254">This behavior is by design.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="c0745-255">은 첫 번째 인스턴스와 동일한 인스턴스/값을 계속해서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-255">continues to return the same instances/values that you saw in the first instance.</span></span> <span data-ttu-id="c0745-256">데이터를 업데이트할 경우에는 낙관적 동시성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-256">When you make updates, you use optimistic concurrency.</span></span> <span data-ttu-id="c0745-257">이 경우 현재 데이터베이스 상태를 원래 데이터와 비교하여 데이터가 변경되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-257">The original data is used to check against the current database state to assert that it is in fact still unchanged.</span></span> <span data-ttu-id="c0745-258">데이터가 변경된 경우 충돌이 발생하고 애플리케이션에서는 이 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-258">If it has changed, a conflict occurs and your application must resolve it.</span></span> <span data-ttu-id="c0745-259">애플리케이션에서는 한 가지 옵션으로 원래 상태를 현재 데이터베이스 상태로 다시 설정한 후 업데이트를 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-259">One option of your application is to reset the original state to the current database state and to try the update again.</span></span> <span data-ttu-id="c0745-260">자세한 내용은 [방법: 변경 내용 충돌 관리](how-to-manage-change-conflicts.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0745-260">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>

<span data-ttu-id="c0745-261"><xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>를 false로 설정하여 캐싱 및 변경 추적을 해제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-261">You can also set <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to false, which turns off caching and change tracking.</span></span> <span data-ttu-id="c0745-262">이렇게 하면 쿼리할 때마다 최신 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-262">You can then retrieve the latest values every time that you query.</span></span>

## <a name="cannot-call-submitchanges-in-read-only-mode"></a><span data-ttu-id="c0745-263">읽기 전용 모드에서 SubmitChanges를 호출할 수 없음</span><span class="sxs-lookup"><span data-stu-id="c0745-263">Cannot Call SubmitChanges in Read-only Mode</span></span>

<span data-ttu-id="c0745-264">17.</span><span class="sxs-lookup"><span data-stu-id="c0745-264">Q.</span></span> <span data-ttu-id="c0745-265">읽기 전용 모드에서 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하려고 하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-265">When I try to call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> in read-only mode, I get an error.</span></span>

<span data-ttu-id="c0745-266">A.</span><span class="sxs-lookup"><span data-stu-id="c0745-266">A.</span></span> <span data-ttu-id="c0745-267">읽기 전용 모드에서는 컨텍스트에서 변경 내용을 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0745-267">Read-only mode turns off the ability of the context to track changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0745-268">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0745-268">See also</span></span>

- [<span data-ttu-id="c0745-269">참조</span><span class="sxs-lookup"><span data-stu-id="c0745-269">Reference</span></span>](reference.md)
- [<span data-ttu-id="c0745-270">문제 해결</span><span class="sxs-lookup"><span data-stu-id="c0745-270">Troubleshooting</span></span>](troubleshooting.md)
- [<span data-ttu-id="c0745-271">LINQ to SQL의 보안</span><span class="sxs-lookup"><span data-stu-id="c0745-271">Security in LINQ to SQL</span></span>](security-in-linq-to-sql.md)
