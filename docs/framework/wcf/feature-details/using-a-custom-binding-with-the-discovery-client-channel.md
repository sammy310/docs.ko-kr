---
title: Discovery 클라이언트 채널을 통해 사용자 지정 바인딩 사용
ms.date: 03/30/2017
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
ms.openlocfilehash: 6fe9370bb22ca424774fc8cb4566e0802bc06697
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918621"
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="f4c5d-102">Discovery 클라이언트 채널을 통해 사용자 지정 바인딩 사용</span><span class="sxs-lookup"><span data-stu-id="f4c5d-102">Using a Custom Binding with the Discovery Client Channel</span></span>
<span data-ttu-id="f4c5d-103"><xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>와 함께 사용자 지정 바인딩을 사용하는 경우 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 인스턴스를 만드는 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c5d-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="f4c5d-104">DiscoveryEndpointProvider 만들기</span><span class="sxs-lookup"><span data-stu-id="f4c5d-104">Creating a DiscoveryEndpointProvider</span></span>  
 <span data-ttu-id="f4c5d-105">합니다 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 담당 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> 주문형 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f4c5d-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="f4c5d-106">검색 엔드포인트 공급자를 정의하려면 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>에서 클래스를 파생시키고 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> 메서드를 재정의한 다음 새 검색 엔드포인트를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f4c5d-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="f4c5d-107">다음 예제에서는 검색 엔드포인트 공급자를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4c5d-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
// to the DiscoveryClientBindingElement. The Discovery ClientChannel   
// uses this endpoint to send Probe message.  
public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
{  
   public override DiscoveryEndpoint GetDiscoveryEndpoint()  
   {  
      return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
   }  
}  
```  
  
 <span data-ttu-id="f4c5d-108">검색 엔드포인트 공급자를 정의한 후에는 다음 예제와 같이 사용자 지정 바인딩을 만들고 검색 엔드포인트 공급자를 참조하는 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4c5d-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
```  
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 <span data-ttu-id="f4c5d-109">Discovery 클라이언트 채널을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [Discovery 클라이언트 채널을 사용 하 여](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="f4c5d-109">For more information about using the discovery client channel, see [Using the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f4c5d-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="f4c5d-110">See also</span></span>

- [<span data-ttu-id="f4c5d-111">WCF 검색 개요</span><span class="sxs-lookup"><span data-stu-id="f4c5d-111">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="f4c5d-112">검색 클라이언트 채널 사용</span><span class="sxs-lookup"><span data-stu-id="f4c5d-112">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
