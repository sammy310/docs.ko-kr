---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 11378e6cc8cbe8e631fd77ab74c91a616099df52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190087"
---
# \<enableWebScript>

<span data-ttu-id="3267e-101">이 요소는 ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 엔드포인트 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3267e-101">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="3267e-102">구문</span><span class="sxs-lookup"><span data-stu-id="3267e-102">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3267e-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3267e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="3267e-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3267e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3267e-105">특성</span><span class="sxs-lookup"><span data-stu-id="3267e-105">Attributes</span></span>  

 <span data-ttu-id="3267e-106">없음</span><span class="sxs-lookup"><span data-stu-id="3267e-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3267e-107">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3267e-107">Child Elements</span></span>  

 <span data-ttu-id="3267e-108">없음</span><span class="sxs-lookup"><span data-stu-id="3267e-108">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3267e-109">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3267e-109">Parent Elements</span></span>  
  
|<span data-ttu-id="3267e-110">요소</span><span class="sxs-lookup"><span data-stu-id="3267e-110">Element</span></span>|<span data-ttu-id="3267e-111">설명</span><span class="sxs-lookup"><span data-stu-id="3267e-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3267e-112">엔드포인트 동작 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3267e-112">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3267e-113">설명</span><span class="sxs-lookup"><span data-stu-id="3267e-113">Remarks</span></span>  

 <span data-ttu-id="3267e-114">이 동작은 [\<webHttpBinding>](webhttpbinding.md) 표준 바인딩 또는 바인딩 요소와 함께 사용 해야 합니다 [\<webMessageEncoding>](webmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="3267e-114">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="3267e-115">이 동작에 대한 자세한 내용은 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3267e-115">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3267e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3267e-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="3267e-117">AJAX 통합 및 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="3267e-117">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
