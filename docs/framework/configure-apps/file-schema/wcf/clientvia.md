---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398106"
---
# <a name="clientvia"></a><span data-ttu-id="9eb0a-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="9eb0a-101">\<clientVia></span></span>
<span data-ttu-id="9eb0a-102">전송 채널을 만들어야 하는 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb0a-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="9eb0a-103">자세한 내용은 <xref:System.ServiceModel.Description.ClientViaBehavior>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9eb0a-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
<span data-ttu-id="9eb0a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9eb0a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9eb0a-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9eb0a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9eb0a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9eb0a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9eb0a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9eb0a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="9eb0a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<동작 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9eb0a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="9eb0a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clientVia >**</span><span class="sxs-lookup"><span data-stu-id="9eb0a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb0a-110">구문</span><span class="sxs-lookup"><span data-stu-id="9eb0a-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9eb0a-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9eb0a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9eb0a-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb0a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9eb0a-113">특성</span><span class="sxs-lookup"><span data-stu-id="9eb0a-113">Attributes</span></span>  
  
|<span data-ttu-id="9eb0a-114">특성</span><span class="sxs-lookup"><span data-stu-id="9eb0a-114">Attribute</span></span>|<span data-ttu-id="9eb0a-115">설명</span><span class="sxs-lookup"><span data-stu-id="9eb0a-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="9eb0a-116">메시지가 이동할 경로를 나타내는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9eb0a-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9eb0a-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9eb0a-117">Child Elements</span></span>  
 <span data-ttu-id="9eb0a-118">없음</span><span class="sxs-lookup"><span data-stu-id="9eb0a-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9eb0a-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9eb0a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9eb0a-120">요소</span><span class="sxs-lookup"><span data-stu-id="9eb0a-120">Element</span></span>|<span data-ttu-id="9eb0a-121">설명</span><span class="sxs-lookup"><span data-stu-id="9eb0a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9eb0a-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9eb0a-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9eb0a-123">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb0a-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9eb0a-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="9eb0a-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
