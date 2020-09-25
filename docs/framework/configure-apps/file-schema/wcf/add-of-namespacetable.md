---
title: <namespaceTable>의 <add>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7d055d4933f1ad625d6842f91a140f668c05c64e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204998"
---
# <a name="add-of-namespacetable"></a>\<namespaceTable>의 \<add>

매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 구성 요소를 나타냅니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|namespace|네임스페이스를 포함하는 문자열입니다.|  
|접두사|이 네임스페이스에 대한 접두사를 포함하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
