---
title: '방법: 프로브 요청의 검색 버전 확인'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 2b7e42714ae1d16a84bcb6f0fc79cf5b376a7a16
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595416"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>방법: 프로브 요청의 검색 버전 확인

검색 프록시는 여러 검색 버전을 사용하여 검색 엔드포인트를 노출할 수 있습니다. UDP 멀티 캐스트 프로브 요청이 프록시에 도착 하면 프록시는 멀티 캐스트 비 표시 오류 메시지를 사용 하 여 응답 해야 합니다. 이를 위해 요청의 검색 버전을 알아야 합니다.

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a>프로브 요청의 검색 버전을 확인하려면

프로브 요청에 응답 하는 메서드 (예:)에서 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> 다음 코드와 같이 정적 속성을 사용 하 여을 검색 합니다.

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [검색 프록시 구현](implementing-a-discovery-proxy.md)
