---
description: '자세한 정보: 활동 트리 검사'
title: 활동 트리 검사
ms.date: 03/30/2017
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
ms.openlocfilehash: aac19dd99199481e6ad0d1a554ad1846678c160e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787957"
---
# <a name="activity-tree-inspection"></a><span data-ttu-id="4fd1f-103">활동 트리 검사</span><span class="sxs-lookup"><span data-stu-id="4fd1f-103">Activity Tree Inspection</span></span>

<span data-ttu-id="4fd1f-104">활동 트리 검사는 워크플로 애플리케이션 작성자가 애플리케이션에서 호스트되는 워크플로를 검사하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-104">Activity tree inspection is used by workflow application authors to inspect the workflows hosted by the application.</span></span> <span data-ttu-id="4fd1f-105"><xref:System.Activities.WorkflowInspectionServices>를 사용하여 워크플로에서 특정 자식 활동을 검색하고, 개별 활동과 속성을 열거하며, 활동에 대한 런타임 메타데이터를 특정 시간에 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-105">By using <xref:System.Activities.WorkflowInspectionServices>, workflows can be searched for specific child activities, individual activities and their properties can be enumerated, and runtime metadata of the activities can be cached at a specific time.</span></span> <span data-ttu-id="4fd1f-106">이 항목에서는 <xref:System.Activities.WorkflowInspectionServices>와 이를 사용한 활동 트리 검사 방법에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-106">This topic provides an overview of <xref:System.Activities.WorkflowInspectionServices> and how to use it to inspect an activity tree.</span></span>  
  
## <a name="using-workflowinspectionservices"></a><span data-ttu-id="4fd1f-107">WorkflowInspectionServices 사용</span><span class="sxs-lookup"><span data-stu-id="4fd1f-107">Using WorkflowInspectionServices</span></span>  

 <span data-ttu-id="4fd1f-108"><xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 메서드는 지정한 활동 트리의 모든 활동을 열거하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-108">The <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> method is used to enumerate all of the activities in the specified activity tree.</span></span> <span data-ttu-id="4fd1f-109"><xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>는 자식, 대리자 처리기, 변수 기본값, 인수 식을 비롯하여 트리 내의 모든 활동을 연결하는 열거형을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-109"><xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> returns an enumerable that touches all activities within the tree including children, delegate handlers, variable defaults, and argument expressions.</span></span> <span data-ttu-id="4fd1f-110">다음 예제에서는 <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.WriteLine> 및 식을 사용하여 워크플로 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-110">In the following example, a workflow definition is created by using a <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.WriteLine>, and expressions.</span></span> <span data-ttu-id="4fd1f-111">워크플로 정의를 만든 후에는 이를 호출한 다음 `InspectActivity` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-111">After the workflow definition is created, it is invoked and then the `InspectActivity` method is called.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 <span data-ttu-id="4fd1f-112">활동을 열거하기 위해 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>를 루트 활동에 대해 호출하고 반환되는 각 활동에 대해 다시 반복적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-112">To enumerate the activities, the <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> is called on the root activity, and again recursively on each returned activity.</span></span> <span data-ttu-id="4fd1f-113">다음 예제에서는 활동 트리의 각 활동과 식에 대한 <xref:System.Activities.Activity.DisplayName%2A>을 콘솔에 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-113">In the following example, the <xref:System.Activities.Activity.DisplayName%2A> of each activity and expression in the activity tree is written to the console.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 <span data-ttu-id="4fd1f-114">이 샘플 코드는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-114">This sample code provides the following output.</span></span>  
  
 <span data-ttu-id="4fd1f-115">**List Item 1**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-115">**List Item 1**</span></span>  
<span data-ttu-id="4fd1f-116">**목록 항목 2** 
 **목록 항목 3** 
 **목록 항목 4** 
 **목록 항목 5** 
 **컬렉션에 추가 된 항목입니다.** 
 **시퀀스** **리터럴<목록 \<String> >**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-116">**List Item 2**
