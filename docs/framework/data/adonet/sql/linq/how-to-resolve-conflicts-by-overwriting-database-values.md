---
description: '자세한 정보: 방법: 데이터베이스 값을 덮어써서 충돌 해결'
title: '방법: 데이터베이스 값을 덮어써서 충돌 해결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
ms.openlocfilehash: 4eaa66b4bb49706bb1ca6449d24c688a89f2750b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723506"
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="30524-103">방법: 데이터베이스 값을 덮어써서 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="30524-103">How to: Resolve Conflicts by Overwriting Database Values</span></span>

<span data-ttu-id="30524-104">변경 내용을 전송하기 전에 예상 데이터베이스 값과 실제 데이터베이스 값의 차이점을 조정하려면 <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>를 사용하여 데이터베이스 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="30524-104">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="30524-105">자세한 내용은 [낙관적 동시성: 개요](optimistic-concurrency-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30524-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30524-106">모든 경우에 데이터베이스에서 업데이트된 데이터를 검색하여 클라이언트의 레코드를 먼저 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="30524-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="30524-107">이렇게 하면 다음 업데이트 시도는 동일한 동시성 검사에서 실패하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30524-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30524-108">예제</span><span class="sxs-lookup"><span data-stu-id="30524-108">Example</span></span>  

 <span data-ttu-id="30524-109">이 시나리오에서는 User1이 변경 내용을 전송하려 하는 경우 User2가 그 동안에 Assistant 열과 Department 열을 변경했기 때문에 <xref:System.Data.Linq.ChangeConflictException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="30524-109">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="30524-110">다음 표에서는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30524-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="30524-111">Manager</span><span class="sxs-lookup"><span data-stu-id="30524-111">Manager</span></span>|<span data-ttu-id="30524-112">Assistant</span><span class="sxs-lookup"><span data-stu-id="30524-112">Assistant</span></span>|<span data-ttu-id="30524-113">department</span><span class="sxs-lookup"><span data-stu-id="30524-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="30524-114">User1과 User2가 쿼리했을 때 원래 데이터베이스 상태</span><span class="sxs-lookup"><span data-stu-id="30524-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="30524-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="30524-115">Alfreds</span></span>|<span data-ttu-id="30524-116">Maria</span><span class="sxs-lookup"><span data-stu-id="30524-116">Maria</span></span>|<span data-ttu-id="30524-117">매출</span><span class="sxs-lookup"><span data-stu-id="30524-117">Sales</span></span>|  
|<span data-ttu-id="30524-118">User1이 변경 내용 전송 준비</span><span class="sxs-lookup"><span data-stu-id="30524-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="30524-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="30524-119">Alfred</span></span>||<span data-ttu-id="30524-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="30524-120">Marketing</span></span>|  
|<span data-ttu-id="30524-121">User2가 이미 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="30524-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="30524-122">Mary</span><span class="sxs-lookup"><span data-stu-id="30524-122">Mary</span></span>|<span data-ttu-id="30524-123">서비스</span><span class="sxs-lookup"><span data-stu-id="30524-123">Service</span></span>|  
  
 <span data-ttu-id="30524-124">User1이 데이터베이스 값을 현재 클라이언트 멤버 값에 덮어써서 이 충돌을 해결하기로 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="30524-124">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="30524-125">User1이 <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>를 사용하여 문제를 해결하는 경우 데이터베이스의 결과는 다음 테이블과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="30524-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="30524-126">Manager</span><span class="sxs-lookup"><span data-stu-id="30524-126">Manager</span></span>|<span data-ttu-id="30524-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="30524-127">Assistant</span></span>|<span data-ttu-id="30524-128">department</span><span class="sxs-lookup"><span data-stu-id="30524-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="30524-129">충돌 해결 후 변경된 상태</span><span class="sxs-lookup"><span data-stu-id="30524-129">New state after conflict resolution.</span></span>|<span data-ttu-id="30524-130">Alfred</span><span class="sxs-lookup"><span data-stu-id="30524-130">Alfred</span></span><br /><br /> <span data-ttu-id="30524-131">(User1이 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="30524-131">(from User1)</span></span>|<span data-ttu-id="30524-132">Maria</span><span class="sxs-lookup"><span data-stu-id="30524-132">Maria</span></span><br /><br /> <span data-ttu-id="30524-133">(원래 값)</span><span class="sxs-lookup"><span data-stu-id="30524-133">(original)</span></span>|<span data-ttu-id="30524-134">Marketing</span><span class="sxs-lookup"><span data-stu-id="30524-134">Marketing</span></span><br /><br /> <span data-ttu-id="30524-135">(User1이 전송한 값)</span><span class="sxs-lookup"><span data-stu-id="30524-135">(from User1)</span></span>|  
  
 <span data-ttu-id="30524-136">다음의 예제 코드에서는 데이터베이스 값을 현재 클라이언트 멤버 값으로 덮어쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30524-136">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="30524-137">각 멤버 충돌에 대한 검사 또는 사용자 지정 처리는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30524-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="30524-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30524-138">See also</span></span>

- [<span data-ttu-id="30524-139">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="30524-139">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
