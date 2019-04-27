---
title: <performanceCounters> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: 6144bcbda69b2ba799e87c3e7fa2118fbe4d9bf6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673744"
---
# <a name="performancecounters-element"></a>\<performanceCounters > 요소

성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.

 \<configuration>\
\<system.diagnostics>\
\<performanceCounters>

## <a name="syntax"></a>구문

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|filemappingsize|필수 특성입니다.<br /><br /> 성능 카운터에서 공유 하는 전역 메모리의 바이트에서 크기를 지정 합니다. 기본값은 524288입니다.|

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|`Configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`system.diagnostics`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|

## <a name="remarks"></a>설명

성능 카운터 메모리 매핑된 파일 또는 공유 메모리를 사용 하 여 성능 데이터를 게시 합니다.  공유 메모리 크기의 인스턴스 개수을 한 번에 사용할 수를 결정 합니다.  공유 메모리의 두 종류가 있습니다: 전역 공유 메모리 및 별도 공유 메모리입니다.  전역 공유 메모리는.NET Framework 버전 1.0 또는 1.1을 사용 하 여 설치 된 모든 성능 카운터 범주에서 사용 됩니다.  자체 메모리가 있는 각 성능 카운터 범주를 사용 하 여 별도 공유 메모리를 사용 하는 성능 카운터 범주는.NET Framework 버전 2.0 사용 하 여 설치 합니다.

구성 파일에만 전역 공유 메모리의 크기를 설정할 수 있습니다.  기본 크기는 524,288 바이트이 하 이기, 최대 크기는 33,554,432 바이트 및 최소 크기는 32,768 바이트입니다.  모든 프로세스 및 범주에서 전역 공유 메모리를 공유 하므로 첫 번째 생성자는 크기를 지정 합니다.  응용 프로그램 구성 파일의 크기를 정의 하는 경우 응용 프로그램 성능 카운터를 실행 시키는 첫 번째 응용 프로그램은 해당 크기만 사용 됩니다.  따라서 올바른 위치를 지정 합니다 `filemappingsize` 값은 Machine.config 파일입니다.  개별 성능 카운터 있으므로 결국 많은 수의 서로 다른 이름 사용 하 여 성능 카운터 인스턴스가 생성 되는 경우 전역 공유 메모리를 모두 사용 하 여 전역 공유 메모리에서 메모리를 해제할 수 없습니다.

별도 공유 메모리의 크기를 DWORD FileMappingSize 값을 레지스트리에서 키 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<범주 이름 >* \Performance 참조 먼저 구성 파일에서 전역 공유 메모리에 대 한 지정 된 값 뒤에 있습니다. FileMappingSize 값 존재 하지 않는 경우 별도 공유 메모리 크기가 1 4로 설정 됩니다 (1/4) 구성 파일에서 전역 설정입니다.

## <a name="see-also"></a>참고자료

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
