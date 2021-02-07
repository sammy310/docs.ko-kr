---
description: 다음에 대해 자세히 알아보세요. <baseAddresses>
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: a32afc23d4332bad149765a318c3ecdc73f99be0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749690"
---
# \<baseAddresses>

<span data-ttu-id="e5236-102">자체 호스팅 환경의 서비스 호스트에 대한 기준 주소인 `baseAddress` 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5236-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="e5236-103">기준 주소가 있는 경우 기준 주소에 대한 상대 주소로 엔드포인트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5236-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**  
  
## <a name="syntax"></a><span data-ttu-id="e5236-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5236-104">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="e5236-105">Type</span><span class="sxs-lookup"><span data-stu-id="e5236-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5236-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e5236-106">Attributes and Elements</span></span>  

 <span data-ttu-id="e5236-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e5236-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5236-108">특성</span><span class="sxs-lookup"><span data-stu-id="e5236-108">Attributes</span></span>  

 <span data-ttu-id="e5236-109">없음</span><span class="sxs-lookup"><span data-stu-id="e5236-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5236-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e5236-110">Child Elements</span></span>  
  
|<span data-ttu-id="e5236-111">요소</span><span class="sxs-lookup"><span data-stu-id="e5236-111">Element</span></span>|<span data-ttu-id="e5236-112">설명</span><span class="sxs-lookup"><span data-stu-id="e5236-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddresses.md)|<span data-ttu-id="e5236-113">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e5236-113">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5236-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e5236-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e5236-115">요소</span><span class="sxs-lookup"><span data-stu-id="e5236-115">Element</span></span>|<span data-ttu-id="e5236-116">설명</span><span class="sxs-lookup"><span data-stu-id="e5236-116">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="e5236-117">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e5236-117">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5236-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5236-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="e5236-119">호스팅</span><span class="sxs-lookup"><span data-stu-id="e5236-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
