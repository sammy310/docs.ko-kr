---
title: GCLOHThreshold 요소
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451325"
---
# <a name="gclohthreshold-element"></a>GCLOHThreshold 요소

가비지 수집기가 개체를 LOH (large object heap)에 배치 하 게 하는 임계값 크기 (바이트)를 지정 합니다.

[\<configuration>](../configuration-element.md)\
[\<런타임 >](runtime-element.md) &nbsp;&nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold >

## <a name="syntax"></a>구문

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|`enabled`|필수 특성입니다.<br /><br />큰 개체 힙에서 개체를 이동 하 게 하는 임계값 크기를 지정 합니다.|

### <a name="enabled-attribute"></a>enabled 특성

|값|설명|
|-----------|-----------------|
|`nnnn`|개체가 큰 개체 힙에 이동 되도록 하는 임계값 크기 (바이트)입니다.|

## <a name="child-elements"></a>자식 요소

없음

## <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|

## <a name="remarks"></a>설명

이 설정은 .NET Framework 4.8에서 도입 되었습니다.

## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- [가비지 컬렉션 기본 사항](../../../../standard/garbage-collection/fundamentals.md)
- [GC에 대 한 NET Core 런타임 구성 옵션](../../../../core/run-time-config/garbage-collector.md)
