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
ms.openlocfilehash: d3d986dae478f49504dae21b9f39574b7887b4d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202224"
---
# <a name="bypasslist-element-network-settings"></a>\<bypasslist > 요소 (네트워크 설정)
프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy>  
\<bypasslist>  
  
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
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|프록시 무시 목록에는 IP 주소 또는 DNS 이름을 추가합니다.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|무시 목록을 지웁니다.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|프록시 무시 목록에서 IP 주소 또는 DNS 이름을 제거합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.|  
  
## <a name="remarks"></a>설명  
 바이패스 목록에는 Uri를 설명 하는 정규식을 포함 하는 <xref:System.Net.WebRequest> 인스턴스에서 직접 대신의 프록시 서버를 통해 액세스 합니다.  
  
 이 요소에 대 한 정규식을 지정 하는 경우 주의 해야 합니다. 정규식 "[a-z] +\\.contoso\\.com" contoso.com 도메인에 호스트 된 일치 항목의 모든 호스트 contoso.com.cpandl.com 도메인에 일치 합니다. Contoso.com 도메인의 호스트 에서만 일치 하는 앵커 ("$") 사용 하 여: "[a-z] +\\.contoso\\.com$"입니다.  
  
 정규식에 대 한 자세한 내용은 다음을 참조 하세요. [.NET framework 정규식](../../../../../docs/standard/base-types/regular-expressions.md)합니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 바이패스 목록에 두 개의 주소를 추가합니다. 첫 번째는 contoso.com 도메인의 모든 서버에 대 한 프록시를 무시합니다. 두 번째 192.168 사용 하 여 모든 서버의 IP 주소가 시작에 대 한 프록시를 무시 합니다.  
  
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
  
## <a name="see-also"></a>참고자료

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
