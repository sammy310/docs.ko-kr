---
title: <proxy> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154792"
---
# <a name="proxy-element-network-settings"></a>\<프록시> 요소(네트워크 설정)
프록시 서버를 정의합니다.  

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<기본 프록시>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<프록시>**

## <a name="syntax"></a>구문  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`autoDetect`|프록시를 자동으로 검색할지 여부를 지정합니다. 기본값은 `unspecified`입니다.|  
|`bypassonlocal`|로컬 리소스에 프록시가 사용되지 않는지 여부를 지정합니다. 로컬 리소스에는 로컬`http://localhost` `http://loopback`서버(또는) `http://127.0.0.1`및 마침표가`http://webserver`없는 URI()가 포함됩니다. 기본값은 `unspecified`입니다.|  
|`proxyaddress`|사용할 프록시 URI를 지정합니다.|  
|`scriptLocation`|구성 스크립트의 위치를 지정합니다. 이 특성과 `bypassonlocal` 함께 특성을 사용하지 마십시오. |  
|`usesystemdefault`|Internet Explorer 프록시 설정을 사용할지 여부를 지정합니다. `true`을 설정하면 후속 특성이 Internet Explorer 프록시 설정을 덮어놓습니다. 기본값은 `unspecified`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[기본 프록시](defaultproxy-element-network-settings.md)|HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.|  
  
## <a name="text-value"></a>텍스트 값  
  
## <a name="remarks"></a>설명  
 요소는 `proxy` 응용 프로그램에 대 한 프록시 서버를 정의 합니다. 구성 파일에서 이 요소가 누락된 경우 .NET Framework는 Internet Explorer의 프록시 설정을 사용합니다.  
  
 특성의 `proxyaddress` 값은 잘 구성된 균일 리소스 표시기(URI)여야 합니다.  
  
 특성은 `scriptLocation` 프록시 구성 스크립트의 자동 검색을 나타냅니다. 클래스는 <xref:System.Net.WebProxy> Internet Explorer에서 **자동 구성** 스크립트 사용 옵션을 선택하면 구성 스크립트(일반적으로 Wpad.dat)를 찾으려고 시도합니다. 값으로 설정된 경우 `bypassonlocal` `scriptLocation` 무시됩니다.
  
 버전 `usesystemdefault` 2.0으로 마이그레이션하는 .NET Framework 버전 1.1 응용 프로그램에 대한 특성을 사용합니다.  
  
 `proxyaddress` 특성이 잘못된 기본 프록시를 지정하면 예외가 throw됩니다. 예외의 <xref:System.Exception.InnerException%2A> 속성에는 오류의 근본 원인에 대한 추가 정보가 있어야 합니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 Internet Explorer 프록시의 기본값을 사용하고, 프록시 주소를 지정하고, 로컬 액세스에 대한 프록시를 무시합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [네트워크 설정 스키마](index.md)
