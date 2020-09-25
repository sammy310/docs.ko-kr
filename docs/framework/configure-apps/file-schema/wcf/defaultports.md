---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 08ca8a2bfcf5b905152f7e64a45cbae4992a7b78
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192375"
---
# \<defaultPorts>

<span data-ttu-id="19934-101">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="19934-101">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**  
  
## <a name="syntax"></a><span data-ttu-id="19934-102">구문</span><span class="sxs-lookup"><span data-stu-id="19934-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19934-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="19934-103">Attributes and Elements</span></span>  

 <span data-ttu-id="19934-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19934-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19934-105">특성</span><span class="sxs-lookup"><span data-stu-id="19934-105">Attributes</span></span>  

 <span data-ttu-id="19934-106">없음</span><span class="sxs-lookup"><span data-stu-id="19934-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="19934-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="19934-107">Child Elements</span></span>  
  
|<span data-ttu-id="19934-108">요소</span><span class="sxs-lookup"><span data-stu-id="19934-108">Element</span></span>|<span data-ttu-id="19934-109">설명</span><span class="sxs-lookup"><span data-stu-id="19934-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19934-110">\<defaultPorts>의 \<add></span><span class="sxs-lookup"><span data-stu-id="19934-110">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="19934-111">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="19934-111">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19934-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="19934-112">Parent Elements</span></span>  
  
|<span data-ttu-id="19934-113">요소</span><span class="sxs-lookup"><span data-stu-id="19934-113">Element</span></span>|<span data-ttu-id="19934-114">설명</span><span class="sxs-lookup"><span data-stu-id="19934-114">Description</span></span>|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="19934-115">기본 포트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="19934-115">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19934-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19934-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
