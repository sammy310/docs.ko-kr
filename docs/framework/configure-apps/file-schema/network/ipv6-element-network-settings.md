---
title: <ipv6> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: c16949171d082bd02abb0a02db83c2e71c2f17df
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088127"
---
# <a name="ipv6-element-network-settings"></a>\<ipv6> 요소(네트워크 설정)
<xref:System.Net.Dns> 클래스의 사용 되지 않는 멤버의 IPv6 (인터넷 프로토콜 버전 6) 응답을 사용 하도록 설정 합니다.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<설정**](settings-element-network-settings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ipv6 >**

## <a name="syntax"></a>구문  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`enabled`|<xref:System.Net.Dns> 클래스의 멤버가 IPv6 (인터넷 프로토콜 버전 6) 주소를 반환 하는지 여부를 지정 합니다. 기본값은 `false`여야 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음.  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[설정](settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## <a name="remarks"></a>주의  
 이 설정은 <xref:System.Net.Dns> 클래스의 사용 되지 않는 멤버 (<xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, <xref:System.Net.Dns.Resolve%2A>에 대 한 IPv6 지원을 사용 하도록 설정 합니다. <xref:System.Net?displayProperty=nameWithType> 네임 스페이스의 다른 구성원의 경우 운영 체제에서 i p v 6을 사용 하도록 설정 하면 IPv6 주소가 반환 될 수 있습니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Net.Dns> 클래스에 대 한 IPv6 지원을 사용 하도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참조

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [네트워크 설정 스키마](index.md)
