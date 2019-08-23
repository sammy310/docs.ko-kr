---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b12a882d942555a24c145b243d2cea764ba106b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919498"
---
# <a name="clientvia"></a><span data-ttu-id="eb6c5-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="eb6c5-101">\<clientVia></span></span>
<span data-ttu-id="eb6c5-102">전송 채널을 만들어야 하는 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c5-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="eb6c5-103">자세한 내용은 <xref:System.ServiceModel.Description.ClientViaBehavior>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb6c5-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="eb6c5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eb6c5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb6c5-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="eb6c5-105">\<behaviors></span></span>  
<span data-ttu-id="eb6c5-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="eb6c5-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="eb6c5-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="eb6c5-107">\<behavior></span></span>  
<span data-ttu-id="eb6c5-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="eb6c5-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb6c5-109">구문</span><span class="sxs-lookup"><span data-stu-id="eb6c5-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb6c5-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eb6c5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eb6c5-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb6c5-112">특성</span><span class="sxs-lookup"><span data-stu-id="eb6c5-112">Attributes</span></span>  
  
|<span data-ttu-id="eb6c5-113">특성</span><span class="sxs-lookup"><span data-stu-id="eb6c5-113">Attribute</span></span>|<span data-ttu-id="eb6c5-114">Description</span><span class="sxs-lookup"><span data-stu-id="eb6c5-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="eb6c5-115">메시지가 이동할 경로를 나타내는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c5-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb6c5-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eb6c5-116">Child Elements</span></span>  
 <span data-ttu-id="eb6c5-117">없음</span><span class="sxs-lookup"><span data-stu-id="eb6c5-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb6c5-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eb6c5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="eb6c5-119">요소</span><span class="sxs-lookup"><span data-stu-id="eb6c5-119">Element</span></span>|<span data-ttu-id="eb6c5-120">설명</span><span class="sxs-lookup"><span data-stu-id="eb6c5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb6c5-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="eb6c5-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="eb6c5-122">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c5-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb6c5-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb6c5-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
