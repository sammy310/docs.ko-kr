---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 3d1f7774f61060880a5c3b0327bdd6c2cc4dd74e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103001"
---
# <a name="host"></a><span data-ttu-id="d03aa-101">\<host></span><span class="sxs-lookup"><span data-stu-id="d03aa-101">\<host></span></span>
<span data-ttu-id="d03aa-102">서비스 호스트의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d03aa-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="d03aa-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d03aa-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d03aa-104">\<services></span><span class="sxs-lookup"><span data-stu-id="d03aa-104">\<services></span></span>  
<span data-ttu-id="d03aa-105">\<service></span><span class="sxs-lookup"><span data-stu-id="d03aa-105">\<service></span></span>  
<span data-ttu-id="d03aa-106">\<host></span><span class="sxs-lookup"><span data-stu-id="d03aa-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d03aa-107">구문</span><span class="sxs-lookup"><span data-stu-id="d03aa-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="d03aa-108">형식</span><span class="sxs-lookup"><span data-stu-id="d03aa-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d03aa-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d03aa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d03aa-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d03aa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d03aa-111">특성</span><span class="sxs-lookup"><span data-stu-id="d03aa-111">Attributes</span></span>  
 <span data-ttu-id="d03aa-112">없음</span><span class="sxs-lookup"><span data-stu-id="d03aa-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d03aa-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d03aa-113">Child Elements</span></span>  
  
|<span data-ttu-id="d03aa-114">요소</span><span class="sxs-lookup"><span data-stu-id="d03aa-114">Element</span></span>|<span data-ttu-id="d03aa-115">설명</span><span class="sxs-lookup"><span data-stu-id="d03aa-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d03aa-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="d03aa-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="d03aa-117">서비스 호스트에서 사용하는 기본 주소를 지정하는 `baseAddress` 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d03aa-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="d03aa-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="d03aa-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="d03aa-119">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d03aa-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d03aa-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d03aa-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d03aa-121">요소</span><span class="sxs-lookup"><span data-stu-id="d03aa-121">Element</span></span>|<span data-ttu-id="d03aa-122">설명</span><span class="sxs-lookup"><span data-stu-id="d03aa-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d03aa-123">\<service></span><span class="sxs-lookup"><span data-stu-id="d03aa-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="d03aa-124">Windows Communication Foundation (WCF) 서비스에 대 한 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d03aa-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d03aa-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="d03aa-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="d03aa-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="d03aa-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
