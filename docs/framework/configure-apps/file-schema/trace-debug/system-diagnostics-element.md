---
title: <시스템.진단> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 4f831592d7d178276b1625e1ef7d8512085342af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153209"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="06cfd-102">\<시스템.진단> 요소</span><span class="sxs-lookup"><span data-stu-id="06cfd-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="06cfd-103">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[<span data-ttu-id="06cfd-104">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="06cfd-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="06cfd-105">&nbsp;&nbsp;**\<system.진단>**</span><span class="sxs-lookup"><span data-stu-id="06cfd-105">&nbsp;&nbsp;**\<system.diagnostics>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06cfd-106">구문</span><span class="sxs-lookup"><span data-stu-id="06cfd-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06cfd-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="06cfd-107">Attributes and Elements</span></span>  
 <span data-ttu-id="06cfd-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06cfd-109">특성</span><span class="sxs-lookup"><span data-stu-id="06cfd-109">Attributes</span></span>  
 <span data-ttu-id="06cfd-110">없음</span><span class="sxs-lookup"><span data-stu-id="06cfd-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="06cfd-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="06cfd-111">Child Elements</span></span>  
  
|<span data-ttu-id="06cfd-112">요소</span><span class="sxs-lookup"><span data-stu-id="06cfd-112">Element</span></span>|<span data-ttu-id="06cfd-113">Description</span><span class="sxs-lookup"><span data-stu-id="06cfd-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06cfd-114">\<어설션></span><span class="sxs-lookup"><span data-stu-id="06cfd-114">\<assert></span></span>](assert-element.md)|<span data-ttu-id="06cfd-115"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정합니다. 또한 메시지를 작성할 파일의 이름도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="06cfd-116">\<성능 카운터></span><span class="sxs-lookup"><span data-stu-id="06cfd-116">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="06cfd-117">성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="06cfd-118">\<공유청취자></span><span class="sxs-lookup"><span data-stu-id="06cfd-118">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="06cfd-119">소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="06cfd-120">공유 리스너로 식별된 수신기는 원본 또는 이름으로 추적에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="06cfd-121">\<소스></span><span class="sxs-lookup"><span data-stu-id="06cfd-121">\<sources></span></span>](sources-element.md)|<span data-ttu-id="06cfd-122">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="06cfd-123">\<>스위치</span><span class="sxs-lookup"><span data-stu-id="06cfd-123">\<switches></span></span>](switches-element.md)|<span data-ttu-id="06cfd-124">추적 스위치와 추적 스위치가 설정된 수준을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="06cfd-125">\<추적></span><span class="sxs-lookup"><span data-stu-id="06cfd-125">\<trace></span></span>](trace-element.md)|<span data-ttu-id="06cfd-126">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06cfd-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="06cfd-127">Parent Elements</span></span>  
  
|<span data-ttu-id="06cfd-128">요소</span><span class="sxs-lookup"><span data-stu-id="06cfd-128">Element</span></span>|<span data-ttu-id="06cfd-129">Description</span><span class="sxs-lookup"><span data-stu-id="06cfd-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="06cfd-130">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="06cfd-131">예제</span><span class="sxs-lookup"><span data-stu-id="06cfd-131">Example</span></span>  
 <span data-ttu-id="06cfd-132">다음 예제에서는 \*\* \<system.diagnostics>\*\* 요소 내에 추적 스위치와 추적 수신기를 포함 하는 방법을 보여 주입니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="06cfd-133">`General` 추적 스위치가 <xref:System.Diagnostics.TraceLevel> 수준으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="06cfd-134">추적 수신기는 `myListener` 라는 `MyListener.log` 파일을 만들고 파일에 출력을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06cfd-135">.NET Framework 버전 2.0에서 텍스트를 사용하여 스위치의 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="06cfd-136">`true` 예를 들어 에 <xref:System.Diagnostics.BooleanSwitch> 대해 지정하거나 `Error` <xref:System.Diagnostics.TraceSwitch>에 대해 와 같은 열거형 값을 나타내는 텍스트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="06cfd-137">선은 `<add name="myTraceSwitch" value="Error" />` `<add name="myTraceSwitch" value="1" />`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="06cfd-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="06cfd-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06cfd-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="06cfd-139">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="06cfd-139">Trace and Debug Settings Schema</span></span>](index.md)
