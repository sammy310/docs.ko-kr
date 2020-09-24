---
title: <namedCaches>에 대한 <clear> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: d65712f091c5fb9212167b4759c70db7e5d744c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149415"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="ba40a-102">\<namedCaches>에 대한 \<clear> 요소</span><span class="sxs-lookup"><span data-stu-id="ba40a-102">\<clear> Element for \<namedCaches></span></span>

<span data-ttu-id="ba40a-103">`namedCache`메모리 캐시의 컬렉션에서 모든 항목을 지웁니다 `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="ba40a-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="ba40a-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba40a-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="ba40a-105">형식</span><span class="sxs-lookup"><span data-stu-id="ba40a-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba40a-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ba40a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ba40a-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba40a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba40a-108">특성</span><span class="sxs-lookup"><span data-stu-id="ba40a-108">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="ba40a-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ba40a-109">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="ba40a-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ba40a-110">Parent Elements</span></span>  
  
|<span data-ttu-id="ba40a-111">요소</span><span class="sxs-lookup"><span data-stu-id="ba40a-111">Element</span></span>|<span data-ttu-id="ba40a-112">설명</span><span class="sxs-lookup"><span data-stu-id="ba40a-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="ba40a-113">명명 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba40a-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba40a-114">설명</span><span class="sxs-lookup"><span data-stu-id="ba40a-114">Remarks</span></span>  

 <span data-ttu-id="ba40a-115">`clear`요소는 `namedCache` 메모리 캐시에 대해 명명 된 캐시 컬렉션에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ba40a-115">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="ba40a-116">요소를 사용 하 여 `clear` 새 명명 된 캐시 엔트리를 추가 하기 전에 요소를 사용 하 여 `add` 컬렉션에 명명 된 다른 캐시가 없는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba40a-116">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba40a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba40a-117">See also</span></span>

- [<span data-ttu-id="ba40a-118">\<namedCaches> 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="ba40a-118">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
