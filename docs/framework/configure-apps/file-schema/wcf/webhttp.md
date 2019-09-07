---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 00644d248e6fb85d7cf712620e6ac74405e6b0c3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399161"
---
# <a name="webhttp"></a><span data-ttu-id="3bcb5-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="3bcb5-101">\<webHttp></span></span>
<span data-ttu-id="3bcb5-102">이 요소는 구성을 통해 엔드포인트에서 <xref:System.ServiceModel.Description.WebHttpBehavior>를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="3bcb5-103">이 동작은 [ \<webHttpBinding >](webhttpbinding.md) 표준 바인딩과 함께 사용 될 경우 WCF (Windows Communication Foundation) 서비스에 대 한 웹 프로그래밍 모델을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
<span data-ttu-id="3bcb5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3bcb5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3bcb5-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3bcb5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3bcb5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3bcb5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3bcb5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3bcb5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="3bcb5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3bcb5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="3bcb5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webHttp >**</span><span class="sxs-lookup"><span data-stu-id="3bcb5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bcb5-110">구문</span><span class="sxs-lookup"><span data-stu-id="3bcb5-110">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bcb5-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3bcb5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3bcb5-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bcb5-113">특성</span><span class="sxs-lookup"><span data-stu-id="3bcb5-113">Attributes</span></span>  
  
|<span data-ttu-id="3bcb5-114">특성</span><span class="sxs-lookup"><span data-stu-id="3bcb5-114">Attribute</span></span>|<span data-ttu-id="3bcb5-115">Description</span><span class="sxs-lookup"><span data-stu-id="3bcb5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3bcb5-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="3bcb5-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="3bcb5-117">이 속성이 `true`로 설정되면 WCF 인프라가 사용할 가장 적절한 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="3bcb5-118">기본적으로 자동 형식 선택은 이전 버전과의 호환성을 위해 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="3bcb5-119">자동 형식 선택은 프로그래밍 방식이나 구성을 통해 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="3bcb5-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="3bcb5-120">defaultBodyStyle</span></span>|<span data-ttu-id="3bcb5-121">반환된 메시지의 기본 본문 스타일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-121">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="3bcb5-122">자세한 내용은 및 <xref:System.ServiceModel.Web.WebMessageBodyStyle> [WCF 웹 HTTP 형식 지정](../../../wcf/feature-details/wcf-web-http-formatting.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-122">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="3bcb5-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="3bcb5-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="3bcb5-124">메시지의 나가는 기본 응답 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-124">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="3bcb5-125">자세한 내용은 [WCF 웹 HTTP 형식 지정](../../../wcf/feature-details/wcf-web-http-formatting.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-125">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="3bcb5-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="3bcb5-126">faultExceptionEnabled</span></span>|<span data-ttu-id="3bcb5-127">내부 서버 오류(HTTP 상태 코드: 500)가 발생할 때 FaultException이 생성되는지 여부를 지정하는 플래그를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="3bcb5-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="3bcb5-128">helpEnabled</span></span>|<span data-ttu-id="3bcb5-129">도움말 페이지를 사용할 수 있는지 여부를 결정하는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3bcb5-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3bcb5-130">Child Elements</span></span>  
 <span data-ttu-id="3bcb5-131">없음</span><span class="sxs-lookup"><span data-stu-id="3bcb5-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3bcb5-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3bcb5-132">Parent Elements</span></span>  
  
|<span data-ttu-id="3bcb5-133">요소</span><span class="sxs-lookup"><span data-stu-id="3bcb5-133">Element</span></span>|<span data-ttu-id="3bcb5-134">설명</span><span class="sxs-lookup"><span data-stu-id="3bcb5-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bcb5-135">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3bcb5-135">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3bcb5-136">엔드포인트 동작 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcb5-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bcb5-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="3bcb5-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="3bcb5-138">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="3bcb5-138">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="3bcb5-139">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3bcb5-139">\<webHttpBinding></span></span>](webhttpbinding.md)
