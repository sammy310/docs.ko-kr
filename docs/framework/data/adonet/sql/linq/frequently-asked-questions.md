---
title: 질문과 대답
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
ms.openlocfilehash: 3cc879e97438138554f1d39cf588e01bfbba28a6
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634705"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="44c11-102">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="44c11-102">Frequently Asked Questions</span></span>

<span data-ttu-id="44c11-103">다음 섹션에서는 LINQ를 구현할 때 발생할 수 있는 몇 가지 일반적인 문제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-103">The following sections answer some common issues that you might encounter when you implement LINQ.</span></span>

<span data-ttu-id="44c11-104">[문제 해결](troubleshooting.md)에서는 추가 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-104">Additional issues are addressed in [Troubleshooting](troubleshooting.md).</span></span>

## <a name="cannot-connect"></a><span data-ttu-id="44c11-105">연결할 수 없음</span><span class="sxs-lookup"><span data-stu-id="44c11-105">Cannot Connect</span></span>

<span data-ttu-id="44c11-106">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-106">Q.</span></span> <span data-ttu-id="44c11-107">데이터베이스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-107">I cannot connect to my database.</span></span>

<span data-ttu-id="44c11-108">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-108">A.</span></span> <span data-ttu-id="44c11-109">연결 문자열이 올바르고 SQL Server 인스턴스가 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-109">Make sure your connection string is correct and that your SQL Server instance is running.</span></span> <span data-ttu-id="44c11-110">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하려면 명명된 파이프 프로토콜도 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-110">Note also that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requires the Named Pipes protocol to be enabled.</span></span> <span data-ttu-id="44c11-111">자세한 내용은 [연습 별 학습](learning-by-walkthroughs.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44c11-111">For more information, see [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

## <a name="changes-to-database-lost"></a><span data-ttu-id="44c11-112">데이터베이스 변경 내용 손실</span><span class="sxs-lookup"><span data-stu-id="44c11-112">Changes to Database Lost</span></span>

<span data-ttu-id="44c11-113">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-113">Q.</span></span> <span data-ttu-id="44c11-114">데이터베이스의 데이터를 변경했는데 애플리케이션을 다시 실행했더니 변경 내용이 없어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-114">I made a change to data in the database, but when I reran my application, the change was no longer there.</span></span>

<span data-ttu-id="44c11-115">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-115">A.</span></span> <span data-ttu-id="44c11-116"><xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하여 결과를 데이터베이스에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-116">Make sure that you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> to save results to the database.</span></span>

## <a name="database-connection-open-how-long"></a><span data-ttu-id="44c11-117">데이터베이스 연결: 연결 시간</span><span class="sxs-lookup"><span data-stu-id="44c11-117">Database Connection: Open How Long?</span></span>

<span data-ttu-id="44c11-118">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-118">Q.</span></span> <span data-ttu-id="44c11-119">데이터베이스는 얼마 동안 연결된 상태로 유지됩니까?</span><span class="sxs-lookup"><span data-stu-id="44c11-119">How long does my database connection remain open?</span></span>

<span data-ttu-id="44c11-120">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-120">A.</span></span> <span data-ttu-id="44c11-121">일반적으로 연결은 쿼리 결과를 사용할 때까지 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-121">A connection typically remains open until you consume the query results.</span></span> <span data-ttu-id="44c11-122">모든 결과를 처리하는 데 시간이 많이 걸릴 것으로 예상되고 결과를 캐시해도 상관 없다면 쿼리에 <xref:System.Linq.Enumerable.ToList%2A> ¦ Àû ëÇÏ Ê Ã À.</span><span class="sxs-lookup"><span data-stu-id="44c11-122">If you expect to take time to process all the results and are not opposed to caching the results, apply <xref:System.Linq.Enumerable.ToList%2A> to the query.</span></span> <span data-ttu-id="44c11-123">각 개체를 한 번만 처리하는 일반적인 시나리오에서는 `DataReader` 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 모두에서 스트리밍 모델을 사용하는 것이 더 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-123">In common scenarios where each object is processed only one time, the streaming model is superior in both `DataReader` and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

<span data-ttu-id="44c11-124">세부적인 연결 사용은 다음에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-124">The exact details of connection usage depend on the following:</span></span>

- <span data-ttu-id="44c11-125">연결 개체를 사용하여 <xref:System.Data.Linq.DataContext>를 만든 경우의 연결 상태</span><span class="sxs-lookup"><span data-stu-id="44c11-125">Connection status if the <xref:System.Data.Linq.DataContext> is constructed with a connection object.</span></span>

- <span data-ttu-id="44c11-126">연결 문자열 설정(예: MARS(Multiple Active Result Sets) 사용).</span><span class="sxs-lookup"><span data-stu-id="44c11-126">Connection string settings (for example, enabling Multiple Active Result Sets (MARS).</span></span> <span data-ttu-id="44c11-127">자세한 내용은 [MARS(여러 활성 결과 집합)](../multiple-active-result-sets-mars.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44c11-127">For more information, see [Multiple Active Result Sets (MARS)](../multiple-active-result-sets-mars.md).</span></span>

## <a name="updating-without-querying"></a><span data-ttu-id="44c11-128">쿼리하지 않고 업데이트</span><span class="sxs-lookup"><span data-stu-id="44c11-128">Updating Without Querying</span></span>

<span data-ttu-id="44c11-129">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-129">Q.</span></span> <span data-ttu-id="44c11-130">데이터베이스를 먼저 쿼리하지 않고 테이블 데이터를 업데이트할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="44c11-130">Can I update table data without first querying the database?</span></span>

<span data-ttu-id="44c11-131">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-131">A.</span></span> <span data-ttu-id="44c11-132">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에는 설정 기반의 업데이트 명령이 없지만 다음 기술 중 하나를 사용하여 쿼리 없이 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-132">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not have set-based update commands, you can use either of the following techniques to update without first querying:</span></span>

- <span data-ttu-id="44c11-133"><xref:System.Data.Linq.DataContext.ExecuteCommand%2A>를 사용하여 SQL 코드를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-133">Use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to send SQL code.</span></span>

- <span data-ttu-id="44c11-134">개체의 새 인스턴스를 만든 후 업데이트에 영향을 주는 현재 값(필드)을 모두 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-134">Create a new instance of the object and initialize all the current values (fields) that affect the update.</span></span> <span data-ttu-id="44c11-135">그런 다음 <xref:System.Data.Linq.DataContext>를 사용하여 개체를 <xref:System.Data.Linq.Table%601.Attach%2A>에 연결하고 변경할 필드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-135">Then attach the object to the <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.Table%601.Attach%2A> and modify the field you want to change.</span></span>

## <a name="unexpected-query-results"></a><span data-ttu-id="44c11-136">예기치 않은 쿼리 결과</span><span class="sxs-lookup"><span data-stu-id="44c11-136">Unexpected Query Results</span></span>

<span data-ttu-id="44c11-137">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-137">Q.</span></span> <span data-ttu-id="44c11-138">쿼리가 예기치 않은 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-138">My query is returning unexpected results.</span></span> <span data-ttu-id="44c11-139">무슨 문제가 있는지 어떻게 확인합니까?</span><span class="sxs-lookup"><span data-stu-id="44c11-139">How can I inspect what is occurring?</span></span>

<span data-ttu-id="44c11-140">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-140">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="44c11-141">에는 생성된 SQL 코드를 검사할 수 있는 도구가 여러 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-141">provides several tools for inspecting the SQL code it generates.</span></span> <span data-ttu-id="44c11-142">그 중에서도 <xref:System.Data.Linq.DataContext.Log%2A>가 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-142">One of the most important is <xref:System.Data.Linq.DataContext.Log%2A>.</span></span> <span data-ttu-id="44c11-143">자세한 내용은 [디버깅 지원](debugging-support.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44c11-143">For more information, see [Debugging Support](debugging-support.md).</span></span>

## <a name="unexpected-stored-procedure-results"></a><span data-ttu-id="44c11-144">예기치 않은 저장 프로시저 결과</span><span class="sxs-lookup"><span data-stu-id="44c11-144">Unexpected Stored Procedure Results</span></span>

<span data-ttu-id="44c11-145">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-145">Q.</span></span> <span data-ttu-id="44c11-146">`MAX()`를 사용하여 반환 값을 계산하는 저장 프로시저를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-146">I have a stored procedure whose return value is calculated by `MAX()`.</span></span> <span data-ttu-id="44c11-147">저장 프로시저를 O/R 디자이너 화면으로 끌면 반환 값이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-147">When I drag the stored procedure to the O/R Designer surface, the return value is not correct.</span></span>

<span data-ttu-id="44c11-148">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-148">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="44c11-149">에서는 다음과 같은 두 가지 방법으로 데이터베이스에서 생성된 값을 저장 프로시저를 통해 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-149">provides two ways to return database-generated values by way of stored procedures:</span></span>

- <span data-ttu-id="44c11-150">출력 결과에 이름을 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="44c11-150">By naming the output result.</span></span>

- <span data-ttu-id="44c11-151">출력 매개 변수를 명시적으로 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="44c11-151">By explicitly specifying an output parameter.</span></span>

<span data-ttu-id="44c11-152">다음은 잘못된 출력의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-152">The following is an example of incorrect output.</span></span> <span data-ttu-id="44c11-153">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 결과를 매핑할 수 없기 때문에 항상 0을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-153">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot map the results, it always returns 0:</span></span>

```sql
create procedure proc2

as

begin

select max(i) from t where name like 'hello'

end
```

<span data-ttu-id="44c11-154">다음은 출력 매개 변수를 사용하여 얻은 올바른 출력의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-154">The following is an example of correct output by using an output parameter:</span></span>

```sql
create procedure proc2

@result int OUTPUT

as

select @result = MAX(i) from t where name like 'hello'

go
```

<span data-ttu-id="44c11-155">다음은 출력 결과에 이름을 지정하여 얻은 올바른 출력의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-155">The following is an example of correct output by naming the output result:</span></span>

```sql
create procedure proc2

as

begin

select nax(i) AS MaxResult from t where name like 'hello'

end
```

<span data-ttu-id="44c11-156">자세한 내용은 [저장 프로시저를 사용 하 여 작업 사용자 지정](customizing-operations-by-using-stored-procedures.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44c11-156">For more information, see [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md).</span></span>

## <a name="serialization-errors"></a><span data-ttu-id="44c11-157">Serialization 오류</span><span class="sxs-lookup"><span data-stu-id="44c11-157">Serialization Errors</span></span>

<span data-ttu-id="44c11-158">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-158">Q.</span></span> <span data-ttu-id="44c11-159">Serialize 하려고 하면 다음과 같은 오류가 발생 합니다. "Type ' ChangeTracker + StandardChangeTracker ' ... serializable로 표시 되어 있지 않습니다. "</span><span class="sxs-lookup"><span data-stu-id="44c11-159">When I try to serialize, I get the following error: "Type 'System.Data.Linq.ChangeTracker+StandardChangeTracker' ... is not marked as serializable."</span></span>

<span data-ttu-id="44c11-160">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-160">A.</span></span> <span data-ttu-id="44c11-161">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 코드 생성은 <xref:System.Runtime.Serialization.DataContractSerializer> serialization을 지원하지만</span><span class="sxs-lookup"><span data-stu-id="44c11-161">Code generation in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports <xref:System.Runtime.Serialization.DataContractSerializer> serialization.</span></span> <span data-ttu-id="44c11-162"><xref:System.Xml.Serialization.XmlSerializer> 또는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-162">It does not support <xref:System.Xml.Serialization.XmlSerializer> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="44c11-163">자세한 내용은 [Serialization](serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44c11-163">For more information, see [Serialization](serialization.md).</span></span>

## <a name="multiple-dbml-files"></a><span data-ttu-id="44c11-164">여러 DBML 파일</span><span class="sxs-lookup"><span data-stu-id="44c11-164">Multiple DBML Files</span></span>

<span data-ttu-id="44c11-165">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-165">Q.</span></span> <span data-ttu-id="44c11-166">여러 DBML 파일에서 일부 테이블을 공유할 경우 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-166">When I have multiple DBML files that share some tables in common, I get a compiler error.</span></span>

<span data-ttu-id="44c11-167">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-167">A.</span></span> <span data-ttu-id="44c11-168">개체 관계형 디자이너의 **컨텍스트 네임 스페이스** 및 **엔터티 네임 스페이스** 속성을 각 DBML 파일에 대 한 고유 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-168">Set the **Context Namespace** and **Entity Namespace** properties from the Object Relational Designer to a distinct value for each DBML file.</span></span> <span data-ttu-id="44c11-169">이렇게 하면 이름/네임스페이스 충돌이 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-169">This approach eliminates the name/namespace collision.</span></span>

## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a><span data-ttu-id="44c11-170">삽입 또는 업데이트 시 데이터베이스에서 생성된 값을 명시적으로 설정해야 하는 문제 방지</span><span class="sxs-lookup"><span data-stu-id="44c11-170">Avoiding Explicit Setting of Database-Generated Values on Insert or Update</span></span>

<span data-ttu-id="44c11-171">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-171">Q.</span></span> <span data-ttu-id="44c11-172">데이터베이스 테이블에 SQL `DateCreated`를 기본값으로 사용하는 `Getdate()` 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-172">I have a database table with a `DateCreated` column that defaults to SQL `Getdate()`.</span></span> <span data-ttu-id="44c11-173">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하여 새 레코드를 삽입하려고 하면 값이 `NULL`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-173">When I try to insert a new record by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the value gets set to `NULL`.</span></span> <span data-ttu-id="44c11-174">데이터베이스의 기본값이 설정되어야 하지 않나요?</span><span class="sxs-lookup"><span data-stu-id="44c11-174">I would expect it to be set to the database default.</span></span>

<span data-ttu-id="44c11-175">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-175">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="44c11-176">은 ID(자동 증분)와 rowguidcol(데이터베이스에서 생성된 GUID) 및 타임스탬프 열에 대해서만 이와 같이 기본값을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-176">handles this situation automatically for identity (auto-increment) and rowguidcol (database-generated GUID) and timestamp columns.</span></span> <span data-ttu-id="44c11-177">다른 경우에는 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true`를 수동으로 설정 하 고 =<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>속성을 <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-177">In other cases, you should manually set <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` and <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> properties.</span></span>

## <a name="multiple-dataloadoptions"></a><span data-ttu-id="44c11-178">여러 DataLoadOptions</span><span class="sxs-lookup"><span data-stu-id="44c11-178">Multiple DataLoadOptions</span></span>

<span data-ttu-id="44c11-179">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-179">Q.</span></span> <span data-ttu-id="44c11-180">첫 번째 로드 옵션을 덮어쓰지 않고 다른 로드 옵션을 지정할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="44c11-180">Can I specify additional load options without overwriting the first?</span></span>

<span data-ttu-id="44c11-181">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-181">A.</span></span> <span data-ttu-id="44c11-182">예,</span><span class="sxs-lookup"><span data-stu-id="44c11-182">Yes.</span></span> <span data-ttu-id="44c11-183">다음 예제에서처럼 첫 번째 로드 옵션을 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-183">The first is not overwritten, as in the following example:</span></span>

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

## <a name="errors-using-sql-compact-35"></a><span data-ttu-id="44c11-184">SQL Compact 3.5 사용 오류</span><span class="sxs-lookup"><span data-stu-id="44c11-184">Errors Using SQL Compact 3.5</span></span>

<span data-ttu-id="44c11-185">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-185">Q.</span></span> <span data-ttu-id="44c11-186">SQL Server Compact 3.5 데이터베이스에서 테이블을 끌어올 때 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-186">I get an error when I drag tables out of a SQL Server Compact 3.5 database.</span></span>

<span data-ttu-id="44c11-187">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-187">A.</span></span> <span data-ttu-id="44c11-188">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 런타임에서는 개체 관계형 디자이너 SQL Server Compact 3.5를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-188">The Object Relational Designer does not support SQL Server Compact 3.5, although the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime does.</span></span> <span data-ttu-id="44c11-189">이 경우에는 고유 엔터티 클래스를 만들어 적절한 특성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-189">In this situation, you must create your own entity classes and add the appropriate attributes.</span></span>

## <a name="errors-in-inheritance-relationships"></a><span data-ttu-id="44c11-190">상속 관계 오류</span><span class="sxs-lookup"><span data-stu-id="44c11-190">Errors in Inheritance Relationships</span></span>

<span data-ttu-id="44c11-191">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-191">Q.</span></span> <span data-ttu-id="44c11-192">개체 관계형 디자이너에서 도구 상자 상속 셰이프를 사용 하 여 두 엔터티를 연결 했지만 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-192">I used the toolbox inheritance shape in the Object Relational Designer to connect two entities, but I get errors.</span></span>

<span data-ttu-id="44c11-193">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-193">A.</span></span> <span data-ttu-id="44c11-194">관계를 만드는 것만으로는 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-194">Creating the relationship is not enough.</span></span> <span data-ttu-id="44c11-195">판별자 열, 기본 클래스 판별자 값 및 파생 클래스 판별자 값 등의 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-195">You must provide information such as the discriminator column, base class discriminator value, and derived class discriminator value.</span></span>

## <a name="provider-model"></a><span data-ttu-id="44c11-196">공급자 모델</span><span class="sxs-lookup"><span data-stu-id="44c11-196">Provider Model</span></span>

<span data-ttu-id="44c11-197">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-197">Q.</span></span> <span data-ttu-id="44c11-198">사용할 수 있는 공용 공급자 모델이 있습니까?</span><span class="sxs-lookup"><span data-stu-id="44c11-198">Is a public provider model available?</span></span>

<span data-ttu-id="44c11-199">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-199">A.</span></span> <span data-ttu-id="44c11-200">아니요, 사용할 수 있는 공용 공급자 모델은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-200">No public provider model is available.</span></span> <span data-ttu-id="44c11-201">이번에는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] SQL Server 및 SQL Server Compact 3.5만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-201">At this time, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports SQL Server and SQL Server Compact 3.5 only.</span></span>

## <a name="sql-injection-attacks"></a><span data-ttu-id="44c11-202">SQL 삽입 공격</span><span class="sxs-lookup"><span data-stu-id="44c11-202">SQL-Injection Attacks</span></span>

<span data-ttu-id="44c11-203">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-203">Q.</span></span> <span data-ttu-id="44c11-204">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 SQL 삽입 공격으로부터 어떻게 보호됩니까?</span><span class="sxs-lookup"><span data-stu-id="44c11-204">How is [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] protected from SQL-injection attacks?</span></span>

<span data-ttu-id="44c11-205">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-205">A.</span></span> <span data-ttu-id="44c11-206">사용자 입력을 연결하여 만든 기존 SQL 쿼리의 경우에는 SQL 삽입 공격이 상당히 큰 위협 요소였습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-206">SQL injection has been a significant risk for traditional SQL queries formed by concatenating user input.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="44c11-207">에서는 쿼리에 <xref:System.Data.SqlClient.SqlParameter>를 사용하여 이러한 삽입 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-207">avoids such injection by using <xref:System.Data.SqlClient.SqlParameter> in queries.</span></span> <span data-ttu-id="44c11-208">즉, 사용자 입력은 매개 변수 값으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-208">User input is turned into parameter values.</span></span> <span data-ttu-id="44c11-209">이 방법을 사용하면 사용자 입력을 통해 악의적인 명령이 사용되는 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-209">This approach prevents malicious commands from being used from customer input.</span></span>

## <a name="changing-read-only-flag-in-dbml-files"></a><span data-ttu-id="44c11-210">DBML 파일에서 읽기 전용 플래그 변경</span><span class="sxs-lookup"><span data-stu-id="44c11-210">Changing Read-only Flag in DBML Files</span></span>

<span data-ttu-id="44c11-211">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-211">Q.</span></span> <span data-ttu-id="44c11-212">DBML 파일에서 개체 모델을 만들 때 일부 속성의 setter를 어떻게 제거합니까?</span><span class="sxs-lookup"><span data-stu-id="44c11-212">How do I eliminate setters from some properties when I create an object model from a DBML file?</span></span>

<span data-ttu-id="44c11-213">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-213">A.</span></span> <span data-ttu-id="44c11-214">이와 같은 고급 시나리오에서는 다음과 같은 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="44c11-214">Take the following steps for this advanced scenario:</span></span>

1. <span data-ttu-id="44c11-215">.dbml 파일에서 <xref:System.Data.Linq.ITable.IsReadOnly%2A> 플래그를 `True`로 변경하여 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-215">In the .dbml file, modify the property by changing the <xref:System.Data.Linq.ITable.IsReadOnly%2A> flag to `True`.</span></span>

2. <span data-ttu-id="44c11-216">부분 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-216">Add a partial class.</span></span> <span data-ttu-id="44c11-217">읽기 전용 멤버에 대해 매개 변수가 있는 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-217">Create a constructor with parameters for the read-only members.</span></span>

3. <span data-ttu-id="44c11-218">기본 <xref:System.Data.Linq.Mapping.UpdateCheck> 값(<xref:System.Data.Linq.Mapping.UpdateCheck.Never>)을 검토하여 애플리케이션에 사용할 수 있는 올바른 값인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-218">Review the default <xref:System.Data.Linq.Mapping.UpdateCheck> value (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) to determine whether that is the correct value for your application.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="44c11-219">Visual Studio에서 개체 관계형 디자이너를 사용 하는 경우 변경 내용을 덮어쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-219">If you are using the Object Relational Designer in Visual Studio, your changes might be overwritten.</span></span>

## <a name="aptca"></a><span data-ttu-id="44c11-220">APTCA</span><span class="sxs-lookup"><span data-stu-id="44c11-220">APTCA</span></span>

<span data-ttu-id="44c11-221">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-221">Q.</span></span> <span data-ttu-id="44c11-222">부분적으로 신뢰할 수 있는 코드에서 System.Data.Linq를 사용할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="44c11-222">Is System.Data.Linq marked for use by partially trusted code?</span></span>

<span data-ttu-id="44c11-223">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-223">A.</span></span> <span data-ttu-id="44c11-224">예, System.object는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성으로 표시 된 .NET Framework 어셈블리 사이에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-224">Yes, the System.Data.Linq.dll assembly is among those .NET Framework assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="44c11-225">이 표시가 없으면 .NET Framework의 어셈블리는 완전히 신뢰할 수 있는 코드 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-225">Without this marking, assemblies in the .NET Framework are intended for use only by fully trusted code.</span></span>

<span data-ttu-id="44c11-226">부분적으로 신뢰할 수 있는 호출자를 허용 하기 위한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 주요 시나리오는 웹 응용 프로그램에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 어셈블리에 액세스할 수 있도록 하는 것입니다. 여기서 *트러스트* 구성은 Medium입니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-226">The principal scenario in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] for allowing partially trusted callers is to enable the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly to be accessed from Web applications, where the *trust* configuration is Medium.</span></span>

## <a name="mapping-data-from-multiple-tables"></a><span data-ttu-id="44c11-227">여러 테이블의 데이터 매핑</span><span class="sxs-lookup"><span data-stu-id="44c11-227">Mapping Data from Multiple Tables</span></span>

<span data-ttu-id="44c11-228">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-228">Q.</span></span> <span data-ttu-id="44c11-229">사용하는 엔터티의 데이터를 여러 테이블에서 가져오는데</span><span class="sxs-lookup"><span data-stu-id="44c11-229">The data in my entity comes from multiple tables.</span></span> <span data-ttu-id="44c11-230">이러한 데이터를 어떻게 매핑합니까?</span><span class="sxs-lookup"><span data-stu-id="44c11-230">How do I map it?</span></span>

<span data-ttu-id="44c11-231">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-231">A.</span></span> <span data-ttu-id="44c11-232">데이터베이스에 뷰를 만들어 엔터티를 해당 뷰에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-232">You can create a view in a database and map the entity to the view.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="44c11-233">에서는 테이블과 마찬가지로 뷰에 대해서도 동일한 SQL을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-233">generates the same SQL for views as it does for tables.</span></span>

> [!NOTE]
> <span data-ttu-id="44c11-234">그러나 이 시나리오에서는 뷰 사용이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-234">The use of views in this scenario has limitations.</span></span> <span data-ttu-id="44c11-235">이 방법은 기본 뷰에서 <xref:System.Data.Linq.Table%601>에 대해 수행되는 작업을 지원하는 경우에 가장 안전하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-235">This approach works most safely when the operations performed on <xref:System.Data.Linq.Table%601> are supported by the underlying view.</span></span> <span data-ttu-id="44c11-236">수행하려는 작업은 사용자 자신만이 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-236">Only you know which operations are intended.</span></span> <span data-ttu-id="44c11-237">예를 들어 대부분의 응용 프로그램은 읽기 전용 이며 다른 큰 숫자는 뷰에 대해 저장 프로시저만 사용 하 여 `Delete` 작업을 /`Update`/`Create`수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-237">For example, most applications are read-only, and another sizeable number perform `Create`/`Update`/`Delete` operations only by using stored procedures against views.</span></span>

## <a name="connection-pooling"></a><span data-ttu-id="44c11-238">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="44c11-238">Connection Pooling</span></span>

<span data-ttu-id="44c11-239">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-239">Q.</span></span> <span data-ttu-id="44c11-240"><xref:System.Data.Linq.DataContext> 풀링에 도움이 되는 생성자가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="44c11-240">Is there a construct that can help with <xref:System.Data.Linq.DataContext> pooling?</span></span>

<span data-ttu-id="44c11-241">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-241">A.</span></span> <span data-ttu-id="44c11-242"><xref:System.Data.Linq.DataContext>의 인스턴스는 다시 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="44c11-242">Do not try to reuse instances of <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="44c11-243">각 <xref:System.Data.Linq.DataContext>는 하나의 특정 편집/쿼리 세션에 대한 상태(ID 캐시 포함)를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-243">Each <xref:System.Data.Linq.DataContext> maintains state (including an identity cache) for one particular edit/query session.</span></span> <span data-ttu-id="44c11-244">데이터베이스의 현재 상태를 기반으로 새 인스턴스를 사용하려면 새 <xref:System.Data.Linq.DataContext>를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="44c11-244">To obtain new instances based on the current state of the database, use a new <xref:System.Data.Linq.DataContext>.</span></span>

<span data-ttu-id="44c11-245">여전히 기본 ADO.NET 연결 풀링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-245">You can still use underlying ADO.NET connection pooling.</span></span> <span data-ttu-id="44c11-246">자세한 내용은 [SQL Server 연결 풀링(ADO.NET)](../../sql-server-connection-pooling.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44c11-246">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../sql-server-connection-pooling.md).</span></span>

## <a name="second-datacontext-is-not-updated"></a><span data-ttu-id="44c11-247">두 번째 DataContext가 업데이트되지 않음</span><span class="sxs-lookup"><span data-stu-id="44c11-247">Second DataContext Is Not Updated</span></span>

<span data-ttu-id="44c11-248">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-248">Q.</span></span> <span data-ttu-id="44c11-249"><xref:System.Data.Linq.DataContext>의 인스턴스 하나를 사용하여 데이터베이스에 값을 저장했습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-249">I used one instance of <xref:System.Data.Linq.DataContext> to store values in the database.</span></span> <span data-ttu-id="44c11-250">그런데 동일한 데이터베이스에 대한 두 번째 <xref:System.Data.Linq.DataContext>에 업데이트된 값이 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-250">However, a second <xref:System.Data.Linq.DataContext> on the same database does not reflect the updated values.</span></span> <span data-ttu-id="44c11-251">두 번째 <xref:System.Data.Linq.DataContext> 인스턴스가 캐시된 값을 반환하는 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-251">The second <xref:System.Data.Linq.DataContext> instance seems to return cached values.</span></span>

<span data-ttu-id="44c11-252">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-252">A.</span></span> <span data-ttu-id="44c11-253">이 동작은 설계 시 의도된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-253">This behavior is by design.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="44c11-254">은 첫 번째 인스턴스와 동일한 인스턴스/값을 계속해서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-254">continues to return the same instances/values that you saw in the first instance.</span></span> <span data-ttu-id="44c11-255">데이터를 업데이트할 경우에는 낙관적 동시성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-255">When you make updates, you use optimistic concurrency.</span></span> <span data-ttu-id="44c11-256">이 경우 현재 데이터베이스 상태를 원래 데이터와 비교하여 데이터가 변경되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-256">The original data is used to check against the current database state to assert that it is in fact still unchanged.</span></span> <span data-ttu-id="44c11-257">데이터가 변경된 경우 충돌이 발생하고 애플리케이션에서는 이 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-257">If it has changed, a conflict occurs and your application must resolve it.</span></span> <span data-ttu-id="44c11-258">애플리케이션에서는 한 가지 옵션으로 원래 상태를 현재 데이터베이스 상태로 다시 설정한 후 업데이트를 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-258">One option of your application is to reset the original state to the current database state and to try the update again.</span></span> <span data-ttu-id="44c11-259">자세한 내용은 [방법: 변경 내용 충돌 관리](how-to-manage-change-conflicts.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44c11-259">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>

<span data-ttu-id="44c11-260"><xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>를 false로 설정하여 캐싱 및 변경 추적을 해제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-260">You can also set <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to false, which turns off caching and change tracking.</span></span> <span data-ttu-id="44c11-261">이렇게 하면 쿼리할 때마다 최신 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-261">You can then retrieve the latest values every time that you query.</span></span>

## <a name="cannot-call-submitchanges-in-read-only-mode"></a><span data-ttu-id="44c11-262">읽기 전용 모드에서 SubmitChanges를 호출할 수 없음</span><span class="sxs-lookup"><span data-stu-id="44c11-262">Cannot Call SubmitChanges in Read-only Mode</span></span>

<span data-ttu-id="44c11-263">Q.</span><span class="sxs-lookup"><span data-stu-id="44c11-263">Q.</span></span> <span data-ttu-id="44c11-264">읽기 전용 모드에서 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하려고 하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-264">When I try to call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> in read-only mode, I get an error.</span></span>

<span data-ttu-id="44c11-265">대답:</span><span class="sxs-lookup"><span data-stu-id="44c11-265">A.</span></span> <span data-ttu-id="44c11-266">읽기 전용 모드에서는 컨텍스트에서 변경 내용을 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44c11-266">Read-only mode turns off the ability of the context to track changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="44c11-267">참조</span><span class="sxs-lookup"><span data-stu-id="44c11-267">See also</span></span>

- [<span data-ttu-id="44c11-268">참조</span><span class="sxs-lookup"><span data-stu-id="44c11-268">Reference</span></span>](reference.md)
- [<span data-ttu-id="44c11-269">문제 해결</span><span class="sxs-lookup"><span data-stu-id="44c11-269">Troubleshooting</span></span>](troubleshooting.md)
- [<span data-ttu-id="44c11-270">LINQ to SQL의 보안</span><span class="sxs-lookup"><span data-stu-id="44c11-270">Security in LINQ to SQL</span></span>](security-in-linq-to-sql.md)
