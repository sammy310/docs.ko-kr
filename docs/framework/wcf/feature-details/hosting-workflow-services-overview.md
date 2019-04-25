---
title: 워크플로 서비스 호스팅 개요
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: dbe271e30e9c4e98a52c01ffaa21de25c127c7ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855896"
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="6f250-102">워크플로 서비스 호스팅 개요</span><span class="sxs-lookup"><span data-stu-id="6f250-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="6f250-103">워크플로 서비스를 실행하려면 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f250-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="6f250-104"><xref:System.ServiceModel.WorkflowServiceHost>는 여러 인스턴스, 구성 및 WCF 메시징(워크플로가 호스팅되기 위해 메시징을 사용할 필요는 없지만)을 지원하는 즉시 사용 가능한 워크플로 호스트로,</span><span class="sxs-lookup"><span data-stu-id="6f250-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="6f250-105">서비스 동작의 집합을 통해 지속성, 추적 및 인스턴스 제어와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f250-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="6f250-106">WCF의 <xref:System.ServiceModel.ServiceHost>와 마찬가지로 <xref:System.ServiceModel.WorkflowServiceHost>는 모든 관리되는 .NET 응용 프로그램에서 자체 호스팅되거나 IIS/WAS에서 .xamlx 파일로 웹 호스팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f250-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="6f250-107">이 단원의 항목에서는 워크플로 서비스를 호스팅하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f250-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f250-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6f250-108">In This Section</span></span>  
 [<span data-ttu-id="6f250-109">워크플로 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="6f250-109">Hosting Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 <span data-ttu-id="6f250-110">워크플로 서비스 호스팅에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f250-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="6f250-111">워크플로 서비스 호스트 내부 기능</span><span class="sxs-lookup"><span data-stu-id="6f250-111">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 <span data-ttu-id="6f250-112"><xref:System.ServiceModel.WorkflowServiceHost>가 들어오는 메시지를 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f250-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="6f250-113">워크플로 서비스 호스트 확장성</span><span class="sxs-lookup"><span data-stu-id="6f250-113">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 <span data-ttu-id="6f250-114">워크플로 서비스 호스트의 기능을 확장하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f250-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="6f250-115">워크플로 제어 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="6f250-115">Workflow Control Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 <span data-ttu-id="6f250-116">워크플로 인스턴스를 만들 수 있는 엔드포인트를 정의하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f250-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>
  
 [<span data-ttu-id="6f250-117">방법: Windows Server App Fabric을 사용 하 여 워크플로 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="6f250-117">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="6f250-118">Windows Server AppFabric에서 기존 워크플로 서비스를 호스팅하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f250-118">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="6f250-119">WorkflowServiceHost 구성</span><span class="sxs-lookup"><span data-stu-id="6f250-119">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 <span data-ttu-id="6f250-120">지속성, 추적, 유휴 상태 및 처리되지 않은 예외 동작을 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f250-120">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6f250-121">참조</span><span class="sxs-lookup"><span data-stu-id="6f250-121">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="6f250-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="6f250-122">Related Sections</span></span>  
 [<span data-ttu-id="6f250-123">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="6f250-123">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
