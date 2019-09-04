---
title: <namedCaches>에 대한 <clear> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252755"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="623d9-102">\<namedcaches의 > \<요소를 지웁니다 ></span><span class="sxs-lookup"><span data-stu-id="623d9-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="623d9-103">메모리 캐시 `namedCache` 의 `namedCaches` 컬렉션에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="623d9-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="623d9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="623d9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="623d9-105">&nbsp;&nbsp;[ **\<>의 런타임 캐싱**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="623d9-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="623d9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="623d9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="623d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="623d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="623d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 지우기**</span><span class="sxs-lookup"><span data-stu-id="623d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="623d9-109">구문</span><span class="sxs-lookup"><span data-stu-id="623d9-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="623d9-110">형식</span><span class="sxs-lookup"><span data-stu-id="623d9-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="623d9-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="623d9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="623d9-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="623d9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="623d9-113">특성</span><span class="sxs-lookup"><span data-stu-id="623d9-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="623d9-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="623d9-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="623d9-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="623d9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="623d9-116">요소</span><span class="sxs-lookup"><span data-stu-id="623d9-116">Element</span></span>|<span data-ttu-id="623d9-117">Description</span><span class="sxs-lookup"><span data-stu-id="623d9-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="623d9-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="623d9-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="623d9-119">명명 <xref:System.Runtime.Caching.MemoryCache> 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="623d9-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="623d9-120">설명</span><span class="sxs-lookup"><span data-stu-id="623d9-120">Remarks</span></span>  
 <span data-ttu-id="623d9-121">요소 `clear` 는 메모리 캐시 `namedCache` 에 대해 명명 된 캐시 컬렉션에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="623d9-121">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="623d9-122">요소를 사용 하 `clear` 여 새 명명 된 캐시 `add` 엔트리를 추가 하기 전에 요소를 사용 하 여 컬렉션에 명명 된 다른 캐시가 없는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="623d9-122">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="623d9-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="623d9-123">See also</span></span>

- [<span data-ttu-id="623d9-124">\<namedCaches > 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="623d9-124">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
