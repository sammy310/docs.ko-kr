---
description: 다음에 대해 자세히 알아보세요. <clientVia>
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 651af0c310504f7672ca172d7df609365c319506
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638774"
---
# \<clientVia>

<span data-ttu-id="71ce2-102">전송 채널을 만들어야 하는 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="71ce2-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="71ce2-103">자세한 내용은 <xref:System.ServiceModel.Description.ClientViaBehavior>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71ce2-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="71ce2-104">구문</span><span class="sxs-lookup"><span data-stu-id="71ce2-104">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71ce2-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="71ce2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="71ce2-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="71ce2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71ce2-107">특성</span><span class="sxs-lookup"><span data-stu-id="71ce2-107">Attributes</span></span>  
  
|<span data-ttu-id="71ce2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="71ce2-108">Attribute</span></span>|<span data-ttu-id="71ce2-109">설명</span><span class="sxs-lookup"><span data-stu-id="71ce2-109">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="71ce2-110">메시지가 이동할 경로를 나타내는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="71ce2-110">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71ce2-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="71ce2-111">Child Elements</span></span>  

 <span data-ttu-id="71ce2-112">없음</span><span class="sxs-lookup"><span data-stu-id="71ce2-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71ce2-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="71ce2-113">Parent Elements</span></span>  
  
|<span data-ttu-id="71ce2-114">요소</span><span class="sxs-lookup"><span data-stu-id="71ce2-114">Element</span></span>|<span data-ttu-id="71ce2-115">설명</span><span class="sxs-lookup"><span data-stu-id="71ce2-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="71ce2-116">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="71ce2-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71ce2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71ce2-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
