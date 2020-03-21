---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 0673507b72690c3a5c7dcc35442c05e378dba43c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153037"
---
# <a name="baseaddressprefixfilters"></a>\<베이스주소사전수정필터>
IIS에서 Windows 통신 재단(WCF) 응용 프로그램을 호스팅할 때 적절한 IIS(인터넷 정보 서비스) 바인딩을 선택하는 메커니즘을 제공하는 필터통과를 지정하는 구성 요소 컬렉션을 나타냅니다.  
  
> [!WARNING]
> \<baseAddressPrefix필터> "로컬 호스트"를 인식하지 못합니다. 대신 정규화된 컴퓨터 이름을 사용합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.service모델>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<서비스호스팅환경>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<베이스주소사전필터>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<>추가](add-of-baseaddressprefixfilter.md)|서비스 호스트에서 사용하는 기본 주소에 대한 접두사 필터를 지정하는 구성 요소를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<서비스호스팅환경>](servicehostingenvironment.md)|특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.|  
  
## <a name="remarks"></a>설명  
 접두사 필터는 공유 호스팅 공급자가 서비스에 사용될 URI를 지정하는 방법을 제공합니다. 이 방법을 사용하면 공유 호스트가 동일한 사이트의 동일한 체계에 대해 기본 주소가 다른 여러 애플리케이션을 호스트할 수 있습니다.  
  
 IIS 웹 사이트는 가상 디렉터리를 포함하는 가상 애플리케이션의 컨테이너입니다. 사이트의 애플리케이션은 하나 이상의 IIS 바인딩을 통해 액세스될 수 있습니다. IIS 바인딩은 바인딩 프로토콜과 바인딩 정보라는 두 가지 정보를 제공합니다. 바인딩 프로토콜(예: HTTP)은 통신이 이루어지는 체계를 정의하며, 바인딩 정보(예: IP 주소, 포트, Hostheader)는 사이트 액세스에 사용되는 데이터를 포함합니다.  
  
 IIS에서는 각 사이트에 대해 여러 개의 IIS 바인딩을 지정할 수 있으므로, 각 체계에 대해 여러 개의 기본 주소가 생성됩니다. 사이트에서 호스팅되는 WCF 서비스는 각 스키마에 대해 하나의 기본 주소만 바인딩할 수 있으므로 접두사 필터 기능을 사용하여 호스팅된 서비스의 필수 기본 주소를 선택할 수 있습니다. IIS에서 제공하는 들어오는 기본 주소는 선택적 접두사 목록 필터를 기반으로 필터링됩니다.  
  
 예를 들어 사이트에 다음과 같은 기본 주소가 포함될 수 있습니다.
  
```
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 다음 구성 파일을 사용하여 appdomain 수준에서 접두사 필터를 지정할 수 있습니다.  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 이 예제에서 `net.tcp://test1.fabrikam.com:8000` 및 `http://test2.fabrikam.com:9000`은 해당 체계에서 통과되도록 허용된 유일한 기본 주소입니다.  
  
 기본적으로, 접두사가 지정되지 않으면 모든 주소가 통과됩니다. 접두사를 지정하면 해당 체계에서 일치하는 기본 주소만 통과됩니다.  
  
> [!NOTE]
> 필터는 와일드카드를 지원하지 않습니다. 또한 IIS에서 제공하는 baseAddress는 `baseAddressPrefixFilters` 목록에 없는 다른 체계에 바인딩되는 주소를 가질 수 있습니다. 이러한 주소는 필터링되지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [호스팅](../../../wcf/feature-details/hosting.md)
