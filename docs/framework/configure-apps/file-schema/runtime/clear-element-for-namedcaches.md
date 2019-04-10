---
title: <clear> 에 대 한 요소 <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: eb0a50919e163a795abc70d132bd45f1d05192ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146863"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="71f41-102">\<지우기 > 요소에 대 한 \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="71f41-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="71f41-103">모두 지웁니다 `namedCache` 에서 항목을 `namedCaches` 메모리 캐시에 대 한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="71f41-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="71f41-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="71f41-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="71f41-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="71f41-105">\<memoryCache></span></span>  
<span data-ttu-id="71f41-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="71f41-106">\<namedCaches></span></span>  
<span data-ttu-id="71f41-107">\<add></span><span class="sxs-lookup"><span data-stu-id="71f41-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f41-108">구문</span><span class="sxs-lookup"><span data-stu-id="71f41-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="71f41-109">형식</span><span class="sxs-lookup"><span data-stu-id="71f41-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71f41-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="71f41-110">Attributes and Elements</span></span>  
 <span data-ttu-id="71f41-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="71f41-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71f41-112">특성</span><span class="sxs-lookup"><span data-stu-id="71f41-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="71f41-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="71f41-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="71f41-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="71f41-114">Parent Elements</span></span>  
  
|<span data-ttu-id="71f41-115">요소</span><span class="sxs-lookup"><span data-stu-id="71f41-115">Element</span></span>|<span data-ttu-id="71f41-116">설명</span><span class="sxs-lookup"><span data-stu-id="71f41-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71f41-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="71f41-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="71f41-118">명명 된 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="71f41-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71f41-119">설명</span><span class="sxs-lookup"><span data-stu-id="71f41-119">Remarks</span></span>  
 <span data-ttu-id="71f41-120">합니다 `clear` 요소를 모두 지웁니다 `namedCache` 메모리 캐시에 대 한 명명 된 캐시 컬렉션의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="71f41-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="71f41-121">사용할 수는 `clear` 요소를 사용 하기 전에 `add` 명명 된 컬렉션에는 캐시는 다른 특정 되려면 새 명명 된 캐시 항목을 추가할 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="71f41-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f41-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="71f41-122">See also</span></span>

- [<span data-ttu-id="71f41-123">\<namedCaches > 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="71f41-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
