---
description: '자세한 정보: 워크플로 서비스'
title: 워크플로 서비스
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: 195ecf0322146a8735362dfbb82dc19bf1c04312
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704474"
---
# <a name="workflow-services"></a><span data-ttu-id="1eae3-103">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="1eae3-103">Workflow Services</span></span>

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="1eae3-104">에서는 XAML을 사용하여 워크플로 기반 서비스를 선언적으로 자세히 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-104">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="1eae3-105">즉, XAML을 사용하여 서비스를 구현하는 워크플로를 정의하고 서비스가 노출하는 엔드포인트를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-105">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="1eae3-106">이 단원의 항목에서는 선언적 방식의 서비스 작성을 지원하는 프로그래밍 모델에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-106">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1eae3-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1eae3-107">In This Section</span></span>  

 [<span data-ttu-id="1eae3-108">워크플로 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="1eae3-108">Workflow Services Overview</span></span>](workflow-services-overview.md)  
 <span data-ttu-id="1eae3-109">워크플로 서비스를 만들고 호스팅하는 데 사용되는 구성 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-109">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="1eae3-110">메시징 활동</span><span class="sxs-lookup"><span data-stu-id="1eae3-110">Messaging Activities</span></span>](messaging-activities.md)  
 <span data-ttu-id="1eae3-111">워크플로에서 메시지를 보내고 받을 수 있는 활동에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-111">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="1eae3-112">방법: 메시징 활동을 사용하여 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="1eae3-112">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="1eae3-113">메시징 활동을 사용하여 워크플로 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-113">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="1eae3-114">방법: 워크플로 애플리케이션에서 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="1eae3-114">How To: Access a Service From a Workflow Application</span></span>](how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="1eae3-115">워크플로 애플리케이션에서 서비스를 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-115">Discusses how to call a service from a workflow application.</span></span>  
  
 <span data-ttu-id="1eae3-116">[Correlation](correlation.md)(상관 관계)</span><span class="sxs-lookup"><span data-stu-id="1eae3-116">[Correlation](correlation.md)</span></span>  
 <span data-ttu-id="1eae3-117">상관 관계를 사용하여 메시지를 서로 매핑하거나 인스턴스에 매핑하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-117">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="1eae3-118">순서에 상관없이 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="1eae3-118">Out-of-Order Message Processing</span></span>](out-of-order-message-processing.md)  
 <span data-ttu-id="1eae3-119">순서가 맞지 않는 메시지를 허용하도록 서비스를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-119">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="1eae3-120">계약 중심 워크플로 서비스 개발</span><span class="sxs-lookup"><span data-stu-id="1eae3-120">Contract First Workflow Service Development</span></span>](../../windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="1eae3-121">기존 서비스 계약을 기반으로 워크플로 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-121">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="1eae3-122">방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="1eae3-122">How to: Create a workflow service that consumes an existing service contract</span></span>](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="1eae3-123">기존 서비스 계약을 사용하여 워크플로 서비스를 만드는 방법을 보여 주는 단계별 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-123">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="1eae3-124">워크플로 서비스 호스팅 개요</span><span class="sxs-lookup"><span data-stu-id="1eae3-124">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)  
 <span data-ttu-id="1eae3-125">워크플로 서비스 호스팅의 여러 측면에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-125">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="1eae3-126">워크플로에서 계약 사용</span><span class="sxs-lookup"><span data-stu-id="1eae3-126">Using Contracts in Workflow</span></span>](using-contracts-in-workflow.md)  
 <span data-ttu-id="1eae3-127">여러 형식의 계약 및 계약 유추에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1eae3-127">Describes the different types of contracts and contract inference.</span></span>
