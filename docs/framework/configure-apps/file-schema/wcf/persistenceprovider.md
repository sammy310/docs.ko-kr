---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 7c4d9ae29ca1e543217d444e05a661b48e2cbb62
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400073"
---
# \<persistenceProvider>
<span data-ttu-id="253a6-101">사용할 지속성 공급자 구현 형식 및 지속성 작업에 사용할 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="253a6-101">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a><span data-ttu-id="253a6-102">구문</span><span class="sxs-lookup"><span data-stu-id="253a6-102">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="253a6-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="253a6-103">Attributes and Elements</span></span>  
 <span data-ttu-id="253a6-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="253a6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="253a6-105">특성</span><span class="sxs-lookup"><span data-stu-id="253a6-105">Attributes</span></span>  
  
|<span data-ttu-id="253a6-106">attribute</span><span class="sxs-lookup"><span data-stu-id="253a6-106">Attribute</span></span>|<span data-ttu-id="253a6-107">Description</span><span class="sxs-lookup"><span data-stu-id="253a6-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="253a6-108">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="253a6-108">persistenceOperationTimeout</span></span>|<span data-ttu-id="253a6-109">지속성 작업에 사용되는 제한 시간을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="253a6-109">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="253a6-110">기본값은 "00:00:30"입니다.</span><span class="sxs-lookup"><span data-stu-id="253a6-110">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="253a6-111">type</span><span class="sxs-lookup"><span data-stu-id="253a6-111">type</span></span>|<span data-ttu-id="253a6-112">사용할 지속성 공급자 팩터리의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="253a6-112">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="253a6-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="253a6-113">Child Elements</span></span>  
 <span data-ttu-id="253a6-114">없음</span><span class="sxs-lookup"><span data-stu-id="253a6-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="253a6-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="253a6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="253a6-116">요소</span><span class="sxs-lookup"><span data-stu-id="253a6-116">Element</span></span>|<span data-ttu-id="253a6-117">Description</span><span class="sxs-lookup"><span data-stu-id="253a6-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="253a6-118">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="253a6-118">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="253a6-119">설명</span><span class="sxs-lookup"><span data-stu-id="253a6-119">Remarks</span></span>  
 <span data-ttu-id="253a6-120">이 요소는 WCF 서비스의 상태를 serialize하는 데 사용되는 지속성 공급자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="253a6-120">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="253a6-121">이 요소는 HTTP 헤더에서 상태 정보를 전달하는 `wsHttpContextBinding`과 함께 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="253a6-121">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="253a6-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="253a6-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
