---
title: < System.diagnostics > 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 026805ffb9b89aa55e84cf9a5c4afb8ed63cec09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142716"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="f0c89-102">\<system.diagnostics> Element</span><span class="sxs-lookup"><span data-stu-id="f0c89-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="f0c89-103">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="f0c89-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f0c89-104">\<configuration></span></span>  
<span data-ttu-id="f0c89-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="f0c89-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c89-106">구문</span><span class="sxs-lookup"><span data-stu-id="f0c89-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0c89-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f0c89-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f0c89-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0c89-109">특성</span><span class="sxs-lookup"><span data-stu-id="f0c89-109">Attributes</span></span>  
 <span data-ttu-id="f0c89-110">없음</span><span class="sxs-lookup"><span data-stu-id="f0c89-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f0c89-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f0c89-111">Child Elements</span></span>  
  
|<span data-ttu-id="f0c89-112">요소</span><span class="sxs-lookup"><span data-stu-id="f0c89-112">Element</span></span>|<span data-ttu-id="f0c89-113">설명</span><span class="sxs-lookup"><span data-stu-id="f0c89-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0c89-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="f0c89-114">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="f0c89-115"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정합니다. 또한 메시지를 작성할 파일의 이름도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="f0c89-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="f0c89-116">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="f0c89-117">성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="f0c89-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="f0c89-118">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="f0c89-119">소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="f0c89-120">공유 수신기로 식별 하는 수신기 이름으로 추적 소스를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="f0c89-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="f0c89-121">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="f0c89-122">추적 메시지를 시작 하는 추적 소스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="f0c89-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="f0c89-123">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="f0c89-124">추적 스위치 및 추적 스위치가 설정 되어 있는 수준에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="f0c89-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="f0c89-125">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="f0c89-126">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0c89-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f0c89-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f0c89-128">요소</span><span class="sxs-lookup"><span data-stu-id="f0c89-128">Element</span></span>|<span data-ttu-id="f0c89-129">설명</span><span class="sxs-lookup"><span data-stu-id="f0c89-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f0c89-130">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f0c89-131">예제</span><span class="sxs-lookup"><span data-stu-id="f0c89-131">Example</span></span>  
 <span data-ttu-id="f0c89-132">다음 예제에서는 추적 스위치 및 내부 추적 수신기를 포함 하는  **\<system.diagnostics >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="f0c89-133">합니다 `General` 추적 스위치가 설정 된는 <xref:System.Diagnostics.TraceLevel> 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="f0c89-134">추적 수신기 `myListener` 라는 파일을 만들고 `MyListener.log` 출력 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0c89-135">.NET Framework 버전 2.0에서는 텍스트를 사용하여 스위치의 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="f0c89-136">예를 들어 지정할 수 있습니다 `true` 에 대 한는 <xref:System.Diagnostics.BooleanSwitch> 와 같은 열거형 값을 나타내는 텍스트를 사용 하거나 `Error` 에 대 한는 <xref:System.Diagnostics.TraceSwitch>합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="f0c89-137">`<add name="myTraceSwitch" value="Error" />` 줄은 `<add name="myTraceSwitch" value="1" />`과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c89-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0c89-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="f0c89-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="f0c89-139">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f0c89-139">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
