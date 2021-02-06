---
description: '자세히 알아보기: GCLOHThreshold 요소'
title: GCLOHThreshold 요소
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: 5d4ef4e6aaf44642c2307dc27ac2e99e966d3ad0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652811"
---
# <a name="gclohthreshold-element"></a>GCLOHThreshold 요소

가비지 수집기가 개체를 LOH (large object heap)에 배치 하 게 하는 임계값 크기 (바이트)를 지정 합니다.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a>구문

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a>특성

|attribute|설명|
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

## <a name="see-also"></a>참고 항목

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- [가비지 컬렉션 기본 사항](../../../../standard/garbage-collection/fundamentals.md)
- [GC에 대 한 NET Core 런타임 구성 옵션](../../../../core/run-time-config/garbage-collector.md)
