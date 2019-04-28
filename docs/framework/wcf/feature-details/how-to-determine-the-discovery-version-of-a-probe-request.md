---
title: '방법: 프로브 요청의 검색 버전 확인'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 6bd112be311eb9397ad89801be5358d67c7499fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773180"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="818b0-102">방법: 프로브 요청의 검색 버전 확인</span><span class="sxs-lookup"><span data-stu-id="818b0-102">How to:Determine the Discovery Version of a Probe Request</span></span>
<span data-ttu-id="818b0-103">검색 프록시는 여러 검색 버전을 사용하여 검색 엔드포인트를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818b0-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="818b0-104">UDP 멀티캐스트 프로브 요청이 프록시에 도달하면 프록시는 멀티캐스트 비표시 오류(Suppression) 메시지로 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="818b0-104">When a UDP multicast Probe request arrives at the proxy the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="818b0-105">이렇게 응답하려면 요청의 검색 버전을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="818b0-105">In order to do this it would have to know the discovery version of the request.</span></span>  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="818b0-106">프로브 요청의 검색 버전을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="818b0-106">To Determine the Discovery Version of a Probe Request</span></span>  
  
1. <span data-ttu-id="818b0-107">프로브 요청(예: <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>)에 응답하는 메서드에서 다음 코드와 같이 정적 <xref:System.ServiceModel.OperationContext.Current%2A> 속성을 사용하여 <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="818b0-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use the static <xref:System.ServiceModel.OperationContext.Current%2A> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> as shown in the following code.</span></span>  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="818b0-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="818b0-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="818b0-109">검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="818b0-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
