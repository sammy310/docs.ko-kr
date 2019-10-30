---
title: <Thread_UseAllCpuGroups> 요소
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115405"
---
# <a name="thread_useallcpugroups-element"></a>\<Thread_UseAllCpuGroups > 요소

런타임이 모든 CPU 그룹에 관리되는 스레드를 배포할지를 지정합니다.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<Thread_UseAllCpuGroups >**  

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
|`false`|런타임은 여러 CPU 그룹에 관리 되는 스레드를 배포 하지 않습니다. 기본값입니다.|
|`true`|컴퓨터에 여러 CPU 그룹이 있고 [\<GCCpuGroup >](gccpugroup-element.md) 요소가 사용 하도록 설정 된 경우 런타임은 여러 cpu 그룹에 관리 되는 스레드를 배포 합니다.|

### <a name="child-elements"></a>자식 요소

없음.

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|

## <a name="remarks"></a>주의

컴퓨터에 여러 CPU 그룹이 있는 경우이 요소를 사용 하도록 설정 하면 런타임이 모든 CPU 그룹에 관리 되는 스레드를 배포 합니다. 이 기능을 사용 하려면 가비지 수집을 모든 CPU 그룹으로 확장 하 고 힙을 만들고 분산할 때 모든 코어를 고려 하는 [\<GCCpuGroup >](gccpugroup-element.md) 요소도 사용 하도록 설정 해야 합니다. [\<GCCpuGroup >](gccpugroup-element.md) 요소를 사용 하도록 설정 하려면 [\<gcServer >](gcserver-element.md) 요소를 사용 하도록 설정 해야 합니다. 이러한 요소를 사용할 수 없는 경우 `<Thread_UseAllCpuGroups>` 요소를 사용 하도록 설정 해도 아무런 효과가 없습니다.

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

## <a name="see-also"></a>참조

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- [\<GCCpuGroup > 요소](gccpugroup-element.md)
