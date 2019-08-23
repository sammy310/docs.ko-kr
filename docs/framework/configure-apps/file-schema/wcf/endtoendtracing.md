---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 6b23728451a051f21ad3863b9a29e6290c3c837a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919009"
---
# <a name="endtoendtracing"></a><span data-ttu-id="8fcf5-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="8fcf5-101">\<endToEndTracing></span></span>
<span data-ttu-id="8fcf5-102">서비스 애플리케이션 실행 중에 엔드투엔드 추적의 다양한 측면을 사용하거나 사용하지 않도록 설정할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8fcf5-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="8fcf5-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8fcf5-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8fcf5-104">\<diagnostic></span><span class="sxs-lookup"><span data-stu-id="8fcf5-104">\<diagnostic></span></span>  
<span data-ttu-id="8fcf5-105">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="8fcf5-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fcf5-106">구문</span><span class="sxs-lookup"><span data-stu-id="8fcf5-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fcf5-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8fcf5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8fcf5-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8fcf5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fcf5-109">특성</span><span class="sxs-lookup"><span data-stu-id="8fcf5-109">Attributes</span></span>  
  
|<span data-ttu-id="8fcf5-110">특성</span><span class="sxs-lookup"><span data-stu-id="8fcf5-110">Attribute</span></span>|<span data-ttu-id="8fcf5-111">Description</span><span class="sxs-lookup"><span data-stu-id="8fcf5-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="8fcf5-112">활동 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8fcf5-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="8fcf5-113">메시지 흐름 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8fcf5-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="8fcf5-114">propagate 특성을 true로 설정할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8fcf5-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fcf5-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8fcf5-115">Child Elements</span></span>  
 <span data-ttu-id="8fcf5-116">없음</span><span class="sxs-lookup"><span data-stu-id="8fcf5-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fcf5-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8fcf5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8fcf5-118">요소</span><span class="sxs-lookup"><span data-stu-id="8fcf5-118">Element</span></span>|<span data-ttu-id="8fcf5-119">설명</span><span class="sxs-lookup"><span data-stu-id="8fcf5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fcf5-120">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="8fcf5-120">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="8fcf5-121">관리자의 런타임 검사 및 제어를 위한 WCF 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8fcf5-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8fcf5-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="8fcf5-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="8fcf5-123">엔드투엔드 추적</span><span class="sxs-lookup"><span data-stu-id="8fcf5-123">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
