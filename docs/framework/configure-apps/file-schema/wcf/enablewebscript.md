---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400380"
---
# <a name="enablewebscript"></a><span data-ttu-id="a929e-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="a929e-101">\<enableWebScript></span></span>
<span data-ttu-id="a929e-102">이 요소는 ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 엔드포인트 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a929e-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
<span data-ttu-id="a929e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a929e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a929e-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a929e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a929e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a929e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="a929e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a929e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="a929e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a929e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="a929e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<enableWebScript >**</span><span class="sxs-lookup"><span data-stu-id="a929e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a929e-109">구문</span><span class="sxs-lookup"><span data-stu-id="a929e-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a929e-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a929e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a929e-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a929e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a929e-112">특성</span><span class="sxs-lookup"><span data-stu-id="a929e-112">Attributes</span></span>  
 <span data-ttu-id="a929e-113">없음</span><span class="sxs-lookup"><span data-stu-id="a929e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a929e-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a929e-114">Child Elements</span></span>  
 <span data-ttu-id="a929e-115">없음</span><span class="sxs-lookup"><span data-stu-id="a929e-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a929e-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a929e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a929e-117">요소</span><span class="sxs-lookup"><span data-stu-id="a929e-117">Element</span></span>|<span data-ttu-id="a929e-118">설명</span><span class="sxs-lookup"><span data-stu-id="a929e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a929e-119">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a929e-119">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a929e-120">엔드포인트 동작 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a929e-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a929e-121">설명</span><span class="sxs-lookup"><span data-stu-id="a929e-121">Remarks</span></span>  
 <span data-ttu-id="a929e-122">이 동작은 [ \<webHttpBinding >](webhttpbinding.md) 표준 [ \<바인딩과 webMessageEncoding >](webmessageencoding.md) binding 요소 중 하 나와 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a929e-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="a929e-123">이 동작에 대한 자세한 내용은 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a929e-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a929e-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="a929e-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="a929e-125">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="a929e-125">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="a929e-126">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="a929e-126">\<webHttp></span></span>](webhttp.md)
