---
description: 다음에 대해 자세히 알아보세요. <useRequestHeadersForMetadataAddress>
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 53636b5890eb54095737e2ed62a75e9b81c1c1f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664433"
---
# \<useRequestHeadersForMetadataAddress>

<span data-ttu-id="472af-102">요청 메시지 헤더에서 메타데이터 주소 정보를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="472af-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="472af-103">구문</span><span class="sxs-lookup"><span data-stu-id="472af-103">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="472af-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="472af-104">Attributes and Elements</span></span>  

 <span data-ttu-id="472af-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="472af-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="472af-106">특성</span><span class="sxs-lookup"><span data-stu-id="472af-106">Attributes</span></span>  

 <span data-ttu-id="472af-107">없음</span><span class="sxs-lookup"><span data-stu-id="472af-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="472af-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="472af-108">Child Elements</span></span>  
  
|<span data-ttu-id="472af-109">요소</span><span class="sxs-lookup"><span data-stu-id="472af-109">Element</span></span>|<span data-ttu-id="472af-110">설명</span><span class="sxs-lookup"><span data-stu-id="472af-110">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="472af-111">클라이언트 애플리케이션에서 수신하는 기본 통신 엔드포인트를 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="472af-111">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="472af-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="472af-112">Parent Elements</span></span>  
  
|<span data-ttu-id="472af-113">요소</span><span class="sxs-lookup"><span data-stu-id="472af-113">Element</span></span>|<span data-ttu-id="472af-114">설명</span><span class="sxs-lookup"><span data-stu-id="472af-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="472af-115">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="472af-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="472af-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="472af-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
