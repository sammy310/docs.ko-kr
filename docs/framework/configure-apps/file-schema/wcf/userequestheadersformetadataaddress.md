---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399196"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="18c33-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="18c33-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="18c33-102">요청 메시지 헤더에서 메타데이터 주소 정보를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="18c33-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="18c33-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="18c33-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="18c33-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="18c33-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="18c33-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="18c33-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="18c33-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="18c33-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="18c33-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="18c33-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="18c33-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<useRequestHeadersForMetadataAddress >**</span><span class="sxs-lookup"><span data-stu-id="18c33-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c33-109">구문</span><span class="sxs-lookup"><span data-stu-id="18c33-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18c33-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="18c33-110">Attributes and Elements</span></span>  
 <span data-ttu-id="18c33-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18c33-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18c33-112">특성</span><span class="sxs-lookup"><span data-stu-id="18c33-112">Attributes</span></span>  
 <span data-ttu-id="18c33-113">없음</span><span class="sxs-lookup"><span data-stu-id="18c33-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="18c33-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="18c33-114">Child Elements</span></span>  
  
|<span data-ttu-id="18c33-115">요소</span><span class="sxs-lookup"><span data-stu-id="18c33-115">Element</span></span>|<span data-ttu-id="18c33-116">설명</span><span class="sxs-lookup"><span data-stu-id="18c33-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18c33-117">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="18c33-117">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="18c33-118">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="18c33-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18c33-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="18c33-119">Parent Elements</span></span>  
  
|<span data-ttu-id="18c33-120">요소</span><span class="sxs-lookup"><span data-stu-id="18c33-120">Element</span></span>|<span data-ttu-id="18c33-121">설명</span><span class="sxs-lookup"><span data-stu-id="18c33-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18c33-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="18c33-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="18c33-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18c33-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18c33-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="18c33-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
