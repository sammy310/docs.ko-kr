---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855289"
---
# \<endToEndTracing>
<span data-ttu-id="9163e-101">서비스 애플리케이션 실행 중에 엔드투엔드 추적의 다양한 측면을 사용하거나 사용하지 않도록 설정할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9163e-101">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="9163e-102">구문</span><span class="sxs-lookup"><span data-stu-id="9163e-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9163e-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9163e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9163e-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9163e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9163e-105">특성</span><span class="sxs-lookup"><span data-stu-id="9163e-105">Attributes</span></span>  
  
|<span data-ttu-id="9163e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="9163e-106">Attribute</span></span>|<span data-ttu-id="9163e-107">Description</span><span class="sxs-lookup"><span data-stu-id="9163e-107">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="9163e-108">활동 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9163e-108">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="9163e-109">메시지 흐름 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9163e-109">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="9163e-110">propagate 특성을 true로 설정할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9163e-110">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9163e-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9163e-111">Child Elements</span></span>  
 <span data-ttu-id="9163e-112">없음</span><span class="sxs-lookup"><span data-stu-id="9163e-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9163e-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9163e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="9163e-114">요소</span><span class="sxs-lookup"><span data-stu-id="9163e-114">Element</span></span>|<span data-ttu-id="9163e-115">Description</span><span class="sxs-lookup"><span data-stu-id="9163e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="9163e-116">관리자의 런타임 검사 및 제어를 위한 WCF 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9163e-116">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9163e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9163e-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="9163e-118">엔드투엔드 추적</span><span class="sxs-lookup"><span data-stu-id="9163e-118">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
