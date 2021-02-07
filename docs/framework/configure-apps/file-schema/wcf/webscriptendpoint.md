---
description: 다음에 대해 자세히 알아보세요. <webScriptEndpoint>
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: eef4eb8e8e7345492f967c85b6245f733a4c824f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682503"
---
# \<webScriptEndpoint>

<span data-ttu-id="7e36c-102">이 구성 요소는 [\<webHttpBinding>](webhttpbinding.md) 동작을 자동으로 추가 하는 고정 바인딩을 사용 하 여 표준 끝점을 정의 [\<enableWebScript>](enablewebscript.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e36c-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="7e36c-103">ASP.NET AJAX 애플리케이션에서 호출되는 서비스를 기록할 때 이 엔드포인트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e36c-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="7e36c-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e36c-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e36c-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7e36c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7e36c-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7e36c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e36c-107">특성</span><span class="sxs-lookup"><span data-stu-id="7e36c-107">Attributes</span></span>  
  
|<span data-ttu-id="7e36c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7e36c-108">Attribute</span></span>|<span data-ttu-id="7e36c-109">설명</span><span class="sxs-lookup"><span data-stu-id="7e36c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e36c-110">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="7e36c-110">webEndpointType</span></span>|<span data-ttu-id="7e36c-111">엔드포인트의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e36c-111">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e36c-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7e36c-112">Child Elements</span></span>  

 <span data-ttu-id="7e36c-113">없음</span><span class="sxs-lookup"><span data-stu-id="7e36c-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e36c-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7e36c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="7e36c-115">요소</span><span class="sxs-lookup"><span data-stu-id="7e36c-115">Element</span></span>|<span data-ttu-id="7e36c-116">설명</span><span class="sxs-lookup"><span data-stu-id="7e36c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="7e36c-117">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="7e36c-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e36c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e36c-118">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
