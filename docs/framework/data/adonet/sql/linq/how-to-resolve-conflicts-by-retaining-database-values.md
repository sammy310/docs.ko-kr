---
description: '자세한 정보: 방법: 데이터베이스 값을 보존 하 여 충돌 해결'
title: '방법: 데이터베이스 값을 유지하여 충돌 해결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
ms.openlocfilehash: ef47370768ce474ccb6d941bcec0e66807290599
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723493"
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="e48c4-103">방법: 데이터베이스 값을 유지하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="e48c4-103">How to: Resolve Conflicts by Retaining Database Values</span></span>

<span data-ttu-id="e48c4-104">변경 내용을 다시 전송하기 전에 예상 데이터베이스 값과 실제 데이터베이스 값의 차이를 조정하려면 <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>를 사용하여 데이터베이스에서 찾은 값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="e48c4-104">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="e48c4-105">그런 다음 개체 모델의 현재 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="e48c4-105">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="e48c4-106">자세한 내용은 [낙관적 동시성: 개요](optimistic-concurrency-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e48c4-106">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e48c4-107">모든 경우에 데이터베이스에서 업데이트된 데이터를 검색하여 클라이언트의 레코드를 먼저 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="e48c4-107">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="e48c4-108">이렇게 하면 다음 업데이트 시도는 동일한 동시성 검사에서 실패하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e48c4-108">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e48c4-109">예제</span><span class="sxs-lookup"><span data-stu-id="e48c4-109">Example</span></span>  

 <span data-ttu-id="e48c4-110">이 시나리오에서는 User1이 변경 내용을 제출하려는 경우 User2가 그 동안에 Assistant 열과 Department 열을 변경했기 때문에 <xref:System.Data.Linq.ChangeConflictException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e48c4-110">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="e48c4-111">다음 표에서는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e48c4-111">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="e48c4-112">Manager</span><span class="sxs-lookup"><span data-stu-id="e48c4-112">Manager</span></span>|<span data-ttu-id="e48c4-113">Assistant</span><span class="sxs-lookup"><span data-stu-id="e48c4-113">Assistant</span></span>|<span data-ttu-id="e48c4-114">department</span><span class="sxs-lookup"><span data-stu-id="e48c4-114">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="e48c4-115">User1과 User2가 쿼리했을 때 원래 데이터베이스 상태</span><span class="sxs-lookup"><span data-stu-id="e48c4-115">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="e48c4-116">Alfreds</span><span class="sxs-lookup"><span data-stu-id="e48c4-116">Alfreds</span></span>|<span data-ttu-id="e48c4-117">Maria</span><span class="sxs-lookup"><span data-stu-id="e48c4-117">Maria</span></span>|<span data-ttu-id="e48c4-118">매출</span><span class="sxs-lookup"><span data-stu-id="e48c4-118">Sales</span></span>|  
|<span data-ttu-id="e48c4-119">User1이 변경 내용 전송 준비</span><span class="sxs-lookup"><span data-stu-id="e48c4-119">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="e48c4-120">Alfred</span><span class="sxs-lookup"><span data-stu-id="e48c4-120">Alfred</span></span>||<span data-ttu-id="e48c4-121">Marketing</span><span class="sxs-lookup"><span data-stu-id="e48c4-121">Marketing</span></span>|  
|<span data-ttu-id="e48c4-122">User2가 이미 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="e48c4-122">User2 has already submitted these changes.</span></span>||<span data-ttu-id="e48c4-123">Mary</span><span class="sxs-lookup"><span data-stu-id="e48c4-123">Mary</span></span>|<span data-ttu-id="e48c4-124">서비스</span><span class="sxs-lookup"><span data-stu-id="e48c4-124">Service</span></span>|  
  
 <span data-ttu-id="e48c4-125">User1이 최신 데이터베이스 값으로 개체 모델의 현재 값을 덮어써서 이 충돌을 해결하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e48c4-125">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="e48c4-126">User1이 <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>를 사용하여 충돌을 해결하는 경우 데이터베이스의 결과는 다음 표와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e48c4-126">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="e48c4-127">Manager</span><span class="sxs-lookup"><span data-stu-id="e48c4-127">Manager</span></span>|<span data-ttu-id="e48c4-128">Assistant</span><span class="sxs-lookup"><span data-stu-id="e48c4-128">Assistant</span></span>|<span data-ttu-id="e48c4-129">department</span><span class="sxs-lookup"><span data-stu-id="e48c4-129">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="e48c4-130">충돌 해결 후 변경된 상태</span><span class="sxs-lookup"><span data-stu-id="e48c4-130">New state after conflict resolution.</span></span>|<span data-ttu-id="e48c4-131">Alfreds</span><span class="sxs-lookup"><span data-stu-id="e48c4-131">Alfreds</span></span><br /><br /> <span data-ttu-id="e48c4-132">(원래 값)</span><span class="sxs-lookup"><span data-stu-id="e48c4-132">(original)</span></span>|<span data-ttu-id="e48c4-133">Mary</span><span class="sxs-lookup"><span data-stu-id="e48c4-133">Mary</span></span><br /><br /> <span data-ttu-id="e48c4-134">(User2가 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="e48c4-134">(from User2)</span></span>|<span data-ttu-id="e48c4-135">서비스</span><span class="sxs-lookup"><span data-stu-id="e48c4-135">Service</span></span><br /><br /> <span data-ttu-id="e48c4-136">(User2가 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="e48c4-136">(from User2)</span></span>|  
  
 <span data-ttu-id="e48c4-137">다음 예제 코드에서는 개체 모델의 현재 값을 데이터베이스 값으로 덮어쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e48c4-137">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="e48c4-138">각 멤버 충돌에 대한 검사 또는 사용자 지정 처리는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e48c4-138">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e48c4-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e48c4-139">See also</span></span>

- [<span data-ttu-id="e48c4-140">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="e48c4-140">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
