---
description: 다음에 대해 자세히 알아보세요. <webHttp>
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: acd8d77e00828d132d076c867ff3164ca1ba7230
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664381"
---
# \<webHttp>

<span data-ttu-id="b8e23-102">이 요소는 구성을 통해 엔드포인트에서 <xref:System.ServiceModel.Description.WebHttpBehavior>를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="b8e23-103">이 동작은 표준 바인딩과 함께 사용 될 경우 [\<webHttpBinding>](webhttpbinding.md) WCF (Windows Communication Foundation) 서비스용 웹 프로그래밍 모델을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**  
  
## <a name="syntax"></a><span data-ttu-id="b8e23-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8e23-104">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8e23-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b8e23-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b8e23-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8e23-107">특성</span><span class="sxs-lookup"><span data-stu-id="b8e23-107">Attributes</span></span>  
  
|<span data-ttu-id="b8e23-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b8e23-108">Attribute</span></span>|<span data-ttu-id="b8e23-109">설명</span><span class="sxs-lookup"><span data-stu-id="b8e23-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8e23-110">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="b8e23-110">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="b8e23-111">이 속성이 `true`로 설정되면 WCF 인프라가 사용할 가장 적절한 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-111">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="b8e23-112">기본적으로 자동 형식 선택은 이전 버전과의 호환성을 위해 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-112">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="b8e23-113">자동 형식 선택은 프로그래밍 방식이나 구성을 통해 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-113">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="b8e23-114">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="b8e23-114">defaultBodyStyle</span></span>|<span data-ttu-id="b8e23-115">반환된 메시지의 기본 본문 스타일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-115">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="b8e23-116">자세한 내용은 <xref:System.ServiceModel.Web.WebMessageBodyStyle> 및 [WCF 웹 HTTP 형식 지정](../../../wcf/feature-details/wcf-web-http-formatting.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e23-116">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="b8e23-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="b8e23-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="b8e23-118">메시지의 나가는 기본 응답 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-118">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="b8e23-119">자세한 내용은 [WCF 웹 HTTP 형식 지정](../../../wcf/feature-details/wcf-web-http-formatting.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e23-119">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="b8e23-120">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="b8e23-120">faultExceptionEnabled</span></span>|<span data-ttu-id="b8e23-121">내부 서버 오류(HTTP 상태 코드: 500)가 발생할 때 FaultException이 생성되는지 여부를 지정하는 플래그를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-121">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="b8e23-122">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="b8e23-122">helpEnabled</span></span>|<span data-ttu-id="b8e23-123">도움말 페이지를 사용할 수 있는지 여부를 결정하는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-123">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8e23-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b8e23-124">Child Elements</span></span>  

 <span data-ttu-id="b8e23-125">없음</span><span class="sxs-lookup"><span data-stu-id="b8e23-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8e23-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b8e23-126">Parent Elements</span></span>  
  
|<span data-ttu-id="b8e23-127">요소</span><span class="sxs-lookup"><span data-stu-id="b8e23-127">Element</span></span>|<span data-ttu-id="b8e23-128">설명</span><span class="sxs-lookup"><span data-stu-id="b8e23-128">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b8e23-129">엔드포인트 동작 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8e23-129">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8e23-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8e23-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="b8e23-131">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="b8e23-131">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
