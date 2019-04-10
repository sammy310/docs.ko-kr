---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 2db168d48e3959a7d80a10ca27134f58e3fcb2de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168079"
---
# <a name="services"></a><span data-ttu-id="a350e-101">\<services></span><span class="sxs-lookup"><span data-stu-id="a350e-101">\<services></span></span>
<span data-ttu-id="a350e-102">서비스는 구성 파일의 `services` 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a350e-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="a350e-103">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a350e-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="a350e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a350e-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a350e-105">구문</span><span class="sxs-lookup"><span data-stu-id="a350e-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a350e-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a350e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a350e-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a350e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a350e-108">특성</span><span class="sxs-lookup"><span data-stu-id="a350e-108">Attributes</span></span>  
 <span data-ttu-id="a350e-109">없음</span><span class="sxs-lookup"><span data-stu-id="a350e-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a350e-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a350e-110">Child Elements</span></span>  
  
|<span data-ttu-id="a350e-111">요소</span><span class="sxs-lookup"><span data-stu-id="a350e-111">Element</span></span>|<span data-ttu-id="a350e-112">설명</span><span class="sxs-lookup"><span data-stu-id="a350e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a350e-113">\<service></span><span class="sxs-lookup"><span data-stu-id="a350e-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="a350e-114">특정 서비스의 서비스 계약, 동작 및 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a350e-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a350e-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a350e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a350e-116">요소</span><span class="sxs-lookup"><span data-stu-id="a350e-116">Element</span></span>|<span data-ttu-id="a350e-117">설명</span><span class="sxs-lookup"><span data-stu-id="a350e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a350e-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a350e-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="a350e-119">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a350e-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a350e-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="a350e-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
