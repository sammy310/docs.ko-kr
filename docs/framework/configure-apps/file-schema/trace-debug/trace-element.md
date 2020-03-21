---
title: <trace> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153168"
---
# <a name="trace-element"></a><span data-ttu-id="c53c3-102">\<추적> 요소</span><span class="sxs-lookup"><span data-stu-id="c53c3-102">\<trace> Element</span></span>
<span data-ttu-id="c53c3-103">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[<span data-ttu-id="c53c3-104">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="c53c3-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c53c3-105">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="c53c3-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="c53c3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<추적>**</span><span class="sxs-lookup"><span data-stu-id="c53c3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c53c3-107">구문</span><span class="sxs-lookup"><span data-stu-id="c53c3-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c53c3-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c53c3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c53c3-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c53c3-110">특성</span><span class="sxs-lookup"><span data-stu-id="c53c3-110">Attributes</span></span>  
  
|<span data-ttu-id="c53c3-111">attribute</span><span class="sxs-lookup"><span data-stu-id="c53c3-111">Attribute</span></span>|<span data-ttu-id="c53c3-112">Description</span><span class="sxs-lookup"><span data-stu-id="c53c3-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="c53c3-113">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c53c3-114">추적 리스너가 모든 쓰기 작업 후에 출력 버퍼를 자동으로 플러시할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="c53c3-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c53c3-116">들여쓰기할 공백 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="c53c3-117">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c53c3-118">전역 잠금을 사용해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="c53c3-119">자동 플러시 특성</span><span class="sxs-lookup"><span data-stu-id="c53c3-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="c53c3-120">값</span><span class="sxs-lookup"><span data-stu-id="c53c3-120">Value</span></span>|<span data-ttu-id="c53c3-121">Description</span><span class="sxs-lookup"><span data-stu-id="c53c3-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c53c3-122">출력 버퍼를 자동으로 플러시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="c53c3-123">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c53c3-124">출력 버퍼를 자동으로 플러시합니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="c53c3-125">use글로벌록 속성</span><span class="sxs-lookup"><span data-stu-id="c53c3-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="c53c3-126">값</span><span class="sxs-lookup"><span data-stu-id="c53c3-126">Value</span></span>|<span data-ttu-id="c53c3-127">Description</span><span class="sxs-lookup"><span data-stu-id="c53c3-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c53c3-128">수신기가 스레드에 안전한 경우 전역 잠금을 사용하지 않습니다. 그렇지 않으면 전역 잠금을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="c53c3-129">수신기가 스레드에 안전한지 여부에 관계없이 전역 잠금을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="c53c3-130">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c53c3-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c53c3-131">Child Elements</span></span>  
  
|<span data-ttu-id="c53c3-132">요소</span><span class="sxs-lookup"><span data-stu-id="c53c3-132">Element</span></span>|<span data-ttu-id="c53c3-133">Description</span><span class="sxs-lookup"><span data-stu-id="c53c3-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c53c3-134">\<청취자></span><span class="sxs-lookup"><span data-stu-id="c53c3-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="c53c3-135">메시지를 수집, 저장 및 라우팅하는 수신기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c53c3-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c53c3-136">Parent Elements</span></span>  
  
|<span data-ttu-id="c53c3-137">요소</span><span class="sxs-lookup"><span data-stu-id="c53c3-137">Element</span></span>|<span data-ttu-id="c53c3-138">Description</span><span class="sxs-lookup"><span data-stu-id="c53c3-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c53c3-139">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c53c3-140">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c53c3-141">예제</span><span class="sxs-lookup"><span data-stu-id="c53c3-141">Example</span></span>  
 <span data-ttu-id="c53c3-142">다음 예제에서는 요소를 사용하여 `<trace>` 컬렉션에 리스터를 `MyListener` 추가하는 `Listeners` 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="c53c3-143">`MyListener`이라는 이름의 `MyListener.log` 파일을 만들고 출력을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="c53c3-144">특성은 `useGlobalLock` `false`로 설정되어 추적 수신기가 스레드에서 안전한 경우 전역 잠금을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="c53c3-145">특성은 `autoflush` `true`로 설정되어 추적 수신기가 <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> 메서드가 호출되는지 여부에 관계없이 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="c53c3-146">특성은 `indentsize` 0(0)으로 설정되어 메서드가 호출될 때 수신기가 0 공백을 <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> 들여쓰기합니다.</span><span class="sxs-lookup"><span data-stu-id="c53c3-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c53c3-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c53c3-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="c53c3-148">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c53c3-148">Trace and Debug Settings Schema</span></span>](index.md)
