---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850212"
---
# \<baseAddresses>
<span data-ttu-id="52e7d-101">자체 호스팅 환경의 서비스 호스트에 대한 기준 주소인 `baseAddress` 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52e7d-101">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="52e7d-102">기준 주소가 있는 경우 기준 주소에 대한 상대 주소로 엔드포인트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52e7d-102">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**  
  
## <a name="syntax"></a><span data-ttu-id="52e7d-103">구문</span><span class="sxs-lookup"><span data-stu-id="52e7d-103">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="52e7d-104">Type</span><span class="sxs-lookup"><span data-stu-id="52e7d-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52e7d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="52e7d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="52e7d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52e7d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52e7d-107">특성</span><span class="sxs-lookup"><span data-stu-id="52e7d-107">Attributes</span></span>  
 <span data-ttu-id="52e7d-108">없음</span><span class="sxs-lookup"><span data-stu-id="52e7d-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="52e7d-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="52e7d-109">Child Elements</span></span>  
  
|<span data-ttu-id="52e7d-110">요소</span><span class="sxs-lookup"><span data-stu-id="52e7d-110">Element</span></span>|<span data-ttu-id="52e7d-111">Description</span><span class="sxs-lookup"><span data-stu-id="52e7d-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddresses.md)|<span data-ttu-id="52e7d-112">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="52e7d-112">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52e7d-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="52e7d-113">Parent Elements</span></span>  
  
|<span data-ttu-id="52e7d-114">요소</span><span class="sxs-lookup"><span data-stu-id="52e7d-114">Element</span></span>|<span data-ttu-id="52e7d-115">Description</span><span class="sxs-lookup"><span data-stu-id="52e7d-115">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="52e7d-116">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="52e7d-116">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52e7d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52e7d-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="52e7d-118">호스팅</span><span class="sxs-lookup"><span data-stu-id="52e7d-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
