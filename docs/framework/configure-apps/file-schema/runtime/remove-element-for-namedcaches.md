---
description: '에 대 한 자세한 정보: <remove> 요소 <namedCaches>'
title: <namedCaches>에 대한 <remove> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 5b39fc596735d746c52cdb5623962f5b9952fa3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802464"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="83067-103">\<namedCaches>에 대한 \<remove> 요소</span><span class="sxs-lookup"><span data-stu-id="83067-103">\<remove> Element for \<namedCaches></span></span>

<span data-ttu-id="83067-104">메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="83067-104">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="83067-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="83067-105">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="83067-106">Type</span><span class="sxs-lookup"><span data-stu-id="83067-106">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83067-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="83067-107">Attributes and Elements</span></span>  

 <span data-ttu-id="83067-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83067-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83067-109">특성</span><span class="sxs-lookup"><span data-stu-id="83067-109">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="83067-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="83067-110">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="83067-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="83067-111">Parent Elements</span></span>  
  
|<span data-ttu-id="83067-112">요소</span><span class="sxs-lookup"><span data-stu-id="83067-112">Element</span></span>|<span data-ttu-id="83067-113">설명</span><span class="sxs-lookup"><span data-stu-id="83067-113">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="83067-114">명명 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 합니다.</span><span class="sxs-lookup"><span data-stu-id="83067-114">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83067-115">설명</span><span class="sxs-lookup"><span data-stu-id="83067-115">Remarks</span></span>  

 <span data-ttu-id="83067-116">`remove`요소는 `namedCache` 메모리 캐시에 대해 명명 된 캐시 컬렉션에서 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="83067-116">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83067-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83067-117">See also</span></span>

- [<span data-ttu-id="83067-118">\<namedCaches> 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="83067-118">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
