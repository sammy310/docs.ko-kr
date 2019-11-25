---
title: authenticationModules의 <remove> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
ms.openlocfilehash: 2113b2b81ae347b398b0f25028dc6c361aec8447
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089175"
---
# <a name="remove-element-for-authenticationmodules-network-settings"></a>authenticationModules (네트워크 설정)에 대 한 > 요소 \<제거
응용 프로그램에서 인증 모듈을 제거 합니다.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**authenticationModules**](authenticationmodules-element-network-settings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<제거 >**

## <a name="syntax"></a>구문  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|**type**|제거할 인증 모듈의 이름입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음.  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[Authenticationmodules>](authenticationmodules-element-network-settings.md)|네트워크 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 `remove` 요소는 구성 파일에서 이전에 정의 되었거나 구성 계층 구조에서 상위 수준에 정의 된 인증 모듈을 제거 합니다.  
  
 `type` 특성에 대 한 값은 올바른 클래스 이름 이어야 합니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 인증 모듈을 제거 합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참조

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [네트워크 설정 스키마](index.md)
