---
description: 다음에 대해 자세히 알아보세요. <services>
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 6e8c0c5ad5390c097db7bf1be1f0d489e1c0d624
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786709"
---
# \<services>

<span data-ttu-id="d0712-102">서비스는 구성 파일의 `services` 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0712-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="d0712-103">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0712-103">Each service has its own `service` configuration section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**  
  
## <a name="syntax"></a><span data-ttu-id="d0712-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0712-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0712-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d0712-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d0712-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0712-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0712-107">특성</span><span class="sxs-lookup"><span data-stu-id="d0712-107">Attributes</span></span>  

 <span data-ttu-id="d0712-108">None</span><span class="sxs-lookup"><span data-stu-id="d0712-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d0712-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d0712-109">Child Elements</span></span>  
  
|<span data-ttu-id="d0712-110">요소</span><span class="sxs-lookup"><span data-stu-id="d0712-110">Element</span></span>|<span data-ttu-id="d0712-111">설명</span><span class="sxs-lookup"><span data-stu-id="d0712-111">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="d0712-112">특정 서비스의 서비스 계약, 동작 및 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d0712-112">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0712-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d0712-113">Parent Elements</span></span>  
  
|<span data-ttu-id="d0712-114">요소</span><span class="sxs-lookup"><span data-stu-id="d0712-114">Element</span></span>|<span data-ttu-id="d0712-115">설명</span><span class="sxs-lookup"><span data-stu-id="d0712-115">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="d0712-116">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d0712-116">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0712-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0712-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
