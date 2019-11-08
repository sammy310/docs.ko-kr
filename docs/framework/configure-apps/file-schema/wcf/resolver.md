---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738735"
---
# <a name="resolver"></a>\<해결 프로그램 >
피어 메시 ID를 확인하는 데 사용되는 피어 확인자를 메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 지정합니다.  
  
[ **\<configuration>** ](../configuration-element.md)\
[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; \
&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**해결 프로그램 >**  
  
## <a name="syntax"></a>구문  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`mode`|이 서비스와 연결된 피어 확인자 인스턴스가 PNRP 관련 사용자 지정 확인자인지 아니면 자동으로 결정되는지 여부를 지정하는 문자열입니다. 이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode> 형식입니다.|  
|`referralPolicy`|피어 간에 조회를 공유하는 방법을 지정하는 문자열입니다. 이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<헤더 >](headers.md)|사용자 지정 피어 확인자 서비스의 설정을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<binding >](bindings.md)|[\<netPeerTcpBinding >](netpeertcpbinding.md)의 모든 바인딩 기능을 정의 합니다.|  
  
## <a name="remarks"></a>주의  
 피어 이름 확인자는 피어 메시에 참여하는 피어 노드를 찾기 위해 피어 채널에서 사용하는 검색 서비스입니다. 피어 메시를 사용 하 여 노드를 "등록" 하는 데도 사용 됩니다 .이 메커니즘은 피어 노드가 알려지고 피어 메시에 서 사용할 수 있게 되는 메커니즘입니다. 피어 확인자에 대 한 자세한 내용은 [피어 확인자](../../../wcf/feature-details/peer-resolvers.md)를 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [피어 확인자](../../../wcf/feature-details/peer-resolvers.md)
- [PeerChannel 응용 프로그램에 사용자 지정 해결 프로그램 추가](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))
