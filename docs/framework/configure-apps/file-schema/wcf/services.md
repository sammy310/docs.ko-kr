---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: c00d5fe3e8b2ba05843e09aca6aaa79386541bad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937197"
---
# <a name="services"></a><span data-ttu-id="eb0a8-101">\<services></span><span class="sxs-lookup"><span data-stu-id="eb0a8-101">\<services></span></span>
<span data-ttu-id="eb0a8-102">서비스는 구성 파일의 `services` 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb0a8-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="eb0a8-103">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb0a8-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="eb0a8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eb0a8-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb0a8-105">구문</span><span class="sxs-lookup"><span data-stu-id="eb0a8-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb0a8-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eb0a8-106">Attributes and Elements</span></span>  
 <span data-ttu-id="eb0a8-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb0a8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb0a8-108">특성</span><span class="sxs-lookup"><span data-stu-id="eb0a8-108">Attributes</span></span>  
 <span data-ttu-id="eb0a8-109">없음</span><span class="sxs-lookup"><span data-stu-id="eb0a8-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb0a8-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eb0a8-110">Child Elements</span></span>  
  
|<span data-ttu-id="eb0a8-111">요소</span><span class="sxs-lookup"><span data-stu-id="eb0a8-111">Element</span></span>|<span data-ttu-id="eb0a8-112">Description</span><span class="sxs-lookup"><span data-stu-id="eb0a8-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb0a8-113">\<service></span><span class="sxs-lookup"><span data-stu-id="eb0a8-113">\<service></span></span>](service.md)|<span data-ttu-id="eb0a8-114">특정 서비스의 서비스 계약, 동작 및 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eb0a8-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb0a8-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eb0a8-115">Parent Elements</span></span>  
  
|<span data-ttu-id="eb0a8-116">요소</span><span class="sxs-lookup"><span data-stu-id="eb0a8-116">Element</span></span>|<span data-ttu-id="eb0a8-117">Description</span><span class="sxs-lookup"><span data-stu-id="eb0a8-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb0a8-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eb0a8-118">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="eb0a8-119">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="eb0a8-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb0a8-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb0a8-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
