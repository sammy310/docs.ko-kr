---
description: '자세한 정보: 낙관적 동시성: 개요'
title: '낙관적 동시성: 개요'
ms.date: 03/30/2017
ms.assetid: c2e38512-d0c8-4807-b30a-cb7e30338694
ms.openlocfilehash: fbf6714851dbb31982a110749c55e5fad7aa2206
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695426"
---
# <a name="optimistic-concurrency-overview"></a><span data-ttu-id="934bc-103">낙관적 동시성: 개요</span><span class="sxs-lookup"><span data-stu-id="934bc-103">Optimistic Concurrency: Overview</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="934bc-104">은 낙관적 동시성 제어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-104">supports optimistic concurrency control.</span></span> <span data-ttu-id="934bc-105">다음 표에서는 설명서에서 낙관적 동시성에 적용 되는 용어에 대해 설명 합니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="934bc-105">The following table describes terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation:</span></span>  
  
|<span data-ttu-id="934bc-106">사용 약관</span><span class="sxs-lookup"><span data-stu-id="934bc-106">Terms</span></span>|<span data-ttu-id="934bc-107">설명</span><span class="sxs-lookup"><span data-stu-id="934bc-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="934bc-108">동시성</span><span class="sxs-lookup"><span data-stu-id="934bc-108">concurrency</span></span>|<span data-ttu-id="934bc-109">둘 이상의 사용자가 동일한 데이터베이스 행을 동시에 업데이트하려는 상황입니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-109">The situation in which two or more users at the same time try to update the same database row.</span></span>|  
|<span data-ttu-id="934bc-110">동시성 충돌(concurrency conflict)</span><span class="sxs-lookup"><span data-stu-id="934bc-110">concurrency conflict</span></span>|<span data-ttu-id="934bc-111">둘 이상의 사용자가 한 행의 하나 이상의 열에 충돌하는 값을 동시에 전송하려는 상황입니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-111">The situation in which two or more users at the same time try to submit conflicting values to one or more columns of a row.</span></span>|  
|<span data-ttu-id="934bc-112">동시성 제어</span><span class="sxs-lookup"><span data-stu-id="934bc-112">concurrency control</span></span>|<span data-ttu-id="934bc-113">동시성 충돌을 해결하는 데 사용되는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-113">The technique used to resolve concurrency conflicts.</span></span>|  
|<span data-ttu-id="934bc-114">낙관적 동시성 제어</span><span class="sxs-lookup"><span data-stu-id="934bc-114">optimistic concurrency control</span></span>|<span data-ttu-id="934bc-115">변경 내용이 전송되도록 허용하기 전에 다른 트랜잭션에서 행의 값을 변경했는지 조사하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-115">The technique that first investigates whether other transactions have changed values in a row before permitting changes to be submitted.</span></span><br /><br /> <span data-ttu-id="934bc-116">*비관적 동시성 제어* 와 달리 동시성 충돌을 방지 하기 위해 레코드를 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-116">Contrast with *pessimistic concurrency control*, which locks the record to avoid concurrency conflicts.</span></span><br /><br /> <span data-ttu-id="934bc-117">*낙관적* 제어는 한 트랜잭션이 다른 트랜잭션으로 간섭 하는 가능성을 고려 하지 않기 때문에 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-117">*Optimistic* control is so termed because it considers the chances of one transaction interfering with another to be unlikely.</span></span>|  
|<span data-ttu-id="934bc-118">충돌 해결</span><span class="sxs-lookup"><span data-stu-id="934bc-118">conflict resolution</span></span>|<span data-ttu-id="934bc-119">데이터베이스를 다시 쿼리한 다음 차이를 조정하여 충돌하는 항목을 새로 고치는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-119">The process of refreshing a conflicting item by querying the database again and then reconciling differences.</span></span><br /><br /> <span data-ttu-id="934bc-120">개체를 새로 고칠 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 변경 추적기는 다음 데이터를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-120">When an object is refreshed, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] change tracker holds the following data:</span></span><br /><br /> <span data-ttu-id="934bc-121">-원래 데이터베이스에서 가져온 값으로 업데이트 확인에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-121">-   The values originally taken from the database and used for the update check.</span></span><br /><span data-ttu-id="934bc-122">-후속 쿼리의 새 데이터베이스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-122">-   The new database values from the subsequent query.</span></span><br /><br /> <span data-ttu-id="934bc-123">그런 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 개체가 충돌하는지 여부(즉, 해당 멤버 값 중 하나 이상이 변경되었는지 여부)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-123">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] then determines whether the object is in conflict (that is, whether one or more of its member values has changed).</span></span> <span data-ttu-id="934bc-124">개체가 충돌할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 해당 멤버 중에서 충돌하는 멤버를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-124">If the object is in conflict, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] next determines which of its members are in conflict.</span></span><br /><br /> <span data-ttu-id="934bc-125">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]이 검색한 모든 멤버 충돌은 충돌 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-125">Any member conflict that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] discovers is added to a conflict list.</span></span>|  
  
 <span data-ttu-id="934bc-126">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]개체 모델에서 *낙관적 동시성 충돌* 은 다음 두 조건에 모두 해당 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-126">In the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model, an *optimistic concurrency conflict* occurs when both of the following conditions are true:</span></span>  
  
