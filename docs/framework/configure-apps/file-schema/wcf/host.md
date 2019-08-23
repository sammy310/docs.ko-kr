---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 21d53df12c2b2d703b771e2b9cb5ee87dafc410e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918714"
---
# <a name="host"></a><span data-ttu-id="52ddd-101">\<host></span><span class="sxs-lookup"><span data-stu-id="52ddd-101">\<host></span></span>
<span data-ttu-id="52ddd-102">서비스 호스트의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52ddd-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="52ddd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="52ddd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="52ddd-104">\<services></span><span class="sxs-lookup"><span data-stu-id="52ddd-104">\<services></span></span>  
<span data-ttu-id="52ddd-105">\<service></span><span class="sxs-lookup"><span data-stu-id="52ddd-105">\<service></span></span>  
<span data-ttu-id="52ddd-106">\<host></span><span class="sxs-lookup"><span data-stu-id="52ddd-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ddd-107">구문</span><span class="sxs-lookup"><span data-stu-id="52ddd-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="52ddd-108">형식</span><span class="sxs-lookup"><span data-stu-id="52ddd-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52ddd-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="52ddd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="52ddd-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52ddd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52ddd-111">특성</span><span class="sxs-lookup"><span data-stu-id="52ddd-111">Attributes</span></span>  
 <span data-ttu-id="52ddd-112">없음</span><span class="sxs-lookup"><span data-stu-id="52ddd-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="52ddd-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="52ddd-113">Child Elements</span></span>  
  
|<span data-ttu-id="52ddd-114">요소</span><span class="sxs-lookup"><span data-stu-id="52ddd-114">Element</span></span>|<span data-ttu-id="52ddd-115">Description</span><span class="sxs-lookup"><span data-stu-id="52ddd-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52ddd-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="52ddd-116">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="52ddd-117">서비스 호스트에서 사용하는 기본 주소를 지정하는 `baseAddress` 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="52ddd-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="52ddd-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="52ddd-118">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="52ddd-119">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="52ddd-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52ddd-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="52ddd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="52ddd-121">요소</span><span class="sxs-lookup"><span data-stu-id="52ddd-121">Element</span></span>|<span data-ttu-id="52ddd-122">Description</span><span class="sxs-lookup"><span data-stu-id="52ddd-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52ddd-123">\<service></span><span class="sxs-lookup"><span data-stu-id="52ddd-123">\<service></span></span>](service.md)|<span data-ttu-id="52ddd-124">WCF (Windows Communication Foundation) 서비스의 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ddd-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52ddd-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="52ddd-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="52ddd-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="52ddd-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
