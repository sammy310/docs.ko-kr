---
title: <Thread_UseAllCpuGroups> 요소
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 236953cc1a430a1dd2a2fbb633c7ef06e6ba200f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230839"
---
# <a name="threaduseallcpugroups-element"></a>\<Thread_UseAllCpuGroups > 요소
런타임이 모든 CPU 그룹에 관리되는 스레드를 배포할지를 지정합니다.  
  
 \<configuration>  
\<runtime>  
<Thread_UseAllCpuGroups>  
  
## <a name="syntax"></a>구문  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임이 모든 CPU 그룹에 관리되는 스레드를 배포할지를 지정합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|런타임은 여러 CPU 그룹에서 관리 되는 스레드를 분산 하지 않는 합니다. 이 값이 기본값입니다.|  
|`true`|런타임 컴퓨터에 여러 CPU 그룹이 있으면 여러 CPU 그룹에서 관리 되는 스레드를 배포 하며 [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) 요소를 사용 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 컴퓨터를 여러 CPU 그룹에이 요소를 사용 하도록 설정 하면 런타임이 모든 CPU 그룹에 관리 되는 스레드를 분산 합니다. 이 기능을 사용 하 여 설정할 수도 있습니다는 [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) 모든 CPU 그룹에 가비지 컬렉션을 확장 하 고 계정 만들기 및 힙 분산 하는 경우에 모든 코어를 사용 하는 요소입니다. 사용 하도록 설정 합니다 [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) 요소를 사용 하도록 설정 해야 합니다 [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) 요소입니다. 이러한 요소를 활성화 되지 않은 경우 사용 하도록 설정 된 `<Thread_UseAllCpuGroups>` 요소에 영향을 주지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 여러 CPU 그룹에 대 한 지원을 사용 하도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<GCCpuGroup > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
