---
title: <memoryCache> 요소(캐시 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 94c21e0408b7616bf0c8a24267b72bfa7cc3aaa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153986"
---
# <a name="memorycache-element-cache-settings"></a>\<메모리캐시> 요소(캐시 설정)
<xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 하는 캐시 구성에 사용되는 요소를 정의합니다. <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> 클래스는 캐시를 구성하는 데 사용할 수 있는 [memoryCache](memorycache-element-cache-settings.md) 요소를 정의합니다. <xref:System.Runtime.Caching.MemoryCache> 클래스의 여러 인스턴스를 단일 애플리케이션에서 사용할 수 있습니다. 구성 파일의 각 `memoryCache` 요소에는 명명된 <xref:System.Runtime.Caching.MemoryCache> 인스턴스의 설정을 포함할 수 있습니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.캐싱>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<메모리 캐시>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<memoryCache>
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>
</memoryCache>  
```  
  
## <a name="type"></a>Type  
 <xref:System.Runtime.Caching.MemoryCache> 클래스.  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<xref:System.Runtime.Caching.MemoryCache> 개체의 인스턴스가 증가될 수 있는 최대 메모리 크기(메가바이트 단위)입니다. 기본값은 0입니다. 이 경우 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 추론이 기본적으로 사용됩니다.|  
|`Name`|캐시 구성의 이름입니다.|  
|`PhysicalMemoryLimitPercentage`|캐시에서 사용할 수 있는 실제 메모리의 비율입니다. 기본값은 0입니다. 이 경우 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 추론이 기본적으로 사용됩니다.|  
|`PollingInterval`|캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다. 값은 "HH:MM:SS" 형식으로 입력됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<명명된 캐시>](namedcaches-element-cache-settings.md)|`namedCache` 인스턴스에 대한 구성 설정 컬렉션을 포함합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<구성>](../configuration-element.md)|공통 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소를 지정합니다.|  
|[\<system.runtime.캐싱>](system-runtime-caching-element-cache-settings.md)|.NET Framework에 기본 제공 된 응용 프로그램에서 출력 캐싱을 구현할 수 있는 형식을 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 <xref:System.Runtime.Caching.MemoryCache> 클래스는 추상적인 <xref:System.Runtime.Caching.ObjectCache> 클래스의 구체적인 구현입니다. <xref:System.Runtime.Caching.MemoryCache> 클래스의 인스턴스는 애플리케이션 구성 파일의 구성 정보와 함께 제공될 수 있습니다. [memoryCache](memorycache-element-cache-settings.md) 구성 섹션은 `namedCaches` 구성 컬렉션을 포함합니다.  
  
 메모리 기반 캐시 개체는 초기화된 후 우선 메모리 캐시 생성자에 전달된 매개 변수의 이름과 일치하는 `namedCaches` 항목을 찾으려고 시도합니다. `namedCaches` 항목이 발견되면 구성 파일에서 폴링 및 메모리 관리 정보에 대한 검색이 수행됩니다.  
  
 그런 다음 초기화 프로세스는 생성자에 있는 구성 정보의 선택적인 이름/값 쌍 컬렉션을 사용하여 구성 항목의 재정의 여부를 결정합니다. 이름/값 쌍 컬렉션에서 다음 값 중 하나를 전달하는 경우 이러한 값은 구성 파일에서 가져온 정보를 재정의합니다.  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Runtime.Caching.MemoryCache> `name` 속성을 "Default"로 설정하여 개체 이름을 기본 캐시 개체 이름으로 설정하는 방법을 보여 주며 있습니다.  
  
 `cacheMemoryLimitMegabytes` 특성 및 `physicalMemoryLimitPercentage` 특성은 0으로 설정됩니다. 이러한 특성을 0으로 설정하면 기본적으로 <xref:System.Runtime.Caching.MemoryCache> 자동 크기 조정 추론이 사용됩니다. 캐시 구현에서는 현재 메모리 로드가 절대 및 백분율 기반 메모리 제한과 2분마다 비교됩니다.  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.Caching.MemoryCache>
- [\<system.runtime.캐싱> 요소(캐시 설정)](system-runtime-caching-element-cache-settings.md)
- [\<명명된 캐시> 요소(캐시 설정)](namedcaches-element-cache-settings.md)
