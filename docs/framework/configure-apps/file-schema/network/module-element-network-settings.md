---
title: <module> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: ad641f93e93f627dae1c7d0bda4620093c4567b2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205050"
---
# <a name="module-element-network-settings"></a>\<module> 요소(네트워크 설정)

애플리케이션에 새 프록시 모듈을 추가합니다.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**

## <a name="syntax"></a>구문  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**Attribute**|**설명**|  
|-------------------|---------------------|  
|`type`|속성으로 표시 되는 정규화 된 형식 이름 <xref:System.Type.FullName%2A> 및 속성으로 표시 되는 어셈블리 이름 (속성으로 표시 <xref:System.Reflection.Assembly.FullName%2A> 됨)을 쉼표로 구분 하 여 프록시를 구현 합니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.|  
  
## <a name="remarks"></a>설명  

 `module`요소는 인터페이스를 구현 하는 프록시 클래스를 등록 <xref:System.Net.IWebProxy> 합니다. 프록시 클래스를 등록한 다음에는 `module`을 사용하여 지원 프록시를 통해 정보를 요청할 수 있습니다.  
  
 특성의 값은 `type` 모듈의 클래스 이름과 해당 DLL (동적 연결 라이브러리)의 이름 이어야 합니다.  
  
## <a name="configuration-files"></a>구성 파일  

 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 사용자 지정 프록시 클래스를 등록 합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [네트워크 설정 스키마](index.md)
