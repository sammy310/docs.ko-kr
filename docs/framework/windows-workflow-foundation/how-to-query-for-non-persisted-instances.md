---
description: '자세한 정보: 방법: 비지속형 인스턴스 쿼리'
title: '방법: 비지속성 인스턴스 쿼리'
ms.date: 03/30/2017
ms.assetid: 294019b1-c1a7-4b81-a14f-b47c106cd723
ms.openlocfilehash: 2cef64f97b32c5f1d31fa078200bc2fe15179485
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777660"
---
# <a name="how-to-query-for-non-persisted-instances"></a><span data-ttu-id="303e4-103">방법: 비지속성 인스턴스 쿼리</span><span class="sxs-lookup"><span data-stu-id="303e4-103">How to: Query for Non-persisted Instances</span></span>

<span data-ttu-id="303e4-104">서비스의 새 인스턴스가 만들어지고 이 서비스에 SQL 워크플로 인스턴스 저장소 동작이 정의되는 경우, 서비스 호스트에서는 인스턴스 저장소에 해당 서비스 인스턴스에 대한 초기 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-104">When a new instance of a service is created and the service has the SQL Workflow Instance Store behavior defined, the service host creates a initial entry for that service instance in the instance store.</span></span> <span data-ttu-id="303e4-105">이후에 서비스 인스턴스가 처음으로 저장되면 SQL 워크플로 인스턴스 저장소 동작은 활성화, 복구 및 제어에 필요한 추가 데이터와 함께 현재 인스턴스 상태를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-105">Subsequently when the service instance persists for the first time, the SQL Workflow Instance Store behavior stores the current instance state together with additional data that is required for activation, recovery, and control.</span></span>

<span data-ttu-id="303e4-106">인스턴스의 초기 항목이 만들어진 후 인스턴스가 저장되지 않은 경우 해당 서비스 인스턴스는 비지속성 상태에 있다고 합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-106">If an instance is not persisted after the initial entry for the instance is created, the service instance is said to be in the non-persisted state.</span></span> <span data-ttu-id="303e4-107">저장된 모든 서비스 인스턴스를 쿼리하고 제어할 수 있지만</span><span class="sxs-lookup"><span data-stu-id="303e4-107">All the persisted service instances can be queried and controlled.</span></span> <span data-ttu-id="303e4-108">비지속성 서비스 인스턴스는 쿼리할 수 없으며 제어할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-108">Non-persisted service instances can neither be queried nor controlled.</span></span> <span data-ttu-id="303e4-109">처리되지 않는 예외로 인해 일시 중단된 비지속성 인스턴스는 쿼리할 수만 있고 제어할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-109">If a non-persisted instance is suspended due to an unhandled exception it can be queried but not controlled.</span></span>

<span data-ttu-id="303e4-110">아직 저장되지 않는 영속 서비스 인스턴스는 다음과 같은 경우에 비지속성 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-110">Durable service instances that are not yet persisted remain in a non-persisted state in the following scenarios:</span></span>

- <span data-ttu-id="303e4-111">인스턴스가 처음으로 저장되기 전에 서비스 호스트에서 충돌이 발생한 경우.</span><span class="sxs-lookup"><span data-stu-id="303e4-111">The service host crashes before the instance persisted for the first time.</span></span> <span data-ttu-id="303e4-112">인스턴스의 초기 항목은 인스턴스 저장소에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-112">The initial entry for the instance remains in the instance store.</span></span> <span data-ttu-id="303e4-113">인스턴스는 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-113">The instance is not recoverable.</span></span> <span data-ttu-id="303e4-114">상관 관계 메시지가 도착하면 인스턴스는 다시 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-114">If a correlated message arrives, the instance becomes active again.</span></span>

- <span data-ttu-id="303e4-115">인스턴스가 처음으로 저장되기 전에 인스턴스에서 예기치 않은 예외가 발생한 경우.</span><span class="sxs-lookup"><span data-stu-id="303e4-115">The instance experiences an unhandled exception before it persisted for the first time.</span></span> <span data-ttu-id="303e4-116">다음 시나리오가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-116">The following scenarios arise</span></span>

  - <span data-ttu-id="303e4-117">**UnhandledExceptionAction** 속성 값이 **중단** 으로 설정 되 면 서비스 배포 정보가 인스턴스 저장소에 기록 되 고 인스턴스가 메모리에서 언로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-117">If the value of the **UnhandledExceptionAction** property is set to **Abandon**, the service deployment information is written to the instance store and the instance is unloaded from memory.</span></span> <span data-ttu-id="303e4-118">인스턴스는 지속성 데이터베이스에서 비지속성 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-118">The instance remains in non-persisted state in the persistence database.</span></span>

  - <span data-ttu-id="303e4-119">**UnhandledExceptionAction** 속성 값이 **AbandonAndSuspend** 로 설정 되 면 서비스 배포 정보가 지 속성 데이터베이스에 기록 되 고 인스턴스 상태가 **일시 중단** 됨으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-119">If the value of the **UnhandledExceptionAction** property is set to **AbandonAndSuspend**, the service deployment information is written to the persistence database and the instance state is set to **Suspended**.</span></span> <span data-ttu-id="303e4-120">이 인스턴스는 다시 시작하거나 취소하거나 종료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-120">The instance cannot be resumed, canceled, or terminated.</span></span> <span data-ttu-id="303e4-121">인스턴스가 아직 저장되지 않아 인스턴스의 데이터베이스 항목이 완료되지 않았으므로 서비스 호스트에서는 해당 인스턴스를 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-121">The service host cannot load the instance because the instance hasn't persisted yet and, hence the database entry for the instance is not complete.</span></span>

  - <span data-ttu-id="303e4-122">**UnhandledExceptionAction** 속성 값이 **Cancel** 또는 **Terminate** 로 설정 되 면 서비스 배포 정보가 인스턴스 저장소에 기록 되 고 인스턴스 상태가 **Completed** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-122">If the value of the **UnhandledExceptionAction** property is set to **Cancel** or **Terminate**, the service deployment information is written to the instance store and the instance state is set to **Completed**.</span></span>

