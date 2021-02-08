---
description: 다음에 대해 자세히 알아보세요. <endToEndTracing>
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 2ac4a7563d7d7881cdb503e843d34f84fd9c95a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782119"
---
# \<endToEndTracing>

<span data-ttu-id="a820a-102">서비스 애플리케이션 실행 중에 엔드투엔드 추적의 다양한 측면을 사용하거나 사용하지 않도록 설정할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a820a-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="a820a-103">구문</span><span class="sxs-lookup"><span data-stu-id="a820a-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a820a-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a820a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a820a-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a820a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a820a-106">특성</span><span class="sxs-lookup"><span data-stu-id="a820a-106">Attributes</span></span>  
  
|<span data-ttu-id="a820a-107">attribute</span><span class="sxs-lookup"><span data-stu-id="a820a-107">Attribute</span></span>|<span data-ttu-id="a820a-108">설명</span><span class="sxs-lookup"><span data-stu-id="a820a-108">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="a820a-109">활동 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a820a-109">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="a820a-110">메시지 흐름 추적 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a820a-110">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="a820a-111">propagate 특성을 true로 설정할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a820a-111">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a820a-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a820a-112">Child Elements</span></span>  

 <span data-ttu-id="a820a-113">없음</span><span class="sxs-lookup"><span data-stu-id="a820a-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a820a-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a820a-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a820a-115">요소</span><span class="sxs-lookup"><span data-stu-id="a820a-115">Element</span></span>|<span data-ttu-id="a820a-116">설명</span><span class="sxs-lookup"><span data-stu-id="a820a-116">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="a820a-117">관리자의 런타임 검사 및 제어를 위한 WCF 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a820a-117">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a820a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a820a-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="a820a-119">엔드투엔드 추적</span><span class="sxs-lookup"><span data-stu-id="a820a-119">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
