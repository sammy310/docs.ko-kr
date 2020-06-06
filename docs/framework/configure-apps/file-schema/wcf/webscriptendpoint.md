---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854808"
---
# \<webScriptEndpoint>
<span data-ttu-id="22b93-101">이 구성 요소는 [\<webHttpBinding>](webhttpbinding.md) 동작을 자동으로 추가 하는 고정 바인딩을 사용 하 여 표준 끝점을 정의 [\<enableWebScript>](enablewebscript.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="22b93-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="22b93-102">ASP.NET AJAX 애플리케이션에서 호출되는 서비스를 기록할 때 이 엔드포인트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="22b93-102">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="22b93-103">구문</span><span class="sxs-lookup"><span data-stu-id="22b93-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22b93-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="22b93-104">Attributes and Elements</span></span>  
 <span data-ttu-id="22b93-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22b93-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22b93-106">특성</span><span class="sxs-lookup"><span data-stu-id="22b93-106">Attributes</span></span>  
  
|<span data-ttu-id="22b93-107">attribute</span><span class="sxs-lookup"><span data-stu-id="22b93-107">Attribute</span></span>|<span data-ttu-id="22b93-108">Description</span><span class="sxs-lookup"><span data-stu-id="22b93-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22b93-109">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="22b93-109">webEndpointType</span></span>|<span data-ttu-id="22b93-110">엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="22b93-110">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22b93-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="22b93-111">Child Elements</span></span>  
 <span data-ttu-id="22b93-112">없음</span><span class="sxs-lookup"><span data-stu-id="22b93-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22b93-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="22b93-113">Parent Elements</span></span>  
  
|<span data-ttu-id="22b93-114">요소</span><span class="sxs-lookup"><span data-stu-id="22b93-114">Element</span></span>|<span data-ttu-id="22b93-115">Description</span><span class="sxs-lookup"><span data-stu-id="22b93-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="22b93-116">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="22b93-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22b93-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22b93-117">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