<span data-ttu-id="303e4-123">다음 단원에서는 SQL 지속성 데이터베이스에서 비지속성 인스턴스를 찾고 이러한 인스턴스를 데이터베이스에서 삭제하는 샘플 쿼리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-123">The following sections provide sample queries to find non-persisted instances in the SQL persistence database and to delete these instances from the database.</span></span>

## <a name="to-find-all-instances-not-persisted-yet"></a><span data-ttu-id="303e4-124">아직 저장되지 않은 모든 인스턴스를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="303e4-124">To find all instances not persisted yet</span></span>

<span data-ttu-id="303e4-125">다음 SQL 쿼리에서는 지속성 데이터베이스에 아직 저장되지 않은 모든 인스턴스의 ID와 만든 시간을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-125">The following SQL query returns the ID and creation time for all instances that are not persisted in to the persistence database yet.</span></span>

```sql
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0;
```

## <a name="to-find-all-instances-not-persisted-yet-and-also-not-loaded"></a><span data-ttu-id="303e4-126">아직 저장되지 않고 로드되지도 않은 모든 인스턴스를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="303e4-126">To find all instances not persisted yet and also not loaded</span></span>

 <span data-ttu-id="303e4-127">다음 SQL 쿼리에서는 아직 저장되지 않고 로드되지도 않은 모든 인스턴스의 ID와 만든 시간을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-127">The following SQL query returns ID and creation time for all instances that are not persisted and also are not loaded.</span></span>

```sql
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and CurrentMachine is NULL;
```

## <a name="to-find-all-suspended-instances-not-persisted-yet"></a><span data-ttu-id="303e4-128">아직 저장되지 않은 일시 중단된 모든 인스턴스를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="303e4-128">To find all suspended instances not persisted yet</span></span>

<span data-ttu-id="303e4-129">다음 SQL 쿼리에서는 저장되지 않고 일시 중단된 상태에 있는 모든 인스턴스의 ID, 만든 시간, 일시 중단 이유 및 일시 중단 예외 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-129">The following SQL query returns ID, creation time, suspension reason, and suspension exception name for all instances that are not persisted and also in a suspended state.</span></span>

```sql
select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and IsSuspended = 1;
```

## <a name="to-delete-non-persisted-instances-from-the-persistence-database"></a><span data-ttu-id="303e4-130">지속성 데이터베이스에서 비지속성 인스턴스를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="303e4-130">To delete non-persisted instances from the persistence database</span></span>

<span data-ttu-id="303e4-131">인스턴스 저장소에서 비지속성 인스턴스를 주기적으로 검사하고, 상관 관계 메시지를 받지 않는 것이 확실한 인스턴스는 인스턴스 저장소에서 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-131">You should periodically check the instance store for non-persisted instances and remove instances from the instance store if you are sure that the instance will not receive a correlated message.</span></span> <span data-ttu-id="303e4-132">예를 들어 인스턴스가 데이터베이스에 몇 달 동안 있었고 일반적으로 워크플로의 수명이 며칠 정도임을 알고 있는 경우 해당 인스턴스는 손상되어 초기화되지 않는 인스턴스라고 간주해도 무방합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-132">For example, if the instance has been in the database for several months and you know that the workflow typically has a lifetime of a few days, it would be safe to assume that this is an uninitialized instance that had crashed.</span></span>

<span data-ttu-id="303e4-133">일반적으로 일시 중단되지 않거나 로드되지 않은 비지속성 인스턴스는 삭제해도 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-133">In general, it is safe to delete non-persisted instances that are not suspended or not loaded.</span></span> <span data-ttu-id="303e4-134">이 인스턴스 집합에는 방금 만들었지만 아직 지속 되지 않은 인스턴스가 포함 되어 있으므로 지속형이 아닌 인스턴스를 **모두** 삭제 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-134">You should not delete **all** the non-persisted instances because this instance set includes instances that are just created but are not persisted yet.</span></span> <span data-ttu-id="303e4-135">인스턴스가 로드된 워크플로 서비스 호스트에서 예외를 발생시켰거나 인스턴스 자체에서 예외를 발생시켰기 때문에 방치된 비지속성 인스턴스만 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-135">You should only delete non-persisted instances that are left over because the workflow service host that had the instance loaded caused an exception or the instance itself caused an exception.</span></span>

> [!WARNING]
> <span data-ttu-id="303e4-136">인스턴스 저장소에서 비지속성 인스턴스를 삭제하면 저장소의 크기가 줄어들고 저장소 작업의 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="303e4-136">Deleting non-persisted instances from the instance store decreases the size of the store and may improve the performance of store operations.</span></span>
