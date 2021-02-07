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
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="5f737-103">\<namedCaches>에 대한 \<clear> 요소</span><span class="sxs-lookup"><span data-stu-id="5f737-103">\<clear> Element for \<namedCaches></span></span>

<span data-ttu-id="5f737-104">`namedCache`메모리 캐시의 컬렉션에서 모든 항목을 지웁니다 `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="5f737-104">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="5f737-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f737-105">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="5f737-106">Type</span><span class="sxs-lookup"><span data-stu-id="5f737-106">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f737-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5f737-107">Attributes and Elements</span></span>  

 <span data-ttu-id="5f737-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5f737-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f737-109">특성</span><span class="sxs-lookup"><span data-stu-id="5f737-109">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="5f737-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5f737-110">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="5f737-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5f737-111">Parent Elements</span></span>  
  
|<span data-ttu-id="5f737-112">요소</span><span class="sxs-lookup"><span data-stu-id="5f737-112">Element</span></span>|<span data-ttu-id="5f737-113">설명</span><span class="sxs-lookup"><span data-stu-id="5f737-113">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="5f737-114">명명 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f737-114">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f737-115">설명</span><span class="sxs-lookup"><span data-stu-id="5f737-115">Remarks</span></span>  

 <span data-ttu-id="5f737-116">`clear`요소는 `namedCache` 메모리 캐시에 대해 명명 된 캐시 컬렉션에서 모든 항목을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5f737-116">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="5f737-117">요소를 사용 하 여 `clear` 새 명명 된 캐시 엔트리를 추가 하기 전에 요소를 사용 하 여 `add` 컬렉션에 명명 된 다른 캐시가 없는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f737-117">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f737-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f737-118">See also</span></span>

- [<span data-ttu-id="5f737-119">\<namedCaches> 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="5f737-119">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
