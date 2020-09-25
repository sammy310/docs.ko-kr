---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 3b6cebd178ac5cd30fa034bd961d2d08075771d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201540"
---
# \<baseAddresses>

<span data-ttu-id="e1fa5-101">자체 호스팅 환경의 서비스 호스트에 대한 기준 주소인 `baseAddress` 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-101">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="e1fa5-102">기준 주소가 있는 경우 기준 주소에 대한 상대 주소로 엔드포인트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-102">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**  
  
## <a name="syntax"></a><span data-ttu-id="e1fa5-103">구문</span><span class="sxs-lookup"><span data-stu-id="e1fa5-103">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="e1fa5-104">형식</span><span class="sxs-lookup"><span data-stu-id="e1fa5-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1fa5-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e1fa5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e1fa5-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1fa5-107">특성</span><span class="sxs-lookup"><span data-stu-id="e1fa5-107">Attributes</span></span>  

 <span data-ttu-id="e1fa5-108">없음</span><span class="sxs-lookup"><span data-stu-id="e1fa5-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e1fa5-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e1fa5-109">Child Elements</span></span>  
  
|<span data-ttu-id="e1fa5-110">요소</span><span class="sxs-lookup"><span data-stu-id="e1fa5-110">Element</span></span>|<span data-ttu-id="e1fa5-111">설명</span><span class="sxs-lookup"><span data-stu-id="e1fa5-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddresses.md)|<span data-ttu-id="e1fa5-112">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-112">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1fa5-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e1fa5-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e1fa5-114">요소</span><span class="sxs-lookup"><span data-stu-id="e1fa5-114">Element</span></span>|<span data-ttu-id="e1fa5-115">설명</span><span class="sxs-lookup"><span data-stu-id="e1fa5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="e1fa5-116">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-116">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1fa5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1fa5-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="e1fa5-118">호스팅</span><span class="sxs-lookup"><span data-stu-id="e1fa5-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
