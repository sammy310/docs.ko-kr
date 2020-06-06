---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854805"
---
# \<webHttpEndpoint>
<span data-ttu-id="dc646-101">이 구성 요소는 [\<webHttpBinding>](webhttpbinding.md) 동작을 자동으로 추가 하는 고정 바인딩을 사용 하 여 표준 끝점을 정의 [\<webHttp>](webhttp.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="dc646-102">REST 서비스를 작성할 때는 이 엔드포인트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-102">Use this endpoint when writing a REST service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="dc646-103">구문</span><span class="sxs-lookup"><span data-stu-id="dc646-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc646-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dc646-104">Attributes and Elements</span></span>  
 <span data-ttu-id="dc646-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc646-106">특성</span><span class="sxs-lookup"><span data-stu-id="dc646-106">Attributes</span></span>  
  
|<span data-ttu-id="dc646-107">attribute</span><span class="sxs-lookup"><span data-stu-id="dc646-107">Attribute</span></span>|<span data-ttu-id="dc646-108">Description</span><span class="sxs-lookup"><span data-stu-id="dc646-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc646-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="dc646-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="dc646-110">자동 서식 선택을 사용하는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-110">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="dc646-111">자동 서식 선택을 사용하면 인프라에서 요청 메시지의 `Accept` 헤더를 구문 분석하여 가장 적합한 응답 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-111">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="dc646-112">`Accept` 헤더에서 적합한 응답 형식을 지정하지 않는 경우 인프라에서 요청 메시지의 `Content-Type`이나 작업의 기본 응답 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-112">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="dc646-113">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="dc646-113">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="dc646-114">나가는 응답의 기본 형식을 지정하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-114">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="dc646-115">이 특성은 <xref:System.ServiceModel.Web.WebMessageFormat> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-115">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="dc646-116">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="dc646-116">helpEnabled</span></span>|<span data-ttu-id="dc646-117">엔드포인트에 대해 HTTP 도움말 페이지가 사용되는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-117">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="dc646-118">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="dc646-118">webEndpointType</span></span>|<span data-ttu-id="dc646-119">엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-119">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc646-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dc646-120">Child Elements</span></span>  
 <span data-ttu-id="dc646-121">없음</span><span class="sxs-lookup"><span data-stu-id="dc646-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc646-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dc646-122">Parent Elements</span></span>  
  
|<span data-ttu-id="dc646-123">요소</span><span class="sxs-lookup"><span data-stu-id="dc646-123">Element</span></span>|<span data-ttu-id="dc646-124">Description</span><span class="sxs-lookup"><span data-stu-id="dc646-124">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="dc646-125">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="dc646-125">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc646-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc646-126">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
