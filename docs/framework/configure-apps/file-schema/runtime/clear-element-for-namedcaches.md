---
title: <namedCaches>에 대한 <clear> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252755"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="c8454-102">\<namedCaches>에 대한 \<clear> 요소</span><span class="sxs-lookup"><span data-stu-id="c8454-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="c8454-103">`namedCache`메모리 캐시의 컬렉션에서 모든 항목을 지웁니다 `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="c8454-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="c8454-104">구문</span><span class="sxs-lookup"><span data-stu-id="c8454-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="c8454-105">Type</span><span class="sxs-lookup"><span data-stu-id="c8454-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8454-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c8454-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c8454-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c8454-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8454-108">특성</span><span class="sxs-lookup"><span data-stu-id="c8454-108">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="c8454-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c8454-109">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="c8454-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c8454-110">Parent Elements</span></span>  
  
|<span data-ttu-id="c8454-111">요소</span><span class="sxs-lookup"><span data-stu-id="c8454-111">Element</span></span>|<span data-ttu-id="c8454-112">Description</span><span class="sxs-lookup"><span data-stu-id="c8454-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="c8454-113">명명 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8454-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8454-114">설명</span><span class="sxs-lookup"><span data-stu-id="c8454-114">Remarks</span></span>  
 <span data-ttu-id="c8454-115">`clear`요소는 `namedCache` 메모리 캐시에 대해 명명 된 캐시 컬렉션에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="c8454-115">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="c8454-116">요소를 사용 하 여 `clear` 새 명명 된 캐시 엔트리를 추가 하기 전에 요소를 사용 하 여 `add` 컬렉션에 명명 된 다른 캐시가 없는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8454-116">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8454-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8454-117">See also</span></span>

- [<span data-ttu-id="c8454-118">\<namedCaches>요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="c8454-118">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
