---
description: 다음에 대해 자세히 알아보세요. <defaultPorts>
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 7cd0635568bf80734900f5e54f918150ea657322
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803908"
---
# \<defaultPorts>

<span data-ttu-id="a02ec-102">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a02ec-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**  
  
## <a name="syntax"></a><span data-ttu-id="a02ec-103">구문</span><span class="sxs-lookup"><span data-stu-id="a02ec-103">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a02ec-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a02ec-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a02ec-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a02ec-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a02ec-106">특성</span><span class="sxs-lookup"><span data-stu-id="a02ec-106">Attributes</span></span>  

 <span data-ttu-id="a02ec-107">없음</span><span class="sxs-lookup"><span data-stu-id="a02ec-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a02ec-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a02ec-108">Child Elements</span></span>  
  
|<span data-ttu-id="a02ec-109">요소</span><span class="sxs-lookup"><span data-stu-id="a02ec-109">Element</span></span>|<span data-ttu-id="a02ec-110">설명</span><span class="sxs-lookup"><span data-stu-id="a02ec-110">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a02ec-111">\<defaultPorts>의 \<add></span><span class="sxs-lookup"><span data-stu-id="a02ec-111">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="a02ec-112">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="a02ec-112">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a02ec-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a02ec-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a02ec-114">요소</span><span class="sxs-lookup"><span data-stu-id="a02ec-114">Element</span></span>|<span data-ttu-id="a02ec-115">설명</span><span class="sxs-lookup"><span data-stu-id="a02ec-115">Description</span></span>|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="a02ec-116">기본 포트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a02ec-116">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a02ec-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a02ec-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
