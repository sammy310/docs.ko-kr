---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 123f58ee3d77bf605db21fa0d9537b3196d56468
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919110"
---
# <a name="enablewebscript"></a><span data-ttu-id="3cf95-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="3cf95-101">\<enableWebScript></span></span>
<span data-ttu-id="3cf95-102">이 요소는 ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 엔드포인트 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf95-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="3cf95-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3cf95-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3cf95-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3cf95-104">\<behaviors></span></span>  
<span data-ttu-id="3cf95-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="3cf95-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="3cf95-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3cf95-106">\<behavior></span></span>  
<span data-ttu-id="3cf95-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="3cf95-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cf95-108">구문</span><span class="sxs-lookup"><span data-stu-id="3cf95-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cf95-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3cf95-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3cf95-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf95-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cf95-111">특성</span><span class="sxs-lookup"><span data-stu-id="3cf95-111">Attributes</span></span>  
 <span data-ttu-id="3cf95-112">없음</span><span class="sxs-lookup"><span data-stu-id="3cf95-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3cf95-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3cf95-113">Child Elements</span></span>  
 <span data-ttu-id="3cf95-114">없음</span><span class="sxs-lookup"><span data-stu-id="3cf95-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cf95-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3cf95-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3cf95-116">요소</span><span class="sxs-lookup"><span data-stu-id="3cf95-116">Element</span></span>|<span data-ttu-id="3cf95-117">설명</span><span class="sxs-lookup"><span data-stu-id="3cf95-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cf95-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3cf95-118">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3cf95-119">엔드포인트 동작 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf95-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cf95-120">설명</span><span class="sxs-lookup"><span data-stu-id="3cf95-120">Remarks</span></span>  
 <span data-ttu-id="3cf95-121">이 동작은 [ \<webHttpBinding >](webhttpbinding.md) 표준 [ \<바인딩과 webMessageEncoding >](webmessageencoding.md) binding 요소 중 하 나와 함께 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf95-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="3cf95-122">이 동작에 대한 자세한 내용은 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cf95-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cf95-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="3cf95-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="3cf95-124">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="3cf95-124">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="3cf95-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="3cf95-125">\<webHttp></span></span>](webhttp.md)
