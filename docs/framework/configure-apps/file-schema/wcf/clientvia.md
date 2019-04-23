---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b8864760c1700cd785922b922346204d194f56cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176815"
---
# <a name="clientvia"></a><span data-ttu-id="b7d66-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="b7d66-101">\<clientVia></span></span>
<span data-ttu-id="b7d66-102">전송 채널을 만들어야 하는 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d66-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="b7d66-103">자세한 내용은 <xref:System.ServiceModel.Description.ClientViaBehavior>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7d66-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="b7d66-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b7d66-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b7d66-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b7d66-105">\<behaviors></span></span>  
<span data-ttu-id="b7d66-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="b7d66-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="b7d66-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b7d66-107">\<behavior></span></span>  
<span data-ttu-id="b7d66-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="b7d66-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d66-109">구문</span><span class="sxs-lookup"><span data-stu-id="b7d66-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7d66-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b7d66-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b7d66-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d66-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7d66-112">특성</span><span class="sxs-lookup"><span data-stu-id="b7d66-112">Attributes</span></span>  
  
|<span data-ttu-id="b7d66-113">특성</span><span class="sxs-lookup"><span data-stu-id="b7d66-113">Attribute</span></span>|<span data-ttu-id="b7d66-114">설명</span><span class="sxs-lookup"><span data-stu-id="b7d66-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="b7d66-115">메시지가 이동할 경로를 나타내는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b7d66-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7d66-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b7d66-116">Child Elements</span></span>  
 <span data-ttu-id="b7d66-117">없음</span><span class="sxs-lookup"><span data-stu-id="b7d66-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7d66-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b7d66-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b7d66-119">요소</span><span class="sxs-lookup"><span data-stu-id="b7d66-119">Element</span></span>|<span data-ttu-id="b7d66-120">설명</span><span class="sxs-lookup"><span data-stu-id="b7d66-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7d66-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b7d66-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b7d66-122">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7d66-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7d66-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7d66-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
