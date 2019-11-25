---
title: GCNoAffinitize 요소
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 4031ff19131c905072696837d1622dbb6e54ae61
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978416"
---
# <a name="gcnoaffinitize-element"></a>\<GCNoAffinitize > 요소

Cpu가 있는 서버 GC 스레드를 선호도 여부를 지정 합니다.

\<구성 > \
&nbsp;&nbsp;\<런타임 > \
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize >

## <a name="syntax"></a>구문

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|`enabled`|필수 특성입니다.<br /><br />서버 GC 스레드/힙이 컴퓨터에서 사용할 수 있는 프로세서와 선호도가 설정 여부를 지정 합니다.|

#### <a name="enabled-attribute"></a>enabled 특성

|값|설명|
|-----------|-----------------|
|`false`|Cpu가 있는 서버 GC 스레드를 선호도 합니다. 기본값입니다.|
|`true`|는 Cpu가 있는 서버 GC 스레드를 선호도 하지 않습니다.|

### <a name="child-elements"></a>자식 요소

없음.

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|

## <a name="remarks"></a>주의

기본적으로 서버 GC 스레드는 해당 Cpu와 함께 하드 선호도가 설정 됩니다. 각 시스템의 사용 가능한 프로세서에는 자체 GC 힙과 스레드가 있습니다. 이 설정은 캐시 사용을 최적화 하므로 일반적으로 선호 되는 설정입니다. .NET Framework 4.6.2 부터는 **GCNoAffinitize** 요소의 `enabled` 특성을 `false`로 설정 하 여 서버 GC 스레드 및 cpu를 긴밀 하 게 결합 하지 않도록 지정할 수 있습니다.

Cpu가 있는 서버 GC 스레드를 선호도 하지 않도록 **GCNoAffinitize** 구성 요소를 단독으로 지정할 수 있습니다. [GCHeapCount](gcheapcount-element.md) 요소와 함께 사용 하 여 응용 프로그램에서 사용 하는 GC 힙과 스레드 수를 제어할 수도 있습니다.

**GCNoAffinitize** 요소의 `enabled` 특성이 `false` (기본값) 되 면 [GCHeapCount](gcheapcount-element.md) 요소를 사용 하 여 gc 스레드 및 힙을 선호도가 설정 하는 프로세서를 지정 하는 [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) 요소와 함께 gc 스레드 및 힙 수를 지정할 수도 있습니다.

## <a name="example"></a>예제

다음 예에서는 서버 GC 스레드를 하드 선호도 하지 않습니다.

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
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

## <a name="see-also"></a>참조

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [GCHeapAffinitizeMask 요소](gcheapaffinitizemask-element.md)
- [GCHeapCount 요소](gcheapcount-element.md)
- [가비지 컬렉션 기본 사항](../../../../standard/garbage-collection/fundamentals.md)
- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