- <span data-ttu-id="934bc-127">클라이언트가 변경 내용을 데이터베이스로 전송하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-127">The client tries to submit changes to the database.</span></span>  
  
- <span data-ttu-id="934bc-128">하나 이상의 업데이트 확인 값이 클라이언트가 마지막으로 읽은 후에 데이터베이스에서 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-128">One or more update-check values have been updated in the database since the client last read them.</span></span>  
  
 <span data-ttu-id="934bc-129">이 충돌을 해결하는 과정에는 충돌하는 개체의 멤버를 검색한 다음 수행할 작업을 결정하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-129">Resolution of this conflict includes discovering which members of the object are in conflict, and then deciding what you want to do about it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="934bc-130"><xref:System.Data.Linq.Mapping.UpdateCheck.Always> 또는 <xref:System.Data.Linq.Mapping.UpdateCheck.WhenChanged>로 매핑된 멤버만 낙관적 동시성 검사에 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-130">Only members mapped as <xref:System.Data.Linq.Mapping.UpdateCheck.Always> or <xref:System.Data.Linq.Mapping.UpdateCheck.WhenChanged> participate in optimistic concurrency checks.</span></span> <span data-ttu-id="934bc-131"><xref:System.Data.Linq.Mapping.UpdateCheck.Never>로 표시된 멤버에는 검사가 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-131">No check is performed for members marked <xref:System.Data.Linq.Mapping.UpdateCheck.Never>.</span></span> <span data-ttu-id="934bc-132">자세한 내용은 <xref:System.Data.Linq.Mapping.UpdateCheck>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="934bc-132">For more information, see <xref:System.Data.Linq.Mapping.UpdateCheck>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="934bc-133">예제</span><span class="sxs-lookup"><span data-stu-id="934bc-133">Example</span></span>  

 <span data-ttu-id="934bc-134">예를 들어, 다음 시나리오에서 User1은 데이터베이스에서 행을 쿼리하여 업데이트 준비를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-134">For example, in the following scenario, User1 starts to prepare an update by querying the database for a row.</span></span> <span data-ttu-id="934bc-135">User1은 Alfreds, Maria 및 Sales 값을 가진 행을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-135">User1 receives a row with values of Alfreds, Maria, and Sales.</span></span>  
  
 <span data-ttu-id="934bc-136">User1은 Manager 열의 값을 Alfred로 변경하고 Department 열의 값을 Marketing으로 변경하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-136">User1 wants to change the value of the Manager column to Alfred and the value of the Department column to Marketing.</span></span> <span data-ttu-id="934bc-137">User1이 이러한 변경 내용을 전송하기 전에 User2가 데이터베이스에 변경 내용을 전송했습니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-137">Before User1 can submit those changes, User2 has submitted changes to the database.</span></span> <span data-ttu-id="934bc-138">따라서 이제 Assistant 열의 값은 Mary로 변경되고 Department 열의 값은 Service로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-138">So now the value of the Assistant column has been changed to Mary and the value of the Department column to Service.</span></span>  
  
 <span data-ttu-id="934bc-139">이제 User1이 변경 내용을 전송하려고 하면 전송이 실패하고 <xref:System.Data.Linq.ChangeConflictException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-139">When User1 now tries to submit changes, the submission fails and a <xref:System.Data.Linq.ChangeConflictException> exception is thrown.</span></span> <span data-ttu-id="934bc-140">Assistant 열과 Department 열에 대한 데이터베이스 값이 예상했던 것과 다르기 때문에 이 결과가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-140">This result occurs because the database values for the Assistant column and the Department column are not those that were expected.</span></span> <span data-ttu-id="934bc-141">Assistant 및 Department 열을 나타내는 멤버가 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-141">Members representing the Assistant and Department columns are in conflict.</span></span> <span data-ttu-id="934bc-142">다음 표에서는 이 상황을 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-142">The following table summarizes the situation.</span></span>  
  
