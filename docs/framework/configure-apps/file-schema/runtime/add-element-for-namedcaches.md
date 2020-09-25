---
title: <namedCaches>에 대한 <add> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: cd920b58290050fcc30ea5d0a1ac113a333902fa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195365"
---
# <a name="add-element-for-namedcaches"></a>\<namedCaches>에 대한 \<add> 요소

`namedCache` `namedCaches` 메모리 캐시의 컬렉션에 항목을 추가 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>형식  

 `None`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|-|-|  
|`CacheMemoryLimitMegabytes`|인스턴스를 확장할 수 있는 최대 허용 크기 (mb)를 지정 하는 정수 값입니다 <xref:System.Runtime.Caching.MemoryCache> . 기본값은 0 이며,이는 <xref:System.Runtime.Caching.MemoryCache> 기본적으로 클래스의 자동 크기 조정 추론을 사용 함을 의미 합니다.|  
|`Name`|캐시의 이름입니다.|  
|`PhysicalMemoryLimitPercentage`|캐시에서 사용할 수 있는 물리적으로 설치 된 컴퓨터 메모리의 최대 백분율을 지정 하는 0에서 100 사이의 정수 값입니다. 기본값은 0 이며,이는 <xref:System.Runtime.Caching.MemoryCache> 기본적으로 클래스의 자동 크기 조정 추론을 사용 함을 의미 합니다.|  
|`PollingInterval`|캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다. 이 값은 "HH: MM: SS" 형식으로 입력 됩니다.|  
  
### <a name="child-elements"></a>자식 요소  

 `None`  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|명명 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 합니다.|  
  
## <a name="remarks"></a>설명  

 `add`요소는 `namedCaches` 메모리 캐시의 컬렉션에 항목을 추가 합니다. 요소를 사용 하기 전에 [clear](clear-element-for-namedcaches.md) 요소를 사용 하 여 `add` 컬렉션에 다른 명명 된 캐시가 없음을 확신할 수 있습니다. 이 요소는 machine.config 파일 및 Web.config 파일에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 `namedCache` `namedCaches` 메모리 캐시의 컬렉션에 대 한 기본 항목에 대 한 설정을 정의 하는 방법을 보여 줍니다.  
  
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

- [\<namedCaches> 요소 (캐시 설정)](namedcaches-element-cache-settings.md)
