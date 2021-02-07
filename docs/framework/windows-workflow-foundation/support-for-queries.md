---
description: '자세히 알아보기: 쿼리 지원'
title: 쿼리 지원
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: 418e511e8b845653b9f3ec86d90c6cbfb25d5671
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755215"
---
# <a name="support-for-queries"></a><span data-ttu-id="5b074-103">쿼리 지원</span><span class="sxs-lookup"><span data-stu-id="5b074-103">Support for Queries</span></span>

<span data-ttu-id="5b074-104">SQL 워크플로 인스턴스 저장소는 잘 알려진 속성 집합을 저장소에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-104">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="5b074-105">사용자는 이러한 속성을 기반으로 인스턴스를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-105">Users can query for instances based on these properties.</span></span> <span data-ttu-id="5b074-106">다음은 잘 알려진 일부 속성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-106">The following list contains some of these well-known properties:</span></span>  
  
- <span data-ttu-id="5b074-107">**사이트 이름입니다.**</span><span class="sxs-lookup"><span data-stu-id="5b074-107">**Site Name.**</span></span> <span data-ttu-id="5b074-108">서비스를 포함하는 웹 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-108">Name of the Web site that contains the service.</span></span>  
  
- <span data-ttu-id="5b074-109">**Relative Application Path.**</span><span class="sxs-lookup"><span data-stu-id="5b074-109">**Relative Application Path.**</span></span> <span data-ttu-id="5b074-110">웹 사이트에 상대적인 애플리케이션 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-110">Path of the application relative to the Web site.</span></span>  
  
- <span data-ttu-id="5b074-111">**Relative Service Path.**</span><span class="sxs-lookup"><span data-stu-id="5b074-111">**Relative Service Path.**</span></span> <span data-ttu-id="5b074-112">애플리케이션에 상대적인 서비스 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-112">Path of the service relative to the application.</span></span>  
  
- <span data-ttu-id="5b074-113">**서비스 이름입니다.**</span><span class="sxs-lookup"><span data-stu-id="5b074-113">**Service Name.**</span></span> <span data-ttu-id="5b074-114">서비스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-114">Name of the service.</span></span>  
  
- <span data-ttu-id="5b074-115">**서비스 네임 스페이스입니다.**</span><span class="sxs-lookup"><span data-stu-id="5b074-115">**Service Namespace.**</span></span> <span data-ttu-id="5b074-116">서비스에 사용되는 네임스페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-116">Name of the namespace that the service uses.</span></span>  
  
- <span data-ttu-id="5b074-117">**Current Machine.**</span><span class="sxs-lookup"><span data-stu-id="5b074-117">**Current Machine.**</span></span>  
  