||<span data-ttu-id="934bc-143">Manager</span><span class="sxs-lookup"><span data-stu-id="934bc-143">Manager</span></span>|<span data-ttu-id="934bc-144">Assistant</span><span class="sxs-lookup"><span data-stu-id="934bc-144">Assistant</span></span>|<span data-ttu-id="934bc-145">department</span><span class="sxs-lookup"><span data-stu-id="934bc-145">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="934bc-146">원래 상태</span><span class="sxs-lookup"><span data-stu-id="934bc-146">Original state</span></span>|<span data-ttu-id="934bc-147">Alfreds</span><span class="sxs-lookup"><span data-stu-id="934bc-147">Alfreds</span></span>|<span data-ttu-id="934bc-148">Maria</span><span class="sxs-lookup"><span data-stu-id="934bc-148">Maria</span></span>|<span data-ttu-id="934bc-149">매출</span><span class="sxs-lookup"><span data-stu-id="934bc-149">Sales</span></span>|  
|<span data-ttu-id="934bc-150">User1</span><span class="sxs-lookup"><span data-stu-id="934bc-150">User1</span></span>|<span data-ttu-id="934bc-151">Alfred</span><span class="sxs-lookup"><span data-stu-id="934bc-151">Alfred</span></span>||<span data-ttu-id="934bc-152">Marketing</span><span class="sxs-lookup"><span data-stu-id="934bc-152">Marketing</span></span>|  
|<span data-ttu-id="934bc-153">User2</span><span class="sxs-lookup"><span data-stu-id="934bc-153">User2</span></span>||<span data-ttu-id="934bc-154">Mary</span><span class="sxs-lookup"><span data-stu-id="934bc-154">Mary</span></span>|<span data-ttu-id="934bc-155">서비스</span><span class="sxs-lookup"><span data-stu-id="934bc-155">Service</span></span>|  
  
 <span data-ttu-id="934bc-156">여러 다른 방법으로 이와 같은 충돌을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-156">You can resolve conflicts such as this in different ways.</span></span> <span data-ttu-id="934bc-157">자세한 내용은 [방법: 변경 내용 충돌 관리](how-to-manage-change-conflicts.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="934bc-157">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="conflict-detection-and-resolution-checklist"></a><span data-ttu-id="934bc-158">충돌 감지 및 해결 검사 목록</span><span class="sxs-lookup"><span data-stu-id="934bc-158">Conflict Detection and Resolution Checklist</span></span>  

 <span data-ttu-id="934bc-159">모든 상세 수준에서 충돌을 감지하고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-159">You can detect and resolve conflicts at any level of detail.</span></span> <span data-ttu-id="934bc-160">한편으로는 추가 고려 사항 없이 세 가지 방법(<xref:System.Data.Linq.RefreshMode> 참조) 중 하나로 모든 충돌을 해결할 수도 있고</span><span class="sxs-lookup"><span data-stu-id="934bc-160">At one extreme, you can resolve all conflicts in one of three ways (see <xref:System.Data.Linq.RefreshMode>) without additional consideration.</span></span> <span data-ttu-id="934bc-161">다른 한편으로는 충돌하는 모든 멤버에서 각 충돌 유형에 대한 특정 작업을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-161">At the other extreme, you can designate a specific action for each type of conflict on every member in conflict.</span></span>  
  
