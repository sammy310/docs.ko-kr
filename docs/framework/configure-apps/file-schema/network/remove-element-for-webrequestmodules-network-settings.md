---
title: webRequestModules의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: 20a586e945a889d1fd8a8d4c5c09c8b790c56fc3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664024"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a>\<webRequestModules (네트워크 설정)에 대 한 > 요소 제거
응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거 합니다.  
  
 \<configuration>  
\<system.net>  
\<webRequestModules>  
\<remove>  
  
## <a name="syntax"></a>구문  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`prefix`|이 웹 요청 모듈에서 처리 하는 요청의 URI 접두사입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 요소 `remove` 는 지정 된 URI 접두사에 대해 등록 된 웹 요청 모듈을 제거 합니다.  
  
 `prefix` 특성의 값은 유효한 URI (예: "`http`" 또는 "`http://www.contoso.com`")의 선행 문자 여야 합니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

다음 예에서는 HTTP에 대 한 기존 웹 요청 모듈을 제거한 다음에 `www.contoso.com`http 요청에 대 한 새 사용자 지정 웹 요청 모듈을 등록 합니다.
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Net.WebRequest>
- [네트워크 설정 스키마](index.md)
