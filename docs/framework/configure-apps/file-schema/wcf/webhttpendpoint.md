---
description: 다음에 대해 자세히 알아보세요. <webHttpEndpoint>
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: d1bcda1fc97dece833c8163e5facbefe614af0ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682594"
---
# \<webHttpEndpoint>

<span data-ttu-id="f347b-102">이 구성 요소는 [\<webHttpBinding>](webhttpbinding.md) 동작을 자동으로 추가 하는 고정 바인딩을 사용 하 여 표준 끝점을 정의 [\<webHttp>](webhttp.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="f347b-103">REST 서비스를 작성할 때는 이 엔드포인트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-103">Use this endpoint when writing a REST service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="f347b-104">구문</span><span class="sxs-lookup"><span data-stu-id="f347b-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f347b-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f347b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f347b-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f347b-107">특성</span><span class="sxs-lookup"><span data-stu-id="f347b-107">Attributes</span></span>  
  
|<span data-ttu-id="f347b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f347b-108">Attribute</span></span>|<span data-ttu-id="f347b-109">설명</span><span class="sxs-lookup"><span data-stu-id="f347b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f347b-110">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="f347b-110">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="f347b-111">자동 서식 선택을 사용하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-111">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="f347b-112">자동 서식 선택을 사용하면 인프라에서 요청 메시지의 `Accept` 헤더를 구문 분석하여 가장 적합한 응답 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-112">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="f347b-113">`Accept` 헤더에서 적합한 응답 형식을 지정하지 않는 경우 인프라에서 요청 메시지의 `Content-Type`이나 작업의 기본 응답 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-113">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="f347b-114">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="f347b-114">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="f347b-115">나가는 응답의 기본 형식을 지정하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-115">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="f347b-116">이 특성은 <xref:System.ServiceModel.Web.WebMessageFormat> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-116">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="f347b-117">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="f347b-117">helpEnabled</span></span>|<span data-ttu-id="f347b-118">엔드포인트에 대해 HTTP 도움말 페이지가 사용되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-118">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="f347b-119">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="f347b-119">webEndpointType</span></span>|<span data-ttu-id="f347b-120">엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-120">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f347b-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f347b-121">Child Elements</span></span>  

 <span data-ttu-id="f347b-122">없음</span><span class="sxs-lookup"><span data-stu-id="f347b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f347b-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f347b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f347b-124">요소</span><span class="sxs-lookup"><span data-stu-id="f347b-124">Element</span></span>|<span data-ttu-id="f347b-125">설명</span><span class="sxs-lookup"><span data-stu-id="f347b-125">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="f347b-126">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f347b-126">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f347b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f347b-127">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
