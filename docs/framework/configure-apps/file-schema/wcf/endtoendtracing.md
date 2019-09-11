---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855289"
---
# <a name="endtoendtracing"></a><span data-ttu-id="470f2-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="470f2-101">\<endToEndTracing></span></span>
<span data-ttu-id="470f2-102">서비스 애플리케이션 실행 중에 엔드투엔드 추적의 다양한 측면을 사용하거나 사용하지 않도록 설정할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="470f2-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
<span data-ttu-id="470f2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="470f2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="470f2-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="470f2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="470f2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<진단 >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="470f2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="470f2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<endToEndTracing >**</span><span class="sxs-lookup"><span data-stu-id="470f2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="470f2-107">구문</span><span class="sxs-lookup"><span data-stu-id="470f2-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="470f2-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="470f2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="470f2-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="470f2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="470f2-110">특성</span><span class="sxs-lookup"><span data-stu-id="470f2-110">Attributes</span></span>  
  
|<span data-ttu-id="470f2-111">특성</span><span class="sxs-lookup"><span data-stu-id="470f2-111">Attribute</span></span>|<span data-ttu-id="470f2-112">Description</span><span class="sxs-lookup"><span data-stu-id="470f2-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="470f2-113">활동 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="470f2-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="470f2-114">메시지 흐름 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="470f2-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="470f2-115">propagate 특성을 true로 설정할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="470f2-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="470f2-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="470f2-116">Child Elements</span></span>  
 <span data-ttu-id="470f2-117">없음</span><span class="sxs-lookup"><span data-stu-id="470f2-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="470f2-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="470f2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="470f2-119">요소</span><span class="sxs-lookup"><span data-stu-id="470f2-119">Element</span></span>|<span data-ttu-id="470f2-120">설명</span><span class="sxs-lookup"><span data-stu-id="470f2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="470f2-121">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="470f2-121">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="470f2-122">관리자의 런타임 검사 및 제어를 위한 WCF 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="470f2-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="470f2-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="470f2-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="470f2-124">엔드투엔드 추적</span><span class="sxs-lookup"><span data-stu-id="470f2-124">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
