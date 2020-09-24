---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: b8cb5075ba41bed5a22b152a231c7213b326a62f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153718"
---
# \<services>

<span data-ttu-id="fb25c-101">서비스는 구성 파일의 `services` 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb25c-101">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="fb25c-102">서비스별로 해당 `service` 구성 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb25c-102">Each service has its own `service` configuration section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**  
  
## <a name="syntax"></a><span data-ttu-id="fb25c-103">구문</span><span class="sxs-lookup"><span data-stu-id="fb25c-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb25c-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fb25c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="fb25c-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fb25c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb25c-106">특성</span><span class="sxs-lookup"><span data-stu-id="fb25c-106">Attributes</span></span>  

 <span data-ttu-id="fb25c-107">없음</span><span class="sxs-lookup"><span data-stu-id="fb25c-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb25c-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fb25c-108">Child Elements</span></span>  
  
|<span data-ttu-id="fb25c-109">요소</span><span class="sxs-lookup"><span data-stu-id="fb25c-109">Element</span></span>|<span data-ttu-id="fb25c-110">설명</span><span class="sxs-lookup"><span data-stu-id="fb25c-110">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="fb25c-111">특정 서비스의 서비스 계약, 동작 및 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fb25c-111">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb25c-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fb25c-112">Parent Elements</span></span>  
  
|<span data-ttu-id="fb25c-113">요소</span><span class="sxs-lookup"><span data-stu-id="fb25c-113">Element</span></span>|<span data-ttu-id="fb25c-114">설명</span><span class="sxs-lookup"><span data-stu-id="fb25c-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="fb25c-115">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fb25c-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb25c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb25c-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
