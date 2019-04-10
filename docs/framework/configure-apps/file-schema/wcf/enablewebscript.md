---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: b2cdd29cda7f82ce555b0f6c1a963567b41ff81b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213001"
---
# <a name="enablewebscript"></a><span data-ttu-id="44d7f-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="44d7f-101">\<enableWebScript></span></span>
<span data-ttu-id="44d7f-102">이 요소는 ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 엔드포인트 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="44d7f-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="44d7f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="44d7f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="44d7f-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="44d7f-104">\<behaviors></span></span>  
<span data-ttu-id="44d7f-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="44d7f-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="44d7f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="44d7f-106">\<behavior></span></span>  
<span data-ttu-id="44d7f-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="44d7f-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44d7f-108">구문</span><span class="sxs-lookup"><span data-stu-id="44d7f-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44d7f-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="44d7f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="44d7f-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44d7f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44d7f-111">특성</span><span class="sxs-lookup"><span data-stu-id="44d7f-111">Attributes</span></span>  
 <span data-ttu-id="44d7f-112">없음</span><span class="sxs-lookup"><span data-stu-id="44d7f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="44d7f-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="44d7f-113">Child Elements</span></span>  
 <span data-ttu-id="44d7f-114">없음</span><span class="sxs-lookup"><span data-stu-id="44d7f-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44d7f-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="44d7f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="44d7f-116">요소</span><span class="sxs-lookup"><span data-stu-id="44d7f-116">Element</span></span>|<span data-ttu-id="44d7f-117">설명</span><span class="sxs-lookup"><span data-stu-id="44d7f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44d7f-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="44d7f-118">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="44d7f-119">엔드포인트 동작 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44d7f-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44d7f-120">설명</span><span class="sxs-lookup"><span data-stu-id="44d7f-120">Remarks</span></span>  
 <span data-ttu-id="44d7f-121">이 동작을 사용 하 여 함께에서 해야 합니다 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 표준 바인딩 또는 [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="44d7f-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="44d7f-122">이 동작에 대한 자세한 내용은 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44d7f-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d7f-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="44d7f-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="44d7f-124">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="44d7f-124">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="44d7f-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="44d7f-125">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
