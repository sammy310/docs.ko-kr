---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772413"
---
# <a name="namespacetable"></a>\<namespaceTable>

매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.

**\<system.serviceModel>**   
&nbsp;&nbsp;**\<routing>**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**
  
## <a name="syntax"></a>구문  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [**\<filter>**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | XPath 식에 사용되는 네임스페이스 접두사 매핑을 정의합니다. |

### <a name="parent-elements"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<routing>**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다<xref:System.ServiceModel.Dispatcher.MessageFilter> 사용할 대상 끝점을 정의 하는 들어오는 메시지를 평가할 수 있을 뿐만 아니라 라우팅 테이블 필터가 일치할 때에 메시지를 보냅니다. |

## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
