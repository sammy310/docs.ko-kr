---
title: <system.Net> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154558"
---
# <a name="systemnet-element-network-settings"></a>\<system.Net> 요소(네트워크 설정)
.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.  
  
[**\<구성>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[authenticationModules](authenticationmodules-element-network-settings.md)|인터넷 요청을 인증하는 데 사용되는 모듈을 지정합니다.|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|인터넷 호스트에 대한 최대 연결 수를 지정합니다.|  
|[기본 프록시](defaultproxy-element-network-settings.md)|HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.|  
|[메일 설정](mailsettings-element-network-settings.md)|간단한 메일 전송 프로토콜(SMTP) 메일 전송 옵션을 구성합니다.|  
|[requestCaching](requestcaching-element-network-settings.md)|네트워크 요청에 대한 캐싱 메커니즘을 제어합니다.|  
|[설정](settings-element-network-settings.md)|<xref:System.Net> 하위 네임스페이스 및 관련 하위 네임스페이스의 클래스에 대한 기본 네트워크 옵션을 구성합니다.|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|인터넷 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[구성](../configuration-element.md)|모든 네임스페이스에 대한 설정을 포함합니다.|  
  
## <a name="remarks"></a>설명  
 [ \<system.net>](system-net-element-network-settings.md) 요소에는 하위 네임스페이스및 관련 하위 네임스페이스의 클래스에 대한 설정이 <xref:System.Net> 포함되어 있습니다. 설정은 인터넷 호스트로부터 정보를 수신하기 위한 인증 모듈, 연결 관리, 메일 설정, 프록시 서버 및 인터넷 요청 모듈을 구성합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 클래스에서 사용하는 <xref:System.Net> 일반적인 구성을 보여 주며 있습니다.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [네트워크 설정 스키마](index.md)
