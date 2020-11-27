---
title: '방법: 코드에서 서비스 엔드포인트 만들기'
description: 클래스에서 서비스를 구현 하 고 프로그래밍 방식으로 끝점을 정의 하는 방법을 알아봅니다. WCF에서 끝점은 일반적으로 구성 파일에 정의 되어 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fbb22fa-2930-48b8-b437-def1de87c6a0
ms.openlocfilehash: 6f5e06154ff19129da0bce77dd70736037c2dc92
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294419"
---
# <a name="how-to-create-a-service-endpoint-in-code"></a><span data-ttu-id="3e475-104">방법: 코드에서 서비스 엔드포인트 만들기</span><span class="sxs-lookup"><span data-stu-id="3e475-104">How to: Create a Service Endpoint in Code</span></span>

<span data-ttu-id="3e475-105">이 예제에서는 계산기 서비스에 대해 `ICalculator` 계약을 정의하고, `CalculatorService` 클래스에서 서비스를 구현한 다음 코드로 엔드포인트를 정의합니다. 이 때 서비스가 <xref:System.ServiceModel.BasicHttpBinding> 클래스를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e475-105">In this example, an `ICalculator` contract is defined for a calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is defined in code, where it is specified that the service must use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="3e475-106">일반적으로 바인딩 및 주소 정보를 코드에서 명령적으로 지정하지 않고 구성에서 선언적으로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e475-106">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="3e475-107">일반적으로 배포 된 서비스에 대 한 바인딩 및 주소가 서비스를 개발 하는 동안 사용 된 것과 다르기 때문에 일반적으로 코드에서 끝점을 정의 하는 것은 실용적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e475-107">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="3e475-108">일반적으로 바인딩 및 주소 지정 정보를 코드와 구분하면 애플리케이션을 다시 컴파일하거나 다시 배포할 필요 없이 해당 정보를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e475-108">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
#### <a name="to-create-a-service-endpoint-in-code"></a><span data-ttu-id="3e475-109">코드에서 서비스 엔드포인트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="3e475-109">To create a service endpoint in code</span></span>  
  
1. <span data-ttu-id="3e475-110">서비스 계약을 정의하는 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e475-110">Create the interface that defines the service contract.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="3e475-111">1단계에서 정의한 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3e475-111">Implement the service contract defined in step 1.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. <span data-ttu-id="3e475-112">호스팅 애플리케이션에서 서비스에 사용할 바인딩 및 서비스에 대한 기본 주소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e475-112">In the hosting application, create the base address for the service and the binding to be used with the service.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. <span data-ttu-id="3e475-113">호스트를 만들고, 호스트에 대한 서비스 엔드포인트를 추가할 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=nameWithType> 또는 다른 오버로드 중 하나를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3e475-113">Create the host and call <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=nameWithType> or one of the other overloads to add the service endpoint for the host.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#6)]
     [!code-vb[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#6)]  
  
     <span data-ttu-id="3e475-114">코드에서 바인딩을 지정 하지만 런타임에서 제공 하는 기본 끝점을 사용 하려면를 만들 때 기본 주소를 생성자에 전달 하 <xref:System.ServiceModel.ServiceHost> 고를 호출 하지 마십시오 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3e475-114">To specify the binding in code but to use the default endpoints provided by the runtime, pass the base address into the constructor when creating the <xref:System.ServiceModel.ServiceHost>, and do not call <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#7)]
     [!code-vb[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#7)]  
  
     <span data-ttu-id="3e475-115">기본 끝점에 대 한 자세한 내용은 [WCF 서비스에 대 한](../samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e475-115">For more information about default endpoints, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e475-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e475-116">See also</span></span>

- [<span data-ttu-id="3e475-117">방법: 코드에서 서비스 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="3e475-117">How to: Specify a Service Binding in Code</span></span>](../how-to-specify-a-service-binding-in-code.md)
