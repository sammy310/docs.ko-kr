---
title: '방법: 프로브 요청의 검색 버전 확인'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 8fbc3936278a5c6f403f48b59390c69c64378004
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425263"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="1215c-102">방법: 프로브 요청의 검색 버전 확인</span><span class="sxs-lookup"><span data-stu-id="1215c-102">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="1215c-103">검색 프록시는 여러 검색 버전을 사용하여 검색 엔드포인트를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1215c-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="1215c-104">Udp 멀티 캐스트 프로브 요청이 프록시에 도착, 프록시는 멀티 캐스트 비 표시 오류 메시지를 사용 하 여 응답 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1215c-104">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="1215c-105">이 작업을 수행 하기 위해 했을 때 요청의 검색 버전을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1215c-105">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="1215c-106">프로브 요청의 검색 버전을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="1215c-106">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="1215c-107">프로브 요청에 응답 하는 방법에 (예를 들어 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) 정적을 사용 하 여 <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> 검색할 속성을 <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>다음 코드에 표시 된 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="1215c-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="1215c-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="1215c-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="1215c-109">검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="1215c-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
