---
title: <namedCaches>에 대한 <remove> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 991ad0eb9c04c27ded4d566115107ac7b47a71e1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252347"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="1e0a3-102">\<namedcaches > 요소 \<를 제거 ></span><span class="sxs-lookup"><span data-stu-id="1e0a3-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="1e0a3-103">메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0a3-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="1e0a3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1e0a3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1e0a3-105">&nbsp;&nbsp;[ **\<>의 런타임 캐싱**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1e0a3-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="1e0a3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1e0a3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="1e0a3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1e0a3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="1e0a3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 제거**</span><span class="sxs-lookup"><span data-stu-id="1e0a3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e0a3-109">구문</span><span class="sxs-lookup"><span data-stu-id="1e0a3-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="1e0a3-110">형식</span><span class="sxs-lookup"><span data-stu-id="1e0a3-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e0a3-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1e0a3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1e0a3-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0a3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e0a3-113">특성</span><span class="sxs-lookup"><span data-stu-id="1e0a3-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="1e0a3-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1e0a3-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="1e0a3-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1e0a3-115">Parent Elements</span></span>  
  
|<span data-ttu-id="1e0a3-116">요소</span><span class="sxs-lookup"><span data-stu-id="1e0a3-116">Element</span></span>|<span data-ttu-id="1e0a3-117">Description</span><span class="sxs-lookup"><span data-stu-id="1e0a3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e0a3-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="1e0a3-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="1e0a3-119">명명 <xref:System.Runtime.Caching.MemoryCache> 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0a3-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e0a3-120">설명</span><span class="sxs-lookup"><span data-stu-id="1e0a3-120">Remarks</span></span>  
 <span data-ttu-id="1e0a3-121">요소 `remove` 는 메모리 캐시 `namedCache` 에 대해 명명 된 캐시 컬렉션에서 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0a3-121">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e0a3-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e0a3-122">See also</span></span>

- [<span data-ttu-id="1e0a3-123">\<namedCaches > 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="1e0a3-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