**List Item 3**
**List Item 4**
**List Item 5**
**Items added to collection.**
**Sequence** **Literal<List\<String>>**</span></span>  
 <span data-ttu-id="4fd1f-117">**While**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-117">**While**</span></span>  
 <span data-ttu-id="4fd1f-118">**AddToCollection\<String>**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-118">**AddToCollection\<String>**</span></span>  
 <span data-ttu-id="4fd1f-119">**VariableValue<ICollection\<String>>**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-119">**VariableValue<ICollection\<String>>**</span></span>  
 <span data-ttu-id="4fd1f-120">**LambdaValue\<String>**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-120">**LambdaValue\<String>**</span></span>  
 <span data-ttu-id="4fd1f-121">**LocationReferenceValue<목록\<String>>**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-121">**LocationReferenceValue<List\<String>>**</span></span>  
 <span data-ttu-id="4fd1f-122">**LambdaValue\<Boolean>**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-122">**LambdaValue\<Boolean>**</span></span>  
 <span data-ttu-id="4fd1f-123">**LocationReferenceValue<목록\<String>>**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-123">**LocationReferenceValue<List\<String>>**</span></span>  
 <span data-ttu-id="4fd1f-124">**ForEach\<String>**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-124">**ForEach\<String>**</span></span>  
 <span data-ttu-id="4fd1f-125">**VariableValue<IEnumerable\<String>>**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-125">**VariableValue<IEnumerable\<String>>**</span></span>  
 <span data-ttu-id="4fd1f-126">**WriteLine**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-126">**WriteLine**</span></span>  
 <span data-ttu-id="4fd1f-127">**DelegateArgumentValue\<String>**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-127">**DelegateArgumentValue\<String>**</span></span>  
 <span data-ttu-id="4fd1f-128">**시퀀스**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-128">**Sequence**</span></span>  
 <span data-ttu-id="4fd1f-129">**WriteLine**</span><span class="sxs-lookup"><span data-stu-id="4fd1f-129">**WriteLine**</span></span>  
 <span data-ttu-id="4fd1f-130">**리터럴 \<String>**  모든 활동을 열거 하는 대신 특정 활동을 검색 하기 위해 <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> 가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-130">**Literal\<String>**  To retrieve a specific activity instead of enumerating all of the activities, <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> is used.</span></span> <span data-ttu-id="4fd1f-131"><xref:System.Activities.WorkflowInspectionServices.Resolve%2A> 및 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>는 모두 `WorkflowInspectionServices.CacheMetadata`가 이전에 호출되지 않은 경우 메타데이터 캐싱을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-131">Both <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> and <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> perform metadata caching if `WorkflowInspectionServices.CacheMetadata` has not been previously called.</span></span> <span data-ttu-id="4fd1f-132"><xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>가 호출된 경우 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>는 기존 메타데이터를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-132">If <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> has been called then <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> is based on the existing metadata.</span></span> <span data-ttu-id="4fd1f-133">따라서 <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>, <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>를 마지막으로 호출한 이후에 트리를 변경한 경우 예기치 못한 결과가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-133">Therefore, if tree changes have been made since the last call to <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>, <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> might give unexpected results.</span></span> <span data-ttu-id="4fd1f-134">를 호출한 후 워크플로를 변경한 경우 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 메서드를 호출 하 여 메타 데이터를 다시 캐시할 수 있습니다 <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> .</span><span class="sxs-lookup"><span data-stu-id="4fd1f-134">If changes have been made to the workflow after calling <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>, metadata can be re-cached by calling the <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> method.</span></span> <span data-ttu-id="4fd1f-135">메타데이터 캐시에 대해서는 다음 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-135">Caching metadata is discussed in the next section.</span></span>  
  
### <a name="caching-metadata"></a><span data-ttu-id="4fd1f-136">메타데이터 캐시</span><span class="sxs-lookup"><span data-stu-id="4fd1f-136">Caching Metadata</span></span>  

 <span data-ttu-id="4fd1f-137">활동에 대한 메타데이터 캐시에서는 활동의 인수, 변수, 자식 활동 및 활동 대리자에 대한 설명을 빌드하고 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-137">Caching the metadata for an activity builds and validates a description of the activity’s arguments, variables, child activities, and activity delegates.</span></span> <span data-ttu-id="4fd1f-138">기본적으로 메타데이터는 런타임에 활동 실행이 준비될 때 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-138">Metadata, by default, is cached by the runtime when an activity is prepared for execution.</span></span> <span data-ttu-id="4fd1f-139">워크플로 호스트 작성자가 이에 앞서 활동 또는 활동 트리에 대한 메타데이터를 캐시하려는 경우(예: 모든 선행투자 비용을 가져오려는 경우) <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>를 사용하여 원하는 시간에 메타데이터를 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fd1f-139">If a workflow host author wants to cache the metadata for an activity or activity tree before this, for example to take all of the cost upfront, then <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> can be used to cache the metadata at the desired time.</span></span>
