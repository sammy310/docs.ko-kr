---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 866be522cb1c64142227a8d6a1a8f88551ca9105
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940478"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="bcfcd-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="bcfcd-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="bcfcd-102">이 구성 요소는 [ \<webhttp >](webhttp.md) 동작을 자동으로 추가 하는 고정 [ \<된 webHttpBinding >](webhttpbinding.md) 바인딩이 있는 표준 끝점을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="bcfcd-103">REST 서비스를 작성할 때는 이 엔드포인트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="bcfcd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bcfcd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bcfcd-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="bcfcd-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfcd-106">구문</span><span class="sxs-lookup"><span data-stu-id="bcfcd-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcfcd-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bcfcd-107">Attributes and Elements</span></span>  
 <span data-ttu-id="bcfcd-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcfcd-109">특성</span><span class="sxs-lookup"><span data-stu-id="bcfcd-109">Attributes</span></span>  
  
|<span data-ttu-id="bcfcd-110">특성</span><span class="sxs-lookup"><span data-stu-id="bcfcd-110">Attribute</span></span>|<span data-ttu-id="bcfcd-111">Description</span><span class="sxs-lookup"><span data-stu-id="bcfcd-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bcfcd-112">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="bcfcd-112">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="bcfcd-113">자동 서식 선택을 사용하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-113">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="bcfcd-114">자동 서식 선택을 사용하면 인프라에서 요청 메시지의 `Accept` 헤더를 구문 분석하여 가장 적합한 응답 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-114">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="bcfcd-115">`Accept` 헤더에서 적합한 응답 형식을 지정하지 않는 경우 인프라에서 요청 메시지의 `Content-Type`이나 작업의 기본 응답 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-115">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="bcfcd-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="bcfcd-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="bcfcd-117">나가는 응답의 기본 형식을 지정하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-117">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="bcfcd-118">이 특성은 <xref:System.ServiceModel.Web.WebMessageFormat> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-118">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="bcfcd-119">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="bcfcd-119">helpEnabled</span></span>|<span data-ttu-id="bcfcd-120">엔드포인트에 대해 HTTP 도움말 페이지가 사용되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-120">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="bcfcd-121">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="bcfcd-121">webEndpointType</span></span>|<span data-ttu-id="bcfcd-122">엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-122">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bcfcd-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bcfcd-123">Child Elements</span></span>  
 <span data-ttu-id="bcfcd-124">없음</span><span class="sxs-lookup"><span data-stu-id="bcfcd-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bcfcd-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bcfcd-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bcfcd-126">요소</span><span class="sxs-lookup"><span data-stu-id="bcfcd-126">Element</span></span>|<span data-ttu-id="bcfcd-127">Description</span><span class="sxs-lookup"><span data-stu-id="bcfcd-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcfcd-128">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="bcfcd-128">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="bcfcd-129">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcd-129">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bcfcd-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="bcfcd-130">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
