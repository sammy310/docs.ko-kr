---
description: '다음에 대 한 자세한 정보: <trace> 요소'
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
ms.openlocfilehash: 470bc300911656a9c9951e52e3883ba5c8b01c59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750327"
---
# <a name="trace-element"></a><span data-ttu-id="1aa46-103">\<trace> 요소</span><span class="sxs-lookup"><span data-stu-id="1aa46-103">\<trace> Element</span></span>

<span data-ttu-id="1aa46-104">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-104">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**  
  
## <a name="syntax"></a><span data-ttu-id="1aa46-105">구문</span><span class="sxs-lookup"><span data-stu-id="1aa46-105">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1aa46-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1aa46-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1aa46-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1aa46-108">특성</span><span class="sxs-lookup"><span data-stu-id="1aa46-108">Attributes</span></span>  
  
|<span data-ttu-id="1aa46-109">attribute</span><span class="sxs-lookup"><span data-stu-id="1aa46-109">Attribute</span></span>|<span data-ttu-id="1aa46-110">설명</span><span class="sxs-lookup"><span data-stu-id="1aa46-110">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="1aa46-111">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1aa46-112">모든 쓰기 작업 후 추적 수신기가 출력 버퍼를 자동으로 플러시하지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-112">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="1aa46-113">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1aa46-114">들여쓸 공백의 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-114">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="1aa46-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1aa46-116">전역 잠금을 사용 해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-116">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="1aa46-117">autoflush 특성</span><span class="sxs-lookup"><span data-stu-id="1aa46-117">autoflush Attribute</span></span>  
  
|<span data-ttu-id="1aa46-118">값</span><span class="sxs-lookup"><span data-stu-id="1aa46-118">Value</span></span>|<span data-ttu-id="1aa46-119">설명</span><span class="sxs-lookup"><span data-stu-id="1aa46-119">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1aa46-120">는 출력 버퍼를 자동으로 플러시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-120">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="1aa46-121">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-121">This is the default.</span></span>|  
|`true`|<span data-ttu-id="1aa46-122">출력 버퍼를 자동으로 플러시합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-122">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="1aa46-123">useGlobalLock 특성</span><span class="sxs-lookup"><span data-stu-id="1aa46-123">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="1aa46-124">값</span><span class="sxs-lookup"><span data-stu-id="1aa46-124">Value</span></span>|<span data-ttu-id="1aa46-125">설명</span><span class="sxs-lookup"><span data-stu-id="1aa46-125">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1aa46-126">수신기가 스레드로부터 안전 하 게 보호 되는 경우 전역 잠금을 사용 하지 않습니다. 그렇지 않으면 전역 잠금을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-126">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="1aa46-127">수신기가 스레드로부터 안전한 지 여부에 관계 없이 전역 잠금을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-127">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="1aa46-128">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-128">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1aa46-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1aa46-129">Child Elements</span></span>  
  
|<span data-ttu-id="1aa46-130">요소</span><span class="sxs-lookup"><span data-stu-id="1aa46-130">Element</span></span>|<span data-ttu-id="1aa46-131">설명</span><span class="sxs-lookup"><span data-stu-id="1aa46-131">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|<span data-ttu-id="1aa46-132">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-132">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1aa46-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1aa46-133">Parent Elements</span></span>  
  
|<span data-ttu-id="1aa46-134">요소</span><span class="sxs-lookup"><span data-stu-id="1aa46-134">Element</span></span>|<span data-ttu-id="1aa46-135">설명</span><span class="sxs-lookup"><span data-stu-id="1aa46-135">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1aa46-136">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-136">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1aa46-137">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-137">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1aa46-138">예제</span><span class="sxs-lookup"><span data-stu-id="1aa46-138">Example</span></span>  

 <span data-ttu-id="1aa46-139">다음 예제에서는 요소를 사용 하 여 `<trace>` 컬렉션에 수신기를 추가 하는 방법을 보여 줍니다 `MyListener` `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="1aa46-139">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="1aa46-140">`MyListener` 이라는 파일을 만들고 출력을 `MyListener.log` 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-140">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="1aa46-141">`useGlobalLock`특성은로 설정 되며 `false` ,이로 인해 추적 수신기가 스레드로부터 안전 하 게 보호 되는 경우 전역 잠금이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-141">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="1aa46-142">`autoflush`특성은로 설정 되며 `true` ,이로 인해 메서드가 호출 되었는지 여부에 관계 없이 추적 수신기가 파일에 쓸 수 <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa46-142">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="1aa46-143">`indentsize`특성이 0으로 설정 되 면 메서드가 호출 될 때 수신기가 공백을 0으로 들여씁니다 <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1aa46-143">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1aa46-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1aa46-144">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="1aa46-145">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="1aa46-145">Trace and Debug Settings Schema</span></span>](index.md)
