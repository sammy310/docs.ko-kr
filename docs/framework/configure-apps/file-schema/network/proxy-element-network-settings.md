---
title: <proxy> 요소(네트워크 설정)
description: <proxy>네트워크 설정 요소는 .NET Framework의 프록시 서버 옵션을 정의 합니다. 이 문서에는 예제가 포함 되어 있습니다.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 54b324dcd27d5827159bc2d773365e388a367d26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190217"
---
# <a name="proxy-element-network-settings"></a>\<proxy> 요소(네트워크 설정)

프록시 서버를 정의합니다.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a>구문  
  
```xml  
<proxy
  autoDetect="True|False|Unspecified"
  bypassonlocal="True|False|Unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="True|False|Unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**Attribute**|**설명**|  
|-------------------|---------------------|  
|`autoDetect`|프록시를 자동으로 검색할지 여부를 지정합니다. 기본값은 `Unspecified`입니다.|  
|`bypassonlocal`|로컬 리소스에 프록시가 사용되지 않는지 여부를 지정합니다. 로컬 리소스에는 로컬 서버 ( `http://localhost` , `http://loopback` 또는 `http://127.0.0.1` )와 마침표 없는 URI ()가 포함 `http://webserver` 됩니다. 기본값은 `Unspecified`입니다.|  
|`proxyaddress`|사용할 프록시 URI를 지정 합니다.|  
|`scriptLocation`|구성 스크립트의 위치를 지정 합니다. 이 특성에는 특성을 사용 하지 마십시오 `bypassonlocal` . |  
|`usesystemdefault`|Internet Explorer 프록시 설정을 사용할지 여부를 지정 합니다. 로 설정 되 면 `True` 후속 특성이 Internet Explorer 프록시 설정을 재정의 합니다. 기본값은 `Unspecified`입니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.|  
  
## <a name="text-value"></a>텍스트 값  
  
## <a name="remarks"></a>설명  

 `proxy`요소는 응용 프로그램에 대 한 프록시 서버를 정의 합니다. 이 요소가 구성 파일에 없는 경우 .NET Framework는 Internet Explorer의 프록시 설정을 사용 합니다.  
  
 특성 값은 `proxyaddress` 올바른 형식의 URI (Uniform Resource identifier) 여야 합니다.  
  
 `scriptLocation`특성은 프록시 구성 스크립트의 자동 검색을 참조 합니다. <xref:System.Net.WebProxy>Internet Explorer에서 **자동 구성 스크립트 사용** 옵션을 선택 하면 클래스는 구성 스크립트 (일반적으로 이름이 지정 된 Wpad .dat)를 찾으려고 시도 합니다. `bypassonlocal`이 값으로 설정 된 경우 `scriptLocation` 는 무시 됩니다.
  
 `usesystemdefault`버전 2.0로 마이그레이션하는 .NET Framework 버전 1.1 응용 프로그램의 경우 특성을 사용 합니다.  
  
 `proxyaddress`특성이 잘못 된 기본 프록시를 지정 하는 경우 예외가 throw 됩니다. 예외의 <xref:System.Exception.InnerException%2A> 속성에는 오류의 근본 원인에 대한 추가 정보가 있어야 합니다.  
  
## <a name="configuration-files"></a>구성 파일  

 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 Internet Explorer 프록시의 기본값을 사용 하 고, 프록시 주소를 지정 하 고, 로컬 액세스를 위해 프록시를 무시 합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [네트워크 설정 스키마](index.md)
