---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 89ebad118c1c9210357d8fd281c9216b7f64b450
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398068"
---
# \<defaultPorts>
<span data-ttu-id="60b92-101">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="60b92-101">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**  
  
## <a name="syntax"></a><span data-ttu-id="60b92-102">구문</span><span class="sxs-lookup"><span data-stu-id="60b92-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60b92-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="60b92-103">Attributes and Elements</span></span>  
 <span data-ttu-id="60b92-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="60b92-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60b92-105">특성</span><span class="sxs-lookup"><span data-stu-id="60b92-105">Attributes</span></span>  
 <span data-ttu-id="60b92-106">없음</span><span class="sxs-lookup"><span data-stu-id="60b92-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="60b92-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="60b92-107">Child Elements</span></span>  
  
|<span data-ttu-id="60b92-108">요소</span><span class="sxs-lookup"><span data-stu-id="60b92-108">Element</span></span>|<span data-ttu-id="60b92-109">Description</span><span class="sxs-lookup"><span data-stu-id="60b92-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60b92-110">\<add>으로\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="60b92-110">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="60b92-111">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="60b92-111">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="60b92-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="60b92-112">Parent Elements</span></span>  
  
|<span data-ttu-id="60b92-113">요소</span><span class="sxs-lookup"><span data-stu-id="60b92-113">Element</span></span>|<span data-ttu-id="60b92-114">Description</span><span class="sxs-lookup"><span data-stu-id="60b92-114">Description</span></span>|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="60b92-115">기본 포트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="60b92-115">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60b92-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60b92-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
