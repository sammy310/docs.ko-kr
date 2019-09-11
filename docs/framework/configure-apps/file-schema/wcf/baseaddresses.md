---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850212"
---
# <a name="baseaddresses"></a><span data-ttu-id="40194-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="40194-101">\<baseAddresses></span></span>
<span data-ttu-id="40194-102">자체 호스팅 환경의 서비스 호스트에 대한 기준 주소인 `baseAddress` 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="40194-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="40194-103">기준 주소가 있는 경우 기준 주소에 대한 상대 주소로 엔드포인트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40194-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
<span data-ttu-id="40194-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="40194-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="40194-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="40194-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="40194-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<서비스 >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="40194-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="40194-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<서비스 >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="40194-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="40194-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<호스트 >** ](host.md)</span><span class="sxs-lookup"><span data-stu-id="40194-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="40194-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<baseAddresses >**</span><span class="sxs-lookup"><span data-stu-id="40194-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40194-110">구문</span><span class="sxs-lookup"><span data-stu-id="40194-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="40194-111">형식</span><span class="sxs-lookup"><span data-stu-id="40194-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40194-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="40194-112">Attributes and Elements</span></span>  
 <span data-ttu-id="40194-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="40194-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40194-114">특성</span><span class="sxs-lookup"><span data-stu-id="40194-114">Attributes</span></span>  
 <span data-ttu-id="40194-115">없음</span><span class="sxs-lookup"><span data-stu-id="40194-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="40194-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="40194-116">Child Elements</span></span>  
  
|<span data-ttu-id="40194-117">요소</span><span class="sxs-lookup"><span data-stu-id="40194-117">Element</span></span>|<span data-ttu-id="40194-118">설명</span><span class="sxs-lookup"><span data-stu-id="40194-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40194-119">\<add></span><span class="sxs-lookup"><span data-stu-id="40194-119">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="40194-120">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="40194-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40194-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="40194-121">Parent Elements</span></span>  
  
|<span data-ttu-id="40194-122">요소</span><span class="sxs-lookup"><span data-stu-id="40194-122">Element</span></span>|<span data-ttu-id="40194-123">설명</span><span class="sxs-lookup"><span data-stu-id="40194-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40194-124">\<host></span><span class="sxs-lookup"><span data-stu-id="40194-124">\<host></span></span>](host.md)|<span data-ttu-id="40194-125">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="40194-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40194-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="40194-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="40194-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="40194-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
