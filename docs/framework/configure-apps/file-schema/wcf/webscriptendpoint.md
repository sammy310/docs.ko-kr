---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: cc69029d9830fd12df5a4070f11847fadf4c60bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940414"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="3c66d-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="3c66d-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="3c66d-102">이 구성 요소는 [ \<enableWebScript >](enablewebscript.md) 동작을 자동으로 추가 하는 고정 [ \<된 webHttpBinding >](webhttpbinding.md) 바인딩이 있는 표준 끝점을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c66d-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="3c66d-103">ASP.NET AJAX 애플리케이션에서 호출되는 서비스를 기록할 때 이 엔드포인트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c66d-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="3c66d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3c66d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3c66d-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3c66d-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c66d-106">구문</span><span class="sxs-lookup"><span data-stu-id="3c66d-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c66d-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3c66d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3c66d-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c66d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c66d-109">특성</span><span class="sxs-lookup"><span data-stu-id="3c66d-109">Attributes</span></span>  
  
|<span data-ttu-id="3c66d-110">특성</span><span class="sxs-lookup"><span data-stu-id="3c66d-110">Attribute</span></span>|<span data-ttu-id="3c66d-111">설명</span><span class="sxs-lookup"><span data-stu-id="3c66d-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c66d-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="3c66d-112">webEndpointType</span></span>|<span data-ttu-id="3c66d-113">엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3c66d-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c66d-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3c66d-114">Child Elements</span></span>  
 <span data-ttu-id="3c66d-115">없음</span><span class="sxs-lookup"><span data-stu-id="3c66d-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c66d-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3c66d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3c66d-117">요소</span><span class="sxs-lookup"><span data-stu-id="3c66d-117">Element</span></span>|<span data-ttu-id="3c66d-118">Description</span><span class="sxs-lookup"><span data-stu-id="3c66d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c66d-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3c66d-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="3c66d-120">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3c66d-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c66d-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="3c66d-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
