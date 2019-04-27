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
ms.openlocfilehash: 5faf352dce2a459a999b3cf54209f6bd9793bde0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673799"
---
# <a name="trace-element"></a><span data-ttu-id="2cfd5-102">\<추적 > 요소</span><span class="sxs-lookup"><span data-stu-id="2cfd5-102">\<trace> Element</span></span>
<span data-ttu-id="2cfd5-103">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="2cfd5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2cfd5-104">\<configuration></span></span>  
<span data-ttu-id="2cfd5-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="2cfd5-105">\<system.diagnostics></span></span>  
<span data-ttu-id="2cfd5-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="2cfd5-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cfd5-107">구문</span><span class="sxs-lookup"><span data-stu-id="2cfd5-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cfd5-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2cfd5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2cfd5-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cfd5-110">특성</span><span class="sxs-lookup"><span data-stu-id="2cfd5-110">Attributes</span></span>  
  
|<span data-ttu-id="2cfd5-111">특성</span><span class="sxs-lookup"><span data-stu-id="2cfd5-111">Attribute</span></span>|<span data-ttu-id="2cfd5-112">설명</span><span class="sxs-lookup"><span data-stu-id="2cfd5-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="2cfd5-113">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2cfd5-114">추적 수신기에 모든 쓰기 작업 후 출력 버퍼를 자동으로 플러시 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="2cfd5-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2cfd5-116">들여쓸 공백의 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="2cfd5-117">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2cfd5-118">전역 잠금을 사용할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="2cfd5-119">autoflush 특성</span><span class="sxs-lookup"><span data-stu-id="2cfd5-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="2cfd5-120">값</span><span class="sxs-lookup"><span data-stu-id="2cfd5-120">Value</span></span>|<span data-ttu-id="2cfd5-121">설명</span><span class="sxs-lookup"><span data-stu-id="2cfd5-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2cfd5-122">출력 버퍼를 자동으로 플러시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="2cfd5-123">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="2cfd5-124">자동으로 출력 버퍼를 플러시합니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="2cfd5-125">useGlobalLock 특성</span><span class="sxs-lookup"><span data-stu-id="2cfd5-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="2cfd5-126">값</span><span class="sxs-lookup"><span data-stu-id="2cfd5-126">Value</span></span>|<span data-ttu-id="2cfd5-127">설명</span><span class="sxs-lookup"><span data-stu-id="2cfd5-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2cfd5-128">수신기가 스레드로부터 안전; 전역 잠금을 사용 하지 않습니다. 그렇지 않으면 전역 잠금을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="2cfd5-129">수신기가 스레드로부터 안전 여부에 관계 없이 전역 잠금을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="2cfd5-130">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2cfd5-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2cfd5-131">Child Elements</span></span>  
  
|<span data-ttu-id="2cfd5-132">요소</span><span class="sxs-lookup"><span data-stu-id="2cfd5-132">Element</span></span>|<span data-ttu-id="2cfd5-133">설명</span><span class="sxs-lookup"><span data-stu-id="2cfd5-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cfd5-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="2cfd5-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="2cfd5-135">저장소를 수집 하는 수신기를 지정 하 고 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cfd5-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2cfd5-136">Parent Elements</span></span>  
  
|<span data-ttu-id="2cfd5-137">요소</span><span class="sxs-lookup"><span data-stu-id="2cfd5-137">Element</span></span>|<span data-ttu-id="2cfd5-138">설명</span><span class="sxs-lookup"><span data-stu-id="2cfd5-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2cfd5-139">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2cfd5-140">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2cfd5-141">예제</span><span class="sxs-lookup"><span data-stu-id="2cfd5-141">Example</span></span>  
 <span data-ttu-id="2cfd5-142">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<trace>` 수신기에 추가할 요소 `MyListener` 에 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="2cfd5-143">`MyListener` 라는 파일을 만듭니다 `MyListener.log` 출력 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="2cfd5-144">합니다 `useGlobalLock` 특성이로 설정 된 `false`, 전역 잠금을 사용 하 여 추적 수신기가 스레드로부터 안전 하지 그러면 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="2cfd5-145">`autoflush` 특성이로 설정 된 `true`, 여부에 관계 없이 파일에 쓸 추적 수신기에 이르게 합니다 <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="2cfd5-146">`indentsize` 특성이 0 공백 들여쓰기 수신기는 0 (영)로 설정 된 경우는 <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cfd5-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2cfd5-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="2cfd5-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="2cfd5-148">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2cfd5-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
