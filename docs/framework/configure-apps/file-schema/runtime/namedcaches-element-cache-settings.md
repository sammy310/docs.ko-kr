---
title: <namedCaches> 요소(캐시 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153960"
---
# <a name="namedcaches-element-cache-settings"></a>\<명명된 캐시> 요소(캐시 설정)
명명된 <xref:System.Runtime.Caching.MemoryCache> 인스턴스에 대한 구성 설정 컬렉션을 지정합니다. 합니다 <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> 하나 이상의 구성 설정의 컬렉션을 참조 하는 속성 `namedCaches` 구성 파일의 요소입니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.캐싱>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<메모리 캐시>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<명명된 캐시>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a>Type  
 `None`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|a 인스턴스가 증가할 <xref:System.Runtime.Caching.MemoryCache> 수 있는 최대 허용 크기(메가바이트)를 지정하는 정수 값입니다. 기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 추론이 기본적으로 사용된다는 것을 의미합니다.|  
|`name`|캐시의 이름입니다.|  
|`physicalMemoryLimitPercentage`|캐시에서 사용할 수 있는 물리적으로 설치된 컴퓨터 메모리의 최대 백분율을 지정하는 0에서 100 사이의 정수 값입니다. 기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 추론이 기본적으로 사용된다는 것을 의미합니다.|  
|`pollingInterval`|캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다. 이 값은 "HH:MM:SS" 형식으로 입력됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<>추가](add-element-for-namedcaches.md)|메모리 캐시용으로 명명된 캐시를 `namedCaches` 컬렉션에 추가합니다.|  
|[\<클리어>](clear-element-for-namedcaches.md)|메모리 캐시에 대해 `namedCaches` 컬렉션을 지웁니다.|  
|[\<>제거](remove-element-for-namedcaches.md)|메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<구성>](../configuration-element.md)|공통 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소를 지정합니다.|  
|[\<메모리 캐시>](memorycache-element-cache-settings.md)|<xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 하는 캐시 구성에 사용되는 요소를 정의합니다.|  
|[\<system.runtime.캐싱>](system-runtime-caching-element-cache-settings.md)|.NET Framework에 기본 제공 된 응용 프로그램에서 출력 캐싱을 구현할 수 있는 형식을 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 Web.config 파일의 메모리 캐시 구성 `add`섹션에는 컬렉션에 대한 및 `remove` `clear` 특성이 `namedCaches` 포함될 수 있습니다. 각 `namedCaches` 항목은 `name` 특성에 의해 고유하게 식별됩니다.  
  
 응용 프로그램 구성 파일의 정보를 참조하여 메모리 캐시 항목의 인스턴스를 검색할 수 있습니다. 기본적으로 기본 캐시 인스턴스만 구성 파일에 항목이 있습니다. 기본 캐시 인스턴스는 속성에서 반환되는 <xref:System.Runtime.Caching.MemoryCache.Default%2A> 인스턴스입니다.  
  
 이름 특성을 "기본값"으로 설정하면 요소는 기본 메모리 캐시 인스턴스를 사용합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `name` 특성을 "기본값"으로 설정하여 캐시 이름을 기본 캐시 항목 이름으로 설정하는 방법을 보여 주며 있습니다.  
  
 `cacheMemoryLimitMegabytes` 특성 및 `physicalMemoryPercentage` 특성은 0으로 설정됩니다. 이러한 특성을 0으로 설정하면 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 휴리스틱이 사용됩니다. 캐시 구현은 현재 메모리 로드를 2분마다 절대 및 백분율 기반 메모리 제한과 비교합니다.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [\<메모리캐시> 요소(캐시 설정)](memorycache-element-cache-settings.md)
