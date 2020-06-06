---
title: <namedCaches>에 대한 <remove> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 991ad0eb9c04c27ded4d566115107ac7b47a71e1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252347"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="656e2-102">\<namedCaches>에 대한 \<remove> 요소</span><span class="sxs-lookup"><span data-stu-id="656e2-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="656e2-103">메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="656e2-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="656e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="656e2-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="656e2-105">Type</span><span class="sxs-lookup"><span data-stu-id="656e2-105">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="656e2-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="656e2-106">Attributes and Elements</span></span>  
 <span data-ttu-id="656e2-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="656e2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="656e2-108">특성</span><span class="sxs-lookup"><span data-stu-id="656e2-108">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="656e2-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="656e2-109">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="656e2-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="656e2-110">Parent Elements</span></span>  
  
|<span data-ttu-id="656e2-111">요소</span><span class="sxs-lookup"><span data-stu-id="656e2-111">Element</span></span>|<span data-ttu-id="656e2-112">Description</span><span class="sxs-lookup"><span data-stu-id="656e2-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="656e2-113">명명 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 합니다.</span><span class="sxs-lookup"><span data-stu-id="656e2-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="656e2-114">설명</span><span class="sxs-lookup"><span data-stu-id="656e2-114">Remarks</span></span>  
 <span data-ttu-id="656e2-115">`remove`요소는 `namedCache` 메모리 캐시에 대해 명명 된 캐시 컬렉션에서 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="656e2-115">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="656e2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="656e2-116">See also</span></span>

- [<span data-ttu-id="656e2-117">\<namedCaches>요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="656e2-117">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
