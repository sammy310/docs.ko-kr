---
title: <namedCaches>에 대한 <remove> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: e9b126cee83bc8109606d915ea48549beea970c9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663469"
---
# <a name="remove-element-for-namedcaches"></a>\<namedcaches > 요소 \<를 제거 >
메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<remove>  
  
## <a name="syntax"></a>구문  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>형식  
 `None`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 `None`  
  
### <a name="child-elements"></a>자식 요소  
 `None`  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|명명 <xref:System.Runtime.Caching.MemoryCache> 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 요소 `remove` 는 메모리 캐시 `namedCache` 에 대해 명명 된 캐시 컬렉션에서 항목을 제거 합니다.  
  
## <a name="see-also"></a>참고자료

- [\<namedCaches > 요소 (캐시 설정)](namedcaches-element-cache-settings.md)
