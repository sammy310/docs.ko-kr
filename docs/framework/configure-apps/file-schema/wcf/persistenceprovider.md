---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dc8dea0ddd1ea074c08952e3e2ebfef2d12f7183
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099289"
---
# <a name="persistenceprovider"></a><span data-ttu-id="a5ac3-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="a5ac3-101">\<persistenceProvider></span></span>
<span data-ttu-id="a5ac3-102">사용할 지속성 공급자 구현 형식 및 지속성 작업에 사용할 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="a5ac3-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a5ac3-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a5ac3-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a5ac3-104">\<behaviors></span></span>  
<span data-ttu-id="a5ac3-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a5ac3-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="a5ac3-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a5ac3-106">\<behavior></span></span>  
<span data-ttu-id="a5ac3-107">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="a5ac3-107">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ac3-108">구문</span><span class="sxs-lookup"><span data-stu-id="a5ac3-108">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5ac3-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a5ac3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a5ac3-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5ac3-111">특성</span><span class="sxs-lookup"><span data-stu-id="a5ac3-111">Attributes</span></span>  
  
|<span data-ttu-id="a5ac3-112">특성</span><span class="sxs-lookup"><span data-stu-id="a5ac3-112">Attribute</span></span>|<span data-ttu-id="a5ac3-113">설명</span><span class="sxs-lookup"><span data-stu-id="a5ac3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5ac3-114">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="a5ac3-114">persistenceOperationTimeout</span></span>|<span data-ttu-id="a5ac3-115">지속성 작업에 사용되는 제한 시간을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-115">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="a5ac3-116">기본값은 "00: 00:30"입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-116">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="a5ac3-117">type</span><span class="sxs-lookup"><span data-stu-id="a5ac3-117">type</span></span>|<span data-ttu-id="a5ac3-118">사용할 지속성 공급자 팩터리의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-118">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5ac3-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a5ac3-119">Child Elements</span></span>  
 <span data-ttu-id="a5ac3-120">없음</span><span class="sxs-lookup"><span data-stu-id="a5ac3-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5ac3-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a5ac3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a5ac3-122">요소</span><span class="sxs-lookup"><span data-stu-id="a5ac3-122">Element</span></span>|<span data-ttu-id="a5ac3-123">설명</span><span class="sxs-lookup"><span data-stu-id="a5ac3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5ac3-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a5ac3-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a5ac3-125">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-125">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5ac3-126">설명</span><span class="sxs-lookup"><span data-stu-id="a5ac3-126">Remarks</span></span>  
 <span data-ttu-id="a5ac3-127">이 요소는 WCF 서비스의 상태를 serialize하는 데 사용되는 지속성 공급자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-127">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="a5ac3-128">이 요소는 HTTP 헤더에서 상태 정보를 전달하는 `wsHttpContextBinding`과 함께 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-128">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ac3-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5ac3-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