- <span data-ttu-id="5b074-118">**마지막 컴퓨터** 입니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-118">**Last Machine**.</span></span> <span data-ttu-id="5b074-119">워크플로 서비스 인스턴스가 마지막으로 실행된 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-119">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b074-120">워크플로 서비스 호스트를 사용하는 자체 호스팅 시나리오의 경우 마지막 네 속성만 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-120">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="5b074-121">워크플로 애플리케이션 시나리오의 경우 마지막 속성만 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-121">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="5b074-122">워크플로 런타임에서 처음 세 속성에 대한 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-122">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="5b074-123">워크플로 서비스 호스트는 **일시 중단 이유** 속성의 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-123">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="5b074-124">SQL 워크플로 인스턴스 저장소는 **마지막으로 업데이트 된 컴퓨터** 속성의 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-124">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="5b074-125">또한 SQL 워크플로 인스턴스 저장소 기능을 사용하면 사용자 지정 속성을 지정하여 지속성 데이터베이스에 값을 저장한 다음 쿼리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-125">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="5b074-126">사용자 지정 승격에 대 한 자세한 내용은 [저장소 확장성](store-extensibility.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b074-126">For more information about custom promotions, see [Store Extensibility](store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="5b074-127">보기</span><span class="sxs-lookup"><span data-stu-id="5b074-127">Views</span></span>  

 <span data-ttu-id="5b074-128">인스턴스 저장소에는 다음 뷰가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-128">The instance store contains the following views.</span></span> <span data-ttu-id="5b074-129">자세한 내용은 [지 속성 데이터베이스 스키마](persistence-database-schema.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b074-129">See [Persistence Database Schema](persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="5b074-130">Instances 뷰</span><span class="sxs-lookup"><span data-stu-id="5b074-130">The Instances View</span></span>  

 <span data-ttu-id="5b074-131">인스턴스 뷰에는 다음 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-131">The Instances view contains the following fields:</span></span>  
  
1. <span data-ttu-id="5b074-132">**ID**</span><span class="sxs-lookup"><span data-stu-id="5b074-132">**Id**</span></span>  
  
2. <span data-ttu-id="5b074-133">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="5b074-133">**PendingTimer**</span></span>  
  
3. <span data-ttu-id="5b074-134">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="5b074-134">**CreationTime**</span></span>  
  
4. <span data-ttu-id="5b074-135">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="5b074-135">**LastUpdatedTime**</span></span>  
  
5. <span data-ttu-id="5b074-136">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="5b074-136">**ServiceDeploymentId**</span></span>  
  
6. <span data-ttu-id="5b074-137">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="5b074-137">**SuspensionExceptionName**</span></span>  
  
7. <span data-ttu-id="5b074-138">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="5b074-138">**SuspensionReason**</span></span>  
  
8. <span data-ttu-id="5b074-139">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="5b074-139">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="5b074-140">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="5b074-140">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="5b074-141">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="5b074-141">**LastMachine**</span></span>  
  
11. <span data-ttu-id="5b074-142">**ExecutionStatus**</span><span class="sxs-lookup"><span data-stu-id="5b074-142">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="5b074-143">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="5b074-143">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="5b074-144">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="5b074-144">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="5b074-145">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="5b074-145">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="5b074-146">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="5b074-146">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="5b074-147">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="5b074-147">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="5b074-148">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="5b074-148">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="5b074-149">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="5b074-149">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="5b074-150">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="5b074-150">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="5b074-151">ServiceDeployments 뷰</span><span class="sxs-lookup"><span data-stu-id="5b074-151">The ServiceDeployments view</span></span>  

 <span data-ttu-id="5b074-152">ServiceDeployments 뷰에는 다음 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-152">The ServiceDeployments view contains the following fields:</span></span>  
  
1. <span data-ttu-id="5b074-153">**SiteName**</span><span class="sxs-lookup"><span data-stu-id="5b074-153">**SiteName**</span></span>  
  
2. <span data-ttu-id="5b074-154">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="5b074-154">**RelativeServicePath**</span></span>  
  
3. <span data-ttu-id="5b074-155">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="5b074-155">**RelativeApplicationPath**</span></span>  
  
4. <span data-ttu-id="5b074-156">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="5b074-156">**ServiceName**</span></span>  
  
5. <span data-ttu-id="5b074-157">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="5b074-157">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="5b074-158">InstancePromotedProperties 뷰</span><span class="sxs-lookup"><span data-stu-id="5b074-158">The InstancePromotedProperties view</span></span>  

 <span data-ttu-id="5b074-159">InstancePromotedProperties 뷰에는 다음 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b074-159">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="5b074-160">승격 된 속성에 대 한 자세한 내용은 [저장소 확장성](store-extensibility.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b074-160">For details on promoted properties, see the [Store Extensibility](store-extensibility.md) topic.</span></span>  
  
1. <span data-ttu-id="5b074-161">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="5b074-161">**InstanceId**</span></span>  
  
2. <span data-ttu-id="5b074-162">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="5b074-162">**EncodingOption**</span></span>  
  
3. <span data-ttu-id="5b074-163">**PromotionName**</span><span class="sxs-lookup"><span data-stu-id="5b074-163">**PromotionName**</span></span>  
  
4. <span data-ttu-id="5b074-164">**값 #** ( **Value1** 에서 **Value64** 까지의 필드 범위)</span><span class="sxs-lookup"><span data-stu-id="5b074-164">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
