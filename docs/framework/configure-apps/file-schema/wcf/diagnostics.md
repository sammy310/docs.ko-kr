---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 2749bc6c66d491a8a160d98b508fb43aa027b806
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398047"
---
# \<diagnostics>
<span data-ttu-id="960a0-101">`diagnostics` 요소는 관리자가 런타임 검사 및 제어에 사용할 수 있는 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-101">The `diagnostics` element defines settings that can be used by an administrator for run-time inspection and control.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="960a0-102">구문</span><span class="sxs-lookup"><span data-stu-id="960a0-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="960a0-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="960a0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="960a0-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="960a0-105">특성</span><span class="sxs-lookup"><span data-stu-id="960a0-105">Attributes</span></span>  
  
|<span data-ttu-id="960a0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="960a0-106">Attribute</span></span>|<span data-ttu-id="960a0-107">Description</span><span class="sxs-lookup"><span data-stu-id="960a0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="960a0-108">etwProviderId</span><span class="sxs-lookup"><span data-stu-id="960a0-108">etwProviderId</span></span>|<span data-ttu-id="960a0-109">ETW 세션에 이벤트를 기록하는 이벤트 추적 공급자에 대한 식별자를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-109">A string that specifies the identifier for the Event-Tracing provider, which writes events to ETW sessions.</span></span>|  
|<span data-ttu-id="960a0-110">performanceCounters</span><span class="sxs-lookup"><span data-stu-id="960a0-110">performanceCounters</span></span>|<span data-ttu-id="960a0-111">어셈블리에 대해 성능 카운터를 사용할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-111">Specifies whether performance counters for the assembly are enabled.</span></span> <span data-ttu-id="960a0-112">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-112">Valid values are</span></span><br /><br /> <span data-ttu-id="960a0-113">-Off: 성능 카운터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-113">-   Off: Performance counters are disabled.</span></span><br /><span data-ttu-id="960a0-114">-ServiceOnly:이 서비스와 관련 된 성능 카운터만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-114">-   ServiceOnly: Only performance counters relevant to this service is enabled.</span></span><br /><span data-ttu-id="960a0-115">-All: 성능 카운터를 런타임에 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-115">-   All: Performance counters can be viewed at runtime.</span></span><br /><span data-ttu-id="960a0-116">-기본값: 단일 성능 카운터 인스턴스 _WCF_Admin 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-116">-   Default: A single performance counter instance _WCF_Admin is created.</span></span> <span data-ttu-id="960a0-117">이 인스턴스는 인프라에서 사용되는 SQM 데이터 컬렉션을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-117">This instance is used to enable the collection of SQM data for used by the infrastructure.</span></span> <span data-ttu-id="960a0-118">이 인스턴스의 어떤 카운터 값도 업데이트되지 않으므로 0으로 남게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-118">None of the counter values for this instance are updated and therefore will remain at zero.</span></span> <span data-ttu-id="960a0-119">이것은 WCF에 대한 구성이 없을 경우 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-119">This is the default value if no configuration is present for WCF.</span></span>|  
|<span data-ttu-id="960a0-120">wmiProviderEnabled</span><span class="sxs-lookup"><span data-stu-id="960a0-120">wmiProviderEnabled</span></span>|<span data-ttu-id="960a0-121">어셈블리에 대해 WMI 공급자를 사용할 수 있는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-121">A Boolean value that specifies whether the WMI provider for the assembly is enabled.</span></span> <span data-ttu-id="960a0-122">사용자가 WCF(Windows Communication Foundation)의 검사 및 제어 기능에 대해 런타임 액세스 권한을 얻으려면 WMI 공급자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-122">The WMI provider is required for user to gain run-time access to the inspection and control features of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="960a0-123">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-123">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="960a0-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="960a0-124">Child Elements</span></span>  
  
|<span data-ttu-id="960a0-125">요소</span><span class="sxs-lookup"><span data-stu-id="960a0-125">Element</span></span>|<span data-ttu-id="960a0-126">Description</span><span class="sxs-lookup"><span data-stu-id="960a0-126">Description</span></span>|  
|-------------|-----------------|  
|[\<endToEndTracing>](endtoendtracing.md)|<span data-ttu-id="960a0-127">서비스 애플리케이션 실행 중에 엔드투엔드 추적의 다양한 측면을 사용하거나 사용하지 않도록 설정할 수 있는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-127">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>|  
|[\<messageLogging>](messagelogging.md)|<span data-ttu-id="960a0-128">WCF 메시지 로깅의 설정을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-128">Describes the settings for WCF message logging.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="960a0-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="960a0-129">Parent Elements</span></span>  
  
|<span data-ttu-id="960a0-130">요소</span><span class="sxs-lookup"><span data-stu-id="960a0-130">Element</span></span>|<span data-ttu-id="960a0-131">Description</span><span class="sxs-lookup"><span data-stu-id="960a0-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="960a0-132">serviceModel</span><span class="sxs-lookup"><span data-stu-id="960a0-132">serviceModel</span></span>|<span data-ttu-id="960a0-133">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="960a0-134">설명</span><span class="sxs-lookup"><span data-stu-id="960a0-134">Remarks</span></span>  
 <span data-ttu-id="960a0-135">`diagnostics` 섹션에서는 어셈블리에 있는 모든 서비스의 진단 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-135">The `diagnostics` section defines the diagnostics settings for all services located in an assembly.</span></span> <span data-ttu-id="960a0-136">어셈블리에 서비스가 하나만 있는 경우가 아니라면 서비스 수준에서 별도의 진단 설정을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-136">It is not possible to define separate diagnostics settings at the service level unless there is only one service in the assembly.</span></span> <span data-ttu-id="960a0-137">해당 섹션의 요구 사항에 따라 특성이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="960a0-137">Attributes are set according to the requirements of the section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="960a0-138">예제</span><span class="sxs-lookup"><span data-stu-id="960a0-138">Example</span></span>  
  
```xml  
<diagnostics wmiProviderEnabled="false"
             performanceCounters="all">
  <messageLogging logEntireMessage="true"
                  logMalformedMessages="true"
                  logMessagesAtServiceLevel="true"
                  logMessagesAtTransportLevel="true"
                  maxMessagesToLog="42"
                  maxSizeOfMessageToLog="42">
    <filters>
      <clear />
    </filters>
  </messageLogging>
</diagnostics>
```  
  
## <a name="see-also"></a><span data-ttu-id="960a0-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="960a0-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
