---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 89ebad118c1c9210357d8fd281c9216b7f64b450
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398068"
---
# <a name="defaultports"></a><span data-ttu-id="d70d3-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="d70d3-101">\<defaultPorts></span></span>
<span data-ttu-id="d70d3-102">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d70d3-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="d70d3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d70d3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d70d3-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d70d3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d70d3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d70d3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d70d3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d70d3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="d70d3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d70d3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="d70d3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<useRequestHeadersForMetadataAddress >** ](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="d70d3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="d70d3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultPorts >**</span><span class="sxs-lookup"><span data-stu-id="d70d3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d70d3-110">구문</span><span class="sxs-lookup"><span data-stu-id="d70d3-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d70d3-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d70d3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d70d3-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d70d3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d70d3-113">특성</span><span class="sxs-lookup"><span data-stu-id="d70d3-113">Attributes</span></span>  
 <span data-ttu-id="d70d3-114">없음</span><span class="sxs-lookup"><span data-stu-id="d70d3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d70d3-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d70d3-115">Child Elements</span></span>  
  
|<span data-ttu-id="d70d3-116">요소</span><span class="sxs-lookup"><span data-stu-id="d70d3-116">Element</span></span>|<span data-ttu-id="d70d3-117">Description</span><span class="sxs-lookup"><span data-stu-id="d70d3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d70d3-118">\<defaultports의 \<> 추가 ></span><span class="sxs-lookup"><span data-stu-id="d70d3-118">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="d70d3-119">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="d70d3-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d70d3-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d70d3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d70d3-121">요소</span><span class="sxs-lookup"><span data-stu-id="d70d3-121">Element</span></span>|<span data-ttu-id="d70d3-122">Description</span><span class="sxs-lookup"><span data-stu-id="d70d3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d70d3-123">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="d70d3-123">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="d70d3-124">기본 포트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d70d3-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d70d3-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="d70d3-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
