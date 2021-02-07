---
description: '자세히 알아보기: ServiceThrottlingBehavior를 사용 하 여 WCF 서비스 성능 제어'
title: ServiceThrottlingBehavior를 사용하여 WCF 서비스 성능 제어
ms.date: 03/30/2017
helpviewer_keywords:
- behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
ms.openlocfilehash: 4a53c89c6b17402b7dd32120d049426052e4f9e0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704422"
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a><span data-ttu-id="646b9-103">ServiceThrottlingBehavior를 사용하여 WCF 서비스 성능 제어</span><span class="sxs-lookup"><span data-stu-id="646b9-103">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>

<span data-ttu-id="646b9-104"><xref:System.ServiceModel.Description.ServiceThrottlingBehavior> 클래스는 애플리케이션 수준에서 생성되는 인스턴스 또는 세션의 수를 제한하기 위해 사용할 수 있는 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="646b9-104">The <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> class exposes properties that you can use to limit how many instances or sessions are created at the application level.</span></span> <span data-ttu-id="646b9-105">이 동작을 사용 하 여 WCF (Windows Communication Foundation) 응용 프로그램의 성능을 세밀 하 게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="646b9-105">Using this behavior, you can fine-tune the performance of your Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a><span data-ttu-id="646b9-106">서비스 인스턴스 및 동시 호출 제어</span><span class="sxs-lookup"><span data-stu-id="646b9-106">Controlling Service Instances and Concurrent Calls</span></span>  

 <span data-ttu-id="646b9-107"><xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> 클래스를 통해 처리 중인 최대 메시지 수를 지정하려면 <xref:System.ServiceModel.ServiceHost> 속성을 사용하고, 서비스의 최대 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> 개체 수를 지정하려면 <xref:System.ServiceModel.InstanceContext> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="646b9-107">Use the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> property to specify the maximum number of messages actively processing across a <xref:System.ServiceModel.ServiceHost> class, and the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> property to specify the maximum number of <xref:System.ServiceModel.InstanceContext> objects in the service.</span></span>  
  
 <span data-ttu-id="646b9-108">일반적으로 이러한 속성에 대 한 설정을 결정 하는 작업은 로드에 대해 응용 프로그램을 실행 한 후에 발생 하므로 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> 일반적으로 응용 프로그램 구성 파일에서 요소를 사용 하 여 속성에 대 한 설정을 지정 합니다 [\<serviceThrottling>](../../configure-apps/file-schema/wcf/servicethrottling.md) .</span><span class="sxs-lookup"><span data-stu-id="646b9-108">Because determining the settings for these properties usually takes place after real-world experience running the application against loads, the settings for the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> properties is typically specified in an application configuration file using the [\<serviceThrottling>](../../configure-apps/file-schema/wcf/servicethrottling.md) element.</span></span>  
  
 <span data-ttu-id="646b9-109">다음 코드 예제에서는 애플리케이션 구성 파일에서 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> 클래스를 사용하여 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> 및 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> 속성을 1로 설정하는 간단한 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="646b9-109">The following code example shows the use of the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> class from an application configuration file that sets the <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, and <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> properties to 1 as a trivial example.</span></span> <span data-ttu-id="646b9-110">실제 경험을 통해 특정 애플리케이션에 대한 최적의 설정을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="646b9-110">Real-world experience determines the optimal settings for any particular application.</span></span>  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 <span data-ttu-id="646b9-111">정확한 런타임 동작은 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> 및 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성의 값에 따라 다르며, 이 속성은 각각 작업에서 한 번에 실행 가능한 메시지 수와 수신 채널 세션 수를 기준으로 <xref:System.ServiceModel.InstanceContext> 서비스의 수명을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="646b9-111">The exact run-time behavior depends upon the values of the <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> and <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> properties, which control how many messages can execute inside an operation at once and the lifetimes of the service <xref:System.ServiceModel.InstanceContext> relative to incoming channel sessions, respectively.</span></span>  
  
 <span data-ttu-id="646b9-112">자세한 내용은 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> 및 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="646b9-112">For details, see <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, and <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="646b9-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="646b9-113">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
