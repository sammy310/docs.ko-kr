---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d4a205f643c844b2fe77d3aa5211b4bc1f322fd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186968"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads> Element
PerfCounter.dll이 .NET Framework 버전 1.1 애플리케이션에서 CategoryOptions 레지스트리 설정을 사용하여 성능 카운터 데이터를 범주별 공유 메모리에서 로드할지 또는 전역 메모리에서 로드할지를 결정하도록 지정합니다.  
  
 \<configuration>  
\<runtime>  
\<forcePerformanceCounterUniqueSharedMemoryReads>  
  
## <a name="syntax"></a>구문  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> Perfcounter.dll이 성능 카운터 데이터를 범주별 공유 메모리 또는 전역 메모리에서 로드할지 여부를 확인 하려면 CategoryOptions 레지스트리 설정을 사용 하는지 여부를 나타냅니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|Perfcounter.dll이 CategoryOptions를 사용 하지 않는 레지스트리 설정의 기본값입니다.|  
|`true`|Perfcounter.dll이 CategoryOptions 레지스트리 설정을 사용 하 여지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 이전의.NET Framework의 버전에는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 프로세스에서 로드 된 런타임에 해당 하는 perfcounter.dll이 로드 된 버전입니다. 컴퓨터는.NET Framework 버전 1.1 했습니다 및 [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] 설치 된.NET Framework 1.1 응용 프로그램을 로드 perfcounter.dll이.NET Framework 1.1 버전입니다. 부터 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], perfcounter.dll이 설치 된 최신 버전이 로드 됩니다. 즉,.NET Framework 1.1 응용 프로그램을 로드 됩니다 합니다 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] perfcounter.dll이 버전이 경우는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 컴퓨터에 설치 됩니다.  
  
 부터 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 성능 카운터를 사용 하 고 perfcounter.dll이 범주별 공유 메모리 또는 전역 공유 메모리에서 읽어야 하는지 여부를 확인 하려면 각 공급자에 대 한 CategoryOptions 레지스트리 항목을 확인 합니다. 범주별 공유 메모리를 인식 하지 않기 때문에.NET Framework 1.1 perfcounter.dll이 해당 레지스트리 항목을 읽지 못하는 항상 전역 공유 메모리에서 읽습니다.  
  
 이전 버전과 호환성을 위해는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] perfcounter.dll이.NET Framework 1.1 응용 프로그램에서 실행 하는 경우 CategoryOptions 레지스트리 항목을 확인 하지 않습니다. 단순히.NET Framework 1.1 perfcounter.dll이 처럼 전역 공유 메모리를 사용합니다. 지시할 수 있습니다 합니다 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] perfcounter.dll이 레지스트리 설정을 사용 하 여 확인 하는 `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소입니다.  
  
> [!NOTE]
>  사용 하도록 설정 된 `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소 범주별 공유 메모리 사용 됨을 보장 하지 않습니다. 사용 하는 설정과 `true` 만 perfcounter.dll이 CategoryOptions 레지스트리 설정을 참조를 사용 하면 됩니다. CategoryOptions의 기본 설정은 범주별 공유 메모리를 사용 하는 것 그러나 전역 공유 메모리를 사용 해야 함을 나타내려면 CategoryOptions를 변경할 수 있습니다.  
  
 CategoryOptions 설정을 포함 하는 레지스트리 키가 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance 합니다. 기본적으로 CategoryOptions은 3으로 설정, perfcounter.dll이 지시 범주별 공유 메모리를 사용 하도록 합니다. CategoryOptions을 0으로 설정 하는 경우 perfcounter.dll이 전역 공유 메모리를 사용 합니다. 생성 되는 인스턴스의 이름을 다시 사용 되는 인스턴스와 동일한 경우에 인스턴스 데이터 집합이 재사용 됩니다. 모든 버전의 범주를 쓸 수 됩니다. CategoryOptions가 1로 설정 된 경우 전역 공유 메모리 크기를 사용 하지만 범주 이름을 다시 사용 되는 범주와 길이가 같은 경우에 인스턴스 데이터를 다시 사용할 수 있습니다.  
  
 0과 1 설정을 메모리 누수 및 가득 찰 성능 카운터 메모리가 발생할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 perfcounter.dll이 범주별 공유 메모리를 사용 해야 하는지 여부를 확인 하려면 CategoryOptions 레지스트리 항목을 참조 해야 하는지 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
