---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: b764bc21e9c4555b39c3d096212b6e6bcabb62ff
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855218"
---
# <a name="host"></a><span data-ttu-id="a8510-101">\<host></span><span class="sxs-lookup"><span data-stu-id="a8510-101">\<host></span></span>
<span data-ttu-id="a8510-102">서비스 호스트의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8510-102">Specifies settings for a service host.</span></span>  
  
<span data-ttu-id="a8510-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8510-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a8510-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a8510-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a8510-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<서비스 >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="a8510-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="a8510-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<서비스 >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="a8510-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="a8510-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<호스트 >**</span><span class="sxs-lookup"><span data-stu-id="a8510-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8510-108">구문</span><span class="sxs-lookup"><span data-stu-id="a8510-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="a8510-109">형식</span><span class="sxs-lookup"><span data-stu-id="a8510-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8510-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a8510-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a8510-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8510-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8510-112">특성</span><span class="sxs-lookup"><span data-stu-id="a8510-112">Attributes</span></span>  
 <span data-ttu-id="a8510-113">없음</span><span class="sxs-lookup"><span data-stu-id="a8510-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8510-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a8510-114">Child Elements</span></span>  
  
|<span data-ttu-id="a8510-115">요소</span><span class="sxs-lookup"><span data-stu-id="a8510-115">Element</span></span>|<span data-ttu-id="a8510-116">Description</span><span class="sxs-lookup"><span data-stu-id="a8510-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8510-117">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="a8510-117">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="a8510-118">서비스 호스트에서 사용하는 기본 주소를 지정하는 `baseAddress` 요소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a8510-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="a8510-119">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="a8510-119">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="a8510-120">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a8510-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8510-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a8510-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a8510-122">요소</span><span class="sxs-lookup"><span data-stu-id="a8510-122">Element</span></span>|<span data-ttu-id="a8510-123">Description</span><span class="sxs-lookup"><span data-stu-id="a8510-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8510-124">\<service></span><span class="sxs-lookup"><span data-stu-id="a8510-124">\<service></span></span>](service.md)|<span data-ttu-id="a8510-125">WCF (Windows Communication Foundation) 서비스의 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8510-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8510-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="a8510-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="a8510-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="a8510-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
