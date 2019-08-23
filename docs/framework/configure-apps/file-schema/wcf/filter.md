---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 68de255b9f11dc4377159d1cc3efa575633db316
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918890"
---
# <a name="filter"></a>\<filter>

들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 형식)<xref:System.ServiceModel.Dispatcher.MessageFilter> 와 필터에 필요한 지원 데이터 나 매개 변수를 결정 하는 라우팅 필터를 정의 합니다.

\<system.serviceModel> \<routing> \<filters> \<filter>
  
## <a name="syntax"></a>구문  
  
```xml  
<routing>
  <filters>
    <filter customType="String"
            filterData="String"
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
            name="String" />
  </filters>
</routing>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

| 특성  | Description |
| ---------- | ----------- |
| customType | 필터로 사용할 사용자 지정 형식의 정규화된 형식 이름을 포함하는 문자열입니다. 가 `filterType` 로`custom`설정 된 경우이 특성은 만들 클래스의 정규화 된 형식 이름을 포함 합니다.  `filterData`사용자 지정 형식 필터를 평가 하는 동안 사용할 값도 포함할 수 있습니다. |
| filterData | 필터 데이터를 포함하는 문자열입니다. 이 특성을 지정하는 방법에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요. |
| filterType | 필터 형식을 포함하는 문자열입니다. 이 특성은 <xref:System.ServiceModel.Routing.Configuration.FilterType> 형식입니다.  `filterData` 특성에서 이 형식이 어떻게 작동하는지에 대한 자세한 내용은 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>를 참조하세요. |
| name       | 이 필터 요소의 고유 이름을 포함하는 문자열입니다. |

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

| 요소 | Description |
| ------- | ----------- |
| [\<routing>](routing.md) | 들어오는 메시지를 평가할 때 사용할 WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> (Windows Communication Foundation 유형을 결정 하는 라우팅 필터 집합을 정의 하는 구성 섹션입니다. |

## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
