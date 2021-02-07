---
description: 다음에 대해 자세히 알아보세요. <enableWebScript>
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: f357bf1ab726cd434a16b2daa9c8115afe7d4430
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725885"
---
# \<enableWebScript>

<span data-ttu-id="e556c-102">이 요소는 ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 엔드포인트 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e556c-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="e556c-103">구문</span><span class="sxs-lookup"><span data-stu-id="e556c-103">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e556c-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e556c-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e556c-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e556c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e556c-106">특성</span><span class="sxs-lookup"><span data-stu-id="e556c-106">Attributes</span></span>  

 <span data-ttu-id="e556c-107">없음</span><span class="sxs-lookup"><span data-stu-id="e556c-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e556c-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e556c-108">Child Elements</span></span>  

 <span data-ttu-id="e556c-109">없음</span><span class="sxs-lookup"><span data-stu-id="e556c-109">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e556c-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e556c-110">Parent Elements</span></span>  
  
|<span data-ttu-id="e556c-111">요소</span><span class="sxs-lookup"><span data-stu-id="e556c-111">Element</span></span>|<span data-ttu-id="e556c-112">설명</span><span class="sxs-lookup"><span data-stu-id="e556c-112">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e556c-113">엔드포인트 동작 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e556c-113">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e556c-114">설명</span><span class="sxs-lookup"><span data-stu-id="e556c-114">Remarks</span></span>  

 <span data-ttu-id="e556c-115">이 동작은 [\<webHttpBinding>](webhttpbinding.md) 표준 바인딩 또는 바인딩 요소와 함께 사용 해야 합니다 [\<webMessageEncoding>](webmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="e556c-115">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="e556c-116">이 동작에 대한 자세한 내용은 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e556c-116">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e556c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e556c-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="e556c-118">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="e556c-118">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
