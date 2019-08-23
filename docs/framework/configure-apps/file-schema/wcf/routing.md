---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 3c7e9cb1284ab55c8dd199d9fb47a223698814f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934133"
---
# <a name="routing"></a>\<라우팅 >

들어오는 메시지를 평가할 때 사용 되는 WCF <xref:System.ServiceModel.Dispatcher.MessageFilter> (Windows Communication Foundation 형식 및 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다. 필터가 일치 하는 경우에 메시지를 보냅니다.

[ **\<system.serviceModel>** ](system-servicemodel.md)   
&nbsp;&nbsp; **\<routing>**
  
## <a name="syntax"></a>구문  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String"
               filterName="String"
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

|     | Description |
| --- | ----------- |
| [ **\<filters>** ](filters-of-routing.md) | 들어오는 메시지를 평가할 때 사용 되는 Windows Communication Foundation (WCF) MessageFilter 유형을 결정 하는 라우팅 필터 집합을 포함 합니다. |
| [ **\<filterTables>** ](filtertables.md) | 필터가 일치할 때 사용할 엔드포인트를 지정하기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함합니다. |

### <a name="parent-elements"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| **\<system.ServiceModel>** | 모든 WCF 구성 요소의 루트 요소입니다. |

## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
