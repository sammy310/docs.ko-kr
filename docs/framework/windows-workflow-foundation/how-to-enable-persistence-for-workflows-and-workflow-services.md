---
title: '방법: 워크플로 및 워크플로 서비스에 지속성 사용'
description: 구성 파일을 사용 하 여 프로그래밍 방식으로 워크플로 및 워크플로 서비스에 지 속성을 사용 하도록 SQL 워크플로 인스턴스 저장소를 구성 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 31fe6e3f06989e9a42254747565342cf97e4b9f1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421516"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="64b76-103">방법: 워크플로 및 워크플로 서비스에 지속성 사용</span><span class="sxs-lookup"><span data-stu-id="64b76-103">How to: Enable Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="64b76-104">이 항목에서는 워크플로 및 워크플로 서비스에 대해 지속성을 사용하도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-104">This topic describes how to enable persistence for workflows and workflow services.</span></span>

## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="64b76-105">워크플로에 대해 지속성 사용</span><span class="sxs-lookup"><span data-stu-id="64b76-105">Enable Persistence for Workflows</span></span>

<span data-ttu-id="64b76-106">클래스의 속성을 사용 하 여 인스턴스 저장소를 **WorkflowApplication** 과 연결할 수 있습니다 <xref:System.Activities.WorkflowApplication.InstanceStore%2A> <xref:System.Activities.WorkflowApplication> .</span><span class="sxs-lookup"><span data-stu-id="64b76-106">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="64b76-107"><xref:System.Activities.WorkflowApplication.Persist%2A> 메서드는 애플리케이션에 연결된 인스턴스 스토리지에 워크플로를 저장하거나 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-107">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="64b76-108"><xref:System.Activities.WorkflowApplication.Unload%2A> 메서드는 인스턴스 저장소에 워크플로를 유지한 다음 메모리에서 인스턴스를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-108">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="64b76-109">**Load** 메서드는 인스턴스 지 속성 저장소에 저장 된 워크플로 데이터를 사용 하 여 워크플로를 메모리로 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-109">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>

<span data-ttu-id="64b76-110">**Persist** 메서드는 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-110">The **Persist** method performs the following steps:</span></span>

1. <span data-ttu-id="64b76-111">워크플로 스케줄러를 일시 중지하고 워크플로가 유휴 상태로 전환될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-111">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="64b76-112">워크플로를 지속성 저장소에 유지하거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-112">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="64b76-113">워크플로 스케줄러를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-113">Resumes the workflow scheduler.</span></span>

 <span data-ttu-id="64b76-114">**Unload** 메서드는 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-114">The **Unload** method performs the following steps:</span></span>

1. <span data-ttu-id="64b76-115">워크플로 스케줄러를 일시 중지하고 워크플로가 유휴 상태로 전환될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-115">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="64b76-116">워크플로를 지속성 저장소에 유지하거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-116">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="64b76-117">워크플로 인스턴스를 메모리에서 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-117">Disposes the workflow instance in the memory.</span></span>

<span data-ttu-id="64b76-118">워크플로가 영구 영역을 종료할 때까지 지속 되지 않은 영역에 있는 동안 **persist** 및 **Unload** 메서드는 모두 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-118">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="64b76-119">비지속성 영역이 완료되면 메서드에서 지속 또는 언로드 작업을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-119">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="64b76-120">제한 시간이 경과할 때까지 비지속성 영역이 완료되지 않거나 지속성 프로세스가 너무 오래 걸릴 경우 TimeoutException이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-120">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>

## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="64b76-121">코드에서 워크플로 서비스에 대해 지속성 사용</span><span class="sxs-lookup"><span data-stu-id="64b76-121">Enable Persistence for Workflow Services in Code</span></span>

<span data-ttu-id="64b76-122">클래스의 **DurableInstancingOptions** 멤버에는 <xref:System.ServiceModel.WorkflowServiceHost> 인스턴스 저장소를 **WorkflowServiceHost**와 연결 하는 데 사용할 수 있는 이름이 **InstanceStore** 인 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-122">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

<span data-ttu-id="64b76-123">**WorkflowServiceHost** 가 열리면 **DurableInstancingOptions** 가 null이 아닌 경우 지 속성을 자동으로 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-123">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>

<span data-ttu-id="64b76-124">일반적으로 서비스 동작은 **InstanceStore** 속성을 사용 하 여 워크플로 서비스 호스트에 사용할 구체적인 인스턴스 저장소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-124">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="64b76-125">예를 들어 SqlWorkflowInstanceStoreBehavior는 **SqlWorkflowInstanceStore**의 인스턴스를 만들고 구성 하 여 **DurableInstancingOptions**에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-125">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="64b76-126">애플리케이션 구성 파일을 사용하여 워크플로 서비스에 지속성 허용</span><span class="sxs-lookup"><span data-stu-id="64b76-126">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>

<span data-ttu-id="64b76-127">다음 코드를 app.config 또는 web.config 파일에 추가하여 애플리케이션 구성 파일을 통해 지속성을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64b76-127">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="myBehavior">
          <sqlWorkflowInstanceStore connectionString="Data Source=myDatabaseServer;Initial Catalog=myPersistenceDatabase" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```
