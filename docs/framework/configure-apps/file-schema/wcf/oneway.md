---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: a5c773ea91de882920775ac8dc0ecc1da68a6c9f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738794"
---
# <a name="oneway"></a>\<oneWay >
사용자 지정 바인딩에 대한 패킷 라우팅 및 단방향 메서드를 사용하도록 설정합니다.  
  
[ **\<configuration>** ](../configuration-element.md)\
[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; \
&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**oneWay >**  
  
## <a name="syntax"></a>구문  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`packetRoutable`|패킷 라우팅 활성화 여부를 나타내는 부울 값입니다. 기본값은 `false`입니다.|  
|`MaxAcceptedChannels`|수락할 수 있는 최대 채널 수를 지정하는 정수입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<channelPoolSettings >](channelpoolsettings.md)|현재 채널의 채널 풀 속성을 포함하는 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> 개체입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<binding >](bindings.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## <a name="remarks"></a>주의  
 패킷 라우팅을 사용하려면 이 요소에서 제공하는 단방향 변환 계층이 필요합니다. 사용자는 세션 인식 또는 요청-회신 전송에 대해이 바인딩을 계층으로 지정 하 여 패킷을 라우팅할 수 있도록 하는 사용자 지정 바인딩을 만들 수 있습니다. 이 요소는 원래의 방식으로 단방향 메서드를 노출하려는 경우에도 유용합니다. 복합 이중 및 안정적인 메시징과 같이이 계층에 더 많은 변환을 적용할 수 있습니다.  
  
## <a name="see-also"></a>참조

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [바인딩](../../../wcf/bindings.md)
- [바인딩 확장](../../../wcf/extending/extending-bindings.md)
- [사용자 지정 바인딩](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
