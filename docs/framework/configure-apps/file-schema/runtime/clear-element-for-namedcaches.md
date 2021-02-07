---
description: '에 대 한 자세한 정보: <clear> 요소 <namedCaches>'
title: <namedCaches>에 대한 <clear> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: 9d883c102fc76875ce155f353920f730bf9700c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719099"
---
# <a name="clear-element-for-namedcaches"></a>\<namedCaches>에 대한 \<clear> 요소

`namedCache`메모리 캐시의 컬렉션에서 모든 항목을 지웁니다 `namedCaches` .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Type  

 `Type`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  

 `None`  
  
### <a name="child-elements"></a>자식 요소  

 `None`  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|명명 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 합니다.|  
  
## <a name="remarks"></a>설명  

 `clear`요소는 `namedCache` 메모리 캐시에 대해 명명 된 캐시 컬렉션에서 모든 항목을 지웁니다. 요소를 사용 하 여 `clear` 새 명명 된 캐시 엔트리를 추가 하기 전에 요소를 사용 하 여 `add` 컬렉션에 명명 된 다른 캐시가 없는지 확인할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [\<namedCaches> 요소 (캐시 설정)](namedcaches-element-cache-settings.md)
