---
title: <namedCaches>에 대한 <add> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154507"
---
# <a name="add-element-for-namedcaches"></a>\<명명 된 \<캐시> 대 한> 요소 추가
메모리 `namedCache` 캐시에 `namedCaches` 대한 항목을 컬렉션에 추가합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.캐싱>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<메모리 캐시>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<명명된 캐시>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**  
  
## <a name="syntax"></a>구문  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Type  
 `None`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|-|-|  
|`CacheMemoryLimitMegabytes`|인스턴스가 증가할 <xref:System.Runtime.Caching.MemoryCache> 수 있는 최대 허용 크기(메가바이트)를 지정하는 정수 값입니다. 기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 휴리스틱이 기본적으로 사용된다는 것을 의미합니다.|  
|`Name`|캐시의 이름입니다.|  
|`PhysicalMemoryLimitPercentage`|캐시에서 사용할 수 있는 물리적으로 설치된 컴퓨터 메모리의 최대 백분율을 지정하는 0에서 100 사이의 정수 값입니다. 기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 휴리스틱이 기본적으로 사용된다는 것을 의미합니다.|  
|`PollingInterval`|캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다. 이 값은 "HH:MM:SS" 형식으로 입력됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
 `None`  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<명명된 캐시>](namedcaches-element-cache-settings.md)|명명된 <xref:System.Runtime.Caching.MemoryCache> 인스턴스에 대한 구성 설정 컬렉션이 포함되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 요소는 `add` 메모리 캐시에 `namedCaches` 대 한 컬렉션에 항목을 추가 합니다. 컬렉션에 명명된 다른 캐시가 없는지 확인하기 위해 요소를 사용하기 전에 clear 요소를 사용할 수 있습니다. [clear](clear-element-for-namedcaches.md) `add` 이 요소는 machine.config 파일 및 Web.config 파일에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 메모리 캐시에 대한 `namedCache` `namedCaches` 컬렉션의 기본 항목에 대한 설정을 정의하는 방법을 보여 주며 있습니다.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [\<명명된 캐시> 요소(캐시 설정)](namedcaches-element-cache-settings.md)
