---
description: 다음에 대해 자세히 알아보세요. <host>
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: ff240c85af3aab7c1208a6a49b1943f3c6a8cd99
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802283"
---
# \<host>

<span data-ttu-id="0562d-102">서비스 호스트의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0562d-102">Specifies settings for a service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**  
  
## <a name="syntax"></a><span data-ttu-id="0562d-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="0562d-103">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="0562d-104">Type</span><span class="sxs-lookup"><span data-stu-id="0562d-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0562d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0562d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0562d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0562d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0562d-107">특성</span><span class="sxs-lookup"><span data-stu-id="0562d-107">Attributes</span></span>  

 <span data-ttu-id="0562d-108">없음</span><span class="sxs-lookup"><span data-stu-id="0562d-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0562d-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0562d-109">Child Elements</span></span>  
  
|<span data-ttu-id="0562d-110">요소</span><span class="sxs-lookup"><span data-stu-id="0562d-110">Element</span></span>|<span data-ttu-id="0562d-111">설명</span><span class="sxs-lookup"><span data-stu-id="0562d-111">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="0562d-112">서비스 호스트에서 사용하는 기본 주소를 지정하는 `baseAddress` 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0562d-112">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[\<timeOuts>](timeouts.md)|<span data-ttu-id="0562d-113">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0562d-113">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0562d-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0562d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0562d-115">요소</span><span class="sxs-lookup"><span data-stu-id="0562d-115">Element</span></span>|<span data-ttu-id="0562d-116">설명</span><span class="sxs-lookup"><span data-stu-id="0562d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="0562d-117">WCF (Windows Communication Foundation) 서비스의 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0562d-117">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0562d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0562d-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="0562d-119">호스팅</span><span class="sxs-lookup"><span data-stu-id="0562d-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
