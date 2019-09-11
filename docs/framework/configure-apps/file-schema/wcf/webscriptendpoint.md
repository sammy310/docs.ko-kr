---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854808"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="f2513-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="f2513-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="f2513-102">이 구성 요소는 [ \<enableWebScript >](enablewebscript.md) 동작을 자동으로 추가 하는 고정 [ \<된 webHttpBinding >](webhttpbinding.md) 바인딩이 있는 표준 끝점을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2513-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="f2513-103">ASP.NET AJAX 애플리케이션에서 호출되는 서비스를 기록할 때 이 엔드포인트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f2513-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="f2513-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f2513-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f2513-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f2513-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f2513-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="f2513-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="f2513-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webScriptEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="f2513-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2513-108">구문</span><span class="sxs-lookup"><span data-stu-id="f2513-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2513-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f2513-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f2513-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f2513-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2513-111">특성</span><span class="sxs-lookup"><span data-stu-id="f2513-111">Attributes</span></span>  
  
|<span data-ttu-id="f2513-112">특성</span><span class="sxs-lookup"><span data-stu-id="f2513-112">Attribute</span></span>|<span data-ttu-id="f2513-113">Description</span><span class="sxs-lookup"><span data-stu-id="f2513-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2513-114">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="f2513-114">webEndpointType</span></span>|<span data-ttu-id="f2513-115">엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f2513-115">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2513-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f2513-116">Child Elements</span></span>  
 <span data-ttu-id="f2513-117">없음</span><span class="sxs-lookup"><span data-stu-id="f2513-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2513-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f2513-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f2513-119">요소</span><span class="sxs-lookup"><span data-stu-id="f2513-119">Element</span></span>|<span data-ttu-id="f2513-120">설명</span><span class="sxs-lookup"><span data-stu-id="f2513-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2513-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="f2513-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="f2513-122">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f2513-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2513-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="f2513-123">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
