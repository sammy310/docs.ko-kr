---
title: GCHeapCount 요소
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283080"
---
# <a name="gcheapcount-element"></a>\<GCHeapCount > 요소

서버 가비지 수집에 사용할 힙/스레드 수를 지정 합니다.

\<configuration>\
&nbsp;&nbsp;\<런타임 > \
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount >

## <a name="syntax"></a>구문

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|`enabled`|필수 특성입니다.<br /><br />서버 가비지 수집에 사용할 힙 수를 지정 합니다. 실제 힙 수는 사용자가 지정 하는 힙 수와 프로세스에서 사용할 수 있는 프로세서 수의 최소값입니다. |

#### <a name="enabled-attribute"></a>enabled 특성

|값|설명|
|-----------|-----------------|
|`nn`|서버 GC에 사용할 힙 수입니다.|

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|

## <a name="remarks"></a>설명

기본적으로 서버 GC 스레드는 각 프로세서에 대해 하나의 GC 힙, 하나의 서버 GC 스레드 및 하나의 백그라운드 서버 GC 스레드를 갖도록 해당 CPU와 하드 선호도가 설정 됩니다. .NET Framework 4.6.2부터 **GCHeapCount** 요소를 사용 하 여 응용 프로그램에서 서버 GC에 사용 하는 힙 수를 제한할 수 있습니다. 서버 GC에 사용 되는 힙 수를 제한 하는 것은 서버 응용 프로그램의 여러 인스턴스를 실행 하는 시스템에 특히 유용 합니다.

**GCHeapCount** 는 일반적으로 두 개의 다른 플래그와 함께 사용 됩니다.

- [GCNoAffinitize](gcnoaffinitize-element.md)-서버 GC 스레드/힙이 cpu와 선호도가 설정 여부를 제어 합니다.

- [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)-cpu를 사용 하 여 GC 스레드/힙의 선호도를 제어 합니다.

**GCHeapCount** 를 설정 하 고 **GCNoAffinitize** 를 사용 하지 않도록 설정 하면 (기본 설정) *nn* GC 스레드/힙과 첫 번째 *nn* 프로세서 간에 선호도가 있습니다. **GCHeapAffinitizeMask** 요소를 사용 하 여 프로세스의 서버 GC 힙에서 사용 되는 프로세서를 지정할 수 있습니다. 그렇지 않으면 여러 서버 프로세스가 시스템에서 실행 되는 경우 프로세서 사용이 겹칩니다.

**GCHeapCount** 이 설정 되 고 **GCNoAffinitize** 가 설정 된 경우 가비지 수집기는 서버 gc에 사용 되는 프로세서 수를 제한 하지만 gc 힙과 프로세서를 선호도 하지 않습니다.

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

다음 예에서는 서버 GC 스레드를 선호도 하 고 GC 힙/스레드 수를 10으로 제한 하지 않습니다.

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [GCNoAffinitize 요소](gcnoaffinitize-element.md)
- [GCHeapAffinitizeMask 요소](gcheapaffinitizemask-element.md)
- [가비지 컬렉션 기본 사항](../../../../standard/garbage-collection/fundamentals.md)
- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
