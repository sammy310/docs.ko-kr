---
description: '자세한 정보: 방법: 프로브 요청의 검색 버전 확인'
title: '방법: 프로브 요청의 검색 버전 확인'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: c41283cb84d75dd2dbf7e86da0dec075ab8b6635
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793794"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="364a6-103">방법: 프로브 요청의 검색 버전 확인</span><span class="sxs-lookup"><span data-stu-id="364a6-103">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="364a6-104">검색 프록시는 여러 검색 버전을 사용하여 검색 엔드포인트를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364a6-104">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="364a6-105">UDP 멀티 캐스트 프로브 요청이 프록시에 도착 하면 프록시는 멀티 캐스트 비 표시 오류 메시지를 사용 하 여 응답 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="364a6-105">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="364a6-106">이를 위해 요청의 검색 버전을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="364a6-106">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="364a6-107">프로브 요청의 검색 버전을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="364a6-107">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="364a6-108">프로브 요청에 응답 하는 메서드 (예:)에서 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> 다음 코드와 같이 정적 속성을 사용 하 여을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="364a6-108">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="364a6-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="364a6-109">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="364a6-110">검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="364a6-110">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)
