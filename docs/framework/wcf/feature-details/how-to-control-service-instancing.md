---
title: '방법: 서비스 인스턴스 만들기 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: b028e062acd47118314c9fafd18dd698d04ec244
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257264"
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="68966-102">방법: 서비스 인스턴스 만들기 제어</span><span class="sxs-lookup"><span data-stu-id="68966-102">How to: Control Service Instancing</span></span>

<span data-ttu-id="68966-103">서비스의 인스턴스 모드를 설정하면 <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>(및 연결된 사용자 정의 서비스 개체)가 만들어지는 시기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68966-103">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="68966-104">가능한 모드에 대해서는 <xref:System.ServiceModel.InstanceContextMode> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68966-104">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> <span data-ttu-id="68966-105">동작에 대 한 자세한 내용은 [동작을 사용 하 여 런타임 구성 및 확장](../extending/configuring-and-extending-the-runtime-with-behaviors.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68966-105">For more information about behaviors, see [Configuring and Extending the Runtime with Behaviors](../extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="68966-106">작업 예제를 보려면 [동작](../samples/behaviors.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68966-106">For working examples, see [Behaviors](../samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="68966-107">코드를 사용하여 서비스 인스턴스 수명을 제어하려면</span><span class="sxs-lookup"><span data-stu-id="68966-107">To control the service instance lifetime using code</span></span>  
  
1. <span data-ttu-id="68966-108">서비스 클래스에 <xref:System.ServiceModel.ServiceBehaviorAttribute>를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="68966-108">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2. <span data-ttu-id="68966-109"><xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성을 <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> 또는 <xref:System.ServiceModel.InstanceContextMode.Single> 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68966-109">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="68966-110">예제</span><span class="sxs-lookup"><span data-stu-id="68966-110">Example</span></span>  

 <span data-ttu-id="68966-111">다음 코드 예제에서는 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 특성의 <xref:System.ServiceModel.ServiceBehaviorAttribute> 속성을 <xref:System.ServiceModel.InstanceContextMode.PerCall>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68966-111">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="68966-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68966-112">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [<span data-ttu-id="68966-113">서비스: 동작 샘플</span><span class="sxs-lookup"><span data-stu-id="68966-113">Service: Behaviors Samples</span></span>](../samples/behaviors.md)
