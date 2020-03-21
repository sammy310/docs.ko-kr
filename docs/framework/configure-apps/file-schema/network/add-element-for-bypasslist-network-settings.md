---
title: bypasslist의 <add> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155079"
---
# <a name="add-element-for-bypasslist-network-settings"></a>\<바이패스리스트에> 요소 추가(네트워크 설정)
프록시 바이패스 목록에 IP 주소 또는 DNS 이름을 추가합니다.  
  
[**\<구성>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<기본 프록시>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<바이패스리스트>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**  
  
## <a name="syntax"></a>구문  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|**주소**|IP 주소 또는 DNS 이름을 설명하는 정규식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[bypasslist](bypasslist-element-network-settings.md)|프록시를 사용하지 않는 주소를 설명하는 정규식 집합을 제공합니다.|  
  
## <a name="remarks"></a>설명  
 이 `add` 요소는 IP 주소 또는 DNS 서버 이름을 설명하는 정규식을 프록시 서버를 우회하는 주소 목록에 삽입합니다.  
  
 특성값은 `address` IP 주소 또는 호스트 이름 집합을 설명하는 정규식이어야 합니다.  
  
 이 요소에 대한 정규식을 지정할 때는 주의해야 합니다. 정규표현식 "[a-z]+\\.contoso.com"은\\contoso.com 도메인의 모든 호스트와 일치하지만 contoso.com.cpandl.com 도메인의 모든 호스트와도 일치합니다. contoso.com 도메인의 호스트만 일치하려면 "a-z]+\\.contoso\\.com$"을 앵커("$")를 사용합니다.  
  
 정규식에 대한 자세한 내용은 을 참조하십시오. [.NET 프레임워크 정규 표현식](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 바이패스 목록에 두 개의 주소를 추가합니다. 첫 번째는 contoso.com 도메인의 모든 서버에 대한 프록시를 무시합니다. 두 번째는 IP 주소가 192.168로 시작하는 모든 서버의 프록시를 무시합니다.  
  
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