- <span data-ttu-id="934bc-162">개체 모델에서 <xref:System.Data.Linq.Mapping.UpdateCheck> 옵션을 지정하거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-162">Specify or revise <xref:System.Data.Linq.Mapping.UpdateCheck> options in your object model.</span></span>  
  
     <span data-ttu-id="934bc-163">자세한 내용은 [방법: 동시성 충돌에 대해 테스트할 멤버 지정](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="934bc-163">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
- <span data-ttu-id="934bc-164"><xref:System.Data.Linq.DataContext.SubmitChanges%2A>에 대한 호출의 try/catch 블록에서 예외를 throw하려는 지점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-164">In the try/catch block of your call to <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, specify at what point you want exceptions to be thrown.</span></span>  
  
     <span data-ttu-id="934bc-165">자세한 내용은 [방법: 동시성 예외가 throw 되는 시기 지정](how-to-specify-when-concurrency-exceptions-are-thrown.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="934bc-165">For more information, see [How to: Specify When Concurrency Exceptions are Thrown](how-to-specify-when-concurrency-exceptions-are-thrown.md).</span></span>  
  
- <span data-ttu-id="934bc-166">검색하려는 충돌 정보의 양을 결정하고 이에 따라 try/catch 블록에 코드를 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-166">Determine how much conflict detail you want to retrieve, and include code in your try/catch block accordingly.</span></span>  
  
     <span data-ttu-id="934bc-167">자세한 내용은 [방법: 엔터티 충돌 정보 검색](how-to-retrieve-entity-conflict-information.md) 및 [방법: 멤버 충돌 정보 검색](how-to-retrieve-member-conflict-information.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="934bc-167">For more information, see [How to: Retrieve Entity Conflict Information](how-to-retrieve-entity-conflict-information.md) and [How to: Retrieve Member Conflict Information](how-to-retrieve-member-conflict-information.md).</span></span>  
  
- <span data-ttu-id="934bc-168">`try` / `catch` 검색 하는 다양 한 충돌을 해결 하는 방법을 코드에 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-168">Include in your `try`/`catch` code how you want to resolve the various conflicts you discover.</span></span>  
  
     <span data-ttu-id="934bc-169">자세한 내용은 [방법: 데이터베이스 값을 보존 하 여 충돌 해결](how-to-resolve-conflicts-by-retaining-database-values.md), [방법: 데이터베이스 값을 덮어써서](how-to-resolve-conflicts-by-overwriting-database-values.md)충돌 해결 및 [방법: 데이터베이스 값을 병합 하](how-to-resolve-conflicts-by-merging-with-database-values.md)여 충돌 해결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="934bc-169">For more information, see [How to: Resolve Conflicts by Retaining Database Values](how-to-resolve-conflicts-by-retaining-database-values.md), [How to: Resolve Conflicts by Overwriting Database Values](how-to-resolve-conflicts-by-overwriting-database-values.md), and [How to: Resolve Conflicts by Merging with Database Values](how-to-resolve-conflicts-by-merging-with-database-values.md).</span></span>  
  
## <a name="linq-to-sql-types-that-support-conflict-discovery-and-resolution"></a><span data-ttu-id="934bc-170">충돌 검색 및 해결을 지원하는 LINQ to SQL 형식</span><span class="sxs-lookup"><span data-stu-id="934bc-170">LINQ to SQL Types That Support Conflict Discovery and Resolution</span></span>  

 <span data-ttu-id="934bc-171">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 낙관적 동시성의 충돌 해결을 지원하기 위한 클래스와 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="934bc-171">Classes and features to support the resolution of conflicts in optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] include the following:</span></span>  
  
- <xref:System.Data.Linq.ObjectChangeConflict?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.MemberChangeConflict?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.ChangeConflictCollection?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.ChangeConflictException?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.ChangeConflicts%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.Refresh%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.Mapping.UpdateCheck?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.RefreshMode?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="934bc-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="934bc-172">See also</span></span>

- [<span data-ttu-id="934bc-173">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="934bc-173">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
