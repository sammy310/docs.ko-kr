---
description: '다음에 대 한 자세한 정보: <GCHeapAffinitizeMask> 요소'
title: GCHeapAffinitizeMask 요소
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: ea6be3fa3d973f228576db69d0700b1f7ddba585
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786982"
---
# <a name="gcheapaffinitizemask-element"></a>\<GCHeapAffinitizeMask> 요소

GC 힙과 개별 프로세서 간의 선호도를 정의 합니다.

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask>

## <a name="syntax"></a>구문

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|attribute|설명|
|---------------|-----------------|
|`enabled`|필수 특성입니다.<br /><br />GC 힙과 개별 프로세서 간의 선호도를 지정 합니다. |

#### <a name="enabled-attribute"></a>enabled 특성

|값|설명|
|-----------|-----------------|
|`nnnn`|서버 GC 힙과 개별 프로세서 간의 선호도를 정의 하는 비트 마스크를 형성 하는 10 진수 값입니다. |

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|

## <a name="remarks"></a>설명

기본적으로 서버 GC 스레드는 각 프로세서에 대해 하나의 GC 힙, 하나의 서버 GC 스레드 및 하나의 백그라운드 서버 GC 스레드를 갖도록 해당 CPU와 하드 선호도가 설정 됩니다. .NET Framework 4.6.2 부터는 **GCHeapAffinitizeMask** 요소를 사용 하 여 힙 수가 **GCHeapCount** 요소에 의해 제한 되는 경우 서버 GC 힙과 프로세서 간의 선호도를 제어할 수 있습니다.

**GCHeapAffinitizeMask** 는 일반적으로 두 개의 다른 플래그와 함께 사용 됩니다.

- [GCNoAffinitize](gcnoaffinitize-element.md)-서버 GC 스레드/힙이 cpu와 선호도가 설정 여부를 제어 합니다. `enabled` [GCNoAffinitize](gcnoaffinitize-element.md) 요소의 특성은 `false` 사용할 **GCHeapAffinitizeMask** 설정에 대해 (기본값) 여야 합니다.

- [GCHeapCount](gcheapcount-element.md)-서버 GC에 대해 프로세스에서 사용 하는 힙 수를 제한 합니다. 기본적으로 각 프로세서에 대해 하나의 힙이 있습니다.

**nnnn** 은 10 진수 값으로 표현 되는 비트 마스크입니다. 바이트 0의 비트 0은 프로세서 0, 바이트 0의 비트 1은 프로세서 1을 나타냅니다. 다음은 그 예입니다. 

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

1023 값은 0x3FF 또는 0011 1111 1111b입니다. 프로세스는 프로세서 0부터 프로세서 9까지 10 개의 프로세서를 사용 합니다.

## <a name="example"></a>예제

다음 예는 응용 프로그램에서 서버 GC를 사용 하 고 힙/스레드를 10 개 사용 함을 나타냅니다. 이러한 힙이 시스템에서 실행 되는 다른 응용 프로그램의 힙과 겹치지 않도록 하기 때문에 **GCHeapAffinitizeMask** 를 사용 하 여 프로세스에서 cpu 0 ~ 9를 사용 하도록 지정 합니다.

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [GCNoAffinitize 요소](gcnoaffinitize-element.md)
- [GCHeapCount 요소](gcheapcount-element.md)
- [가비지 컬렉션 기본 사항](../../../../standard/garbage-collection/fundamentals.md)
- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
