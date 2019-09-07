---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 1f9cb6c95fa14a5b8a55cc561699e2a07e1dc80c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399592"
---
# <a name="services"></a><span data-ttu-id="20731-101">\<services></span><span class="sxs-lookup"><span data-stu-id="20731-101">\<services></span></span>
<span data-ttu-id="20731-102">서비스는 구성 파일의 `services` 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="20731-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="20731-103">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20731-103">Each service has its own `service` configuration section.</span></span>  
  
<span data-ttu-id="20731-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="20731-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="20731-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="20731-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="20731-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<서비스 >**</span><span class="sxs-lookup"><span data-stu-id="20731-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**</span></span>  
## <a name="syntax"></a><span data-ttu-id="20731-107">구문</span><span class="sxs-lookup"><span data-stu-id="20731-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20731-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="20731-108">Attributes and Elements</span></span>  
 <span data-ttu-id="20731-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="20731-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20731-110">특성</span><span class="sxs-lookup"><span data-stu-id="20731-110">Attributes</span></span>  
 <span data-ttu-id="20731-111">없음</span><span class="sxs-lookup"><span data-stu-id="20731-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20731-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="20731-112">Child Elements</span></span>  
  
|<span data-ttu-id="20731-113">요소</span><span class="sxs-lookup"><span data-stu-id="20731-113">Element</span></span>|<span data-ttu-id="20731-114">Description</span><span class="sxs-lookup"><span data-stu-id="20731-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20731-115">\<service></span><span class="sxs-lookup"><span data-stu-id="20731-115">\<service></span></span>](service.md)|<span data-ttu-id="20731-116">특정 서비스의 서비스 계약, 동작 및 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="20731-116">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20731-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="20731-117">Parent Elements</span></span>  
  
|<span data-ttu-id="20731-118">요소</span><span class="sxs-lookup"><span data-stu-id="20731-118">Element</span></span>|<span data-ttu-id="20731-119">Description</span><span class="sxs-lookup"><span data-stu-id="20731-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20731-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="20731-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="20731-121">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="20731-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20731-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="20731-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
