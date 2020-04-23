---
title: <GCCpuGroup> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102894"
---
# <a name="gccpugroup-element"></a>\<GCCpu그룹> 요소

가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpu그룹>**

## <a name="syntax"></a>구문

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|attribute|Description|
|---------------|-----------------|
|`enabled`|필수 특성입니다.<br /><br /> 가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.|

## <a name="enabled-attribute"></a>enabled 특성

|값|Description|
|-----------|-----------------|
|`false`|가비지 수집은 여러 CPU 그룹을 지원하지 않습니다. 이것이 기본값입니다.|
|`true`|가비지 수집은 서버 가비지 수집이 활성화된 경우 여러 CPU 그룹을 지원합니다.|

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|Description|
|-------------|-----------------|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|

## <a name="remarks"></a>설명

컴퓨터에 여러 CPU 그룹이 있고 서버 가비지 수집이 활성화된 [ \<경우(gcServer>](gcserver-element.md) 요소 참조) 이 요소를 사용하면 모든 CPU 그룹에 걸쳐 가비지 수집이 확장되고 힙을 만들고 균형을 잡을 때 모든 코어가 고려됩니다.

> [!NOTE]
> 이 요소는 가비지 수집 스레드에만 적용됩니다. 런타임이 모든 CPU 그룹에 사용자 스레드를 배포할 수 있도록 하려면 [ \<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) 요소도 사용하도록 설정해야 합니다.

## <a name="example"></a>예제

다음 예제에서는 여러 CPU 그룹에 대해 가비지 수집을 사용하도록 설정하는 방법을 보여 주었습니다.

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>참고 항목

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- [동시 가비지 수집 사용 안 함](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [워크스테이션 및 서버 가비지 수집](../../../../standard/garbage-collection/workstation-server-gc.md)
