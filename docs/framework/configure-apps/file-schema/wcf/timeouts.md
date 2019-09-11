---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854968"
---
# <a name="timeouts"></a><span data-ttu-id="0fbf1-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="0fbf1-101">\<timeOuts></span></span>
<span data-ttu-id="0fbf1-102">서비스 호스트가 열리거나 닫히는 데 허용되는 시간 간격을 지정하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0fbf1-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
<span data-ttu-id="0fbf1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0fbf1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0fbf1-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0fbf1-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0fbf1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<서비스 >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="0fbf1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="0fbf1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<서비스 >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="0fbf1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="0fbf1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<호스트 >** ](host.md)</span><span class="sxs-lookup"><span data-stu-id="0fbf1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="0fbf1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<시간 제한 >**</span><span class="sxs-lookup"><span data-stu-id="0fbf1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fbf1-109">구문</span><span class="sxs-lookup"><span data-stu-id="0fbf1-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0fbf1-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0fbf1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0fbf1-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fbf1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0fbf1-112">특성</span><span class="sxs-lookup"><span data-stu-id="0fbf1-112">Attributes</span></span>  
  
|<span data-ttu-id="0fbf1-113">특성</span><span class="sxs-lookup"><span data-stu-id="0fbf1-113">Attribute</span></span>|<span data-ttu-id="0fbf1-114">설명</span><span class="sxs-lookup"><span data-stu-id="0fbf1-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="0fbf1-115">서비스 호스트를 닫는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0fbf1-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="0fbf1-116">서비스 호스트를 여는 데 허용되는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0fbf1-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0fbf1-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0fbf1-117">Child Elements</span></span>  
 <span data-ttu-id="0fbf1-118">없음</span><span class="sxs-lookup"><span data-stu-id="0fbf1-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0fbf1-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0fbf1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0fbf1-120">요소</span><span class="sxs-lookup"><span data-stu-id="0fbf1-120">Element</span></span>|<span data-ttu-id="0fbf1-121">Description</span><span class="sxs-lookup"><span data-stu-id="0fbf1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0fbf1-122">\<host></span><span class="sxs-lookup"><span data-stu-id="0fbf1-122">\<host></span></span>](host.md)|<span data-ttu-id="0fbf1-123">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fbf1-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fbf1-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="0fbf1-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="0fbf1-125">호스팅</span><span class="sxs-lookup"><span data-stu-id="0fbf1-125">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
