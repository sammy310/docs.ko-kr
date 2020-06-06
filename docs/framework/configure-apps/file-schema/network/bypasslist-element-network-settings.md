---
title: <bypasslist> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154948"
---
# <a name="bypasslist-element-network-settings"></a>\<bypasslist> 요소(네트워크 설정)
프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**

## <a name="syntax"></a>구문  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[추가](add-element-for-bypasslist-network-settings.md)|프록시 무시 목록에 IP 주소 또는 DNS 이름을 추가 합니다.|  
|[해제](clear-element-for-bypasslist-network-settings.md)|바이패스 목록을 지웁니다.|  
|[remove](remove-element-for-bypasslist-network-settings.md)|프록시 바이패스 목록에서 IP 주소 또는 DNS 이름을 제거 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.|  
  
## <a name="remarks"></a>설명  
 바이패스 목록에는 <xref:System.Net.WebRequest> 인스턴스가 프록시 서버를 통하지 않고 직접 액세스 하는 uri를 설명 하는 정규식이 포함 되어 있습니다.  
  
 이 요소에 대 한 정규식을 지정할 때는 주의 해야 합니다. 정규식 "[a-z] + \\ . \\ .com"은 contoso.com 도메인의 모든 호스트와 일치 하지만 contoso.com.cpandl.com 도메인의 모든 호스트와 일치 합니다. Contoso.com 도메인의 호스트만 일치 시키려면 앵커 ("$"): "[a-z] + \\ . contoso \\ $"를 사용 합니다.  
  
 정규식에 대 한 자세한 내용은을 참조 하십시오. [정규식을 .NET Framework](../../../../standard/base-types/regular-expressions.md)합니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 바이패스 목록에 두 개의 주소를 추가 합니다. 첫 번째는 contoso.com 도메인에 있는 모든 서버에 대 한 프록시를 무시 합니다. 두 번째는 IP 주소가 192.168으로 시작 하는 모든 서버에 대해 프록시를 무시 합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [네트워크 설정 스키마](index.md)
