---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: a323e6da0eb173e303d70cc3b7309b898a805573
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172816"
---
# \<useRequestHeadersForMetadataAddress>

<span data-ttu-id="9ab31-101">요청 메시지 헤더에서 메타데이터 주소 정보를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab31-101">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="9ab31-102">구문</span><span class="sxs-lookup"><span data-stu-id="9ab31-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ab31-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9ab31-103">Attributes and Elements</span></span>  

 <span data-ttu-id="9ab31-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab31-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ab31-105">특성</span><span class="sxs-lookup"><span data-stu-id="9ab31-105">Attributes</span></span>  

 <span data-ttu-id="9ab31-106">없음</span><span class="sxs-lookup"><span data-stu-id="9ab31-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9ab31-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9ab31-107">Child Elements</span></span>  
  
|<span data-ttu-id="9ab31-108">요소</span><span class="sxs-lookup"><span data-stu-id="9ab31-108">Element</span></span>|<span data-ttu-id="9ab31-109">설명</span><span class="sxs-lookup"><span data-stu-id="9ab31-109">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="9ab31-110">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9ab31-110">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ab31-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9ab31-111">Parent Elements</span></span>  
  
|<span data-ttu-id="9ab31-112">요소</span><span class="sxs-lookup"><span data-stu-id="9ab31-112">Element</span></span>|<span data-ttu-id="9ab31-113">설명</span><span class="sxs-lookup"><span data-stu-id="9ab31-113">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9ab31-114">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab31-114">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ab31-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ab31-115">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
