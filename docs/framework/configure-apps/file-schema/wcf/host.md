---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 524226cbb826486def18c1b3b66c5b4a3c456dec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185680"
---
# \<host>

<span data-ttu-id="dd5dd-101">서비스 호스트의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dd5dd-101">Specifies settings for a service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**  
  
## <a name="syntax"></a><span data-ttu-id="dd5dd-102">구문</span><span class="sxs-lookup"><span data-stu-id="dd5dd-102">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="dd5dd-103">형식</span><span class="sxs-lookup"><span data-stu-id="dd5dd-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd5dd-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dd5dd-104">Attributes and Elements</span></span>  

 <span data-ttu-id="dd5dd-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd5dd-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd5dd-106">특성</span><span class="sxs-lookup"><span data-stu-id="dd5dd-106">Attributes</span></span>  

 <span data-ttu-id="dd5dd-107">없음</span><span class="sxs-lookup"><span data-stu-id="dd5dd-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dd5dd-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dd5dd-108">Child Elements</span></span>  
  
|<span data-ttu-id="dd5dd-109">요소</span><span class="sxs-lookup"><span data-stu-id="dd5dd-109">Element</span></span>|<span data-ttu-id="dd5dd-110">설명</span><span class="sxs-lookup"><span data-stu-id="dd5dd-110">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="dd5dd-111">서비스 호스트에서 사용하는 기본 주소를 지정하는 `baseAddress` 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="dd5dd-111">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[\<timeOuts>](timeouts.md)|<span data-ttu-id="dd5dd-112">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dd5dd-112">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd5dd-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dd5dd-113">Parent Elements</span></span>  
  
|<span data-ttu-id="dd5dd-114">요소</span><span class="sxs-lookup"><span data-stu-id="dd5dd-114">Element</span></span>|<span data-ttu-id="dd5dd-115">설명</span><span class="sxs-lookup"><span data-stu-id="dd5dd-115">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="dd5dd-116">WCF (Windows Communication Foundation) 서비스의 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd5dd-116">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd5dd-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd5dd-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="dd5dd-118">호스팅</span><span class="sxs-lookup"><span data-stu-id="dd5dd-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
