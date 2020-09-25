---
title: <diagnostics> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: aff324ac9952c95c78d7ca15572651dba23b79b7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195170"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="389bd-102">\<system.diagnostics> 요소</span><span class="sxs-lookup"><span data-stu-id="389bd-102">\<system.diagnostics> Element</span></span>

<span data-ttu-id="389bd-103">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="389bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="389bd-104">Syntax</span></span>  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="389bd-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="389bd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="389bd-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="389bd-107">특성</span><span class="sxs-lookup"><span data-stu-id="389bd-107">Attributes</span></span>  

 <span data-ttu-id="389bd-108">없음</span><span class="sxs-lookup"><span data-stu-id="389bd-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="389bd-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="389bd-109">Child Elements</span></span>  
  
|<span data-ttu-id="389bd-110">요소</span><span class="sxs-lookup"><span data-stu-id="389bd-110">Element</span></span>|<span data-ttu-id="389bd-111">설명</span><span class="sxs-lookup"><span data-stu-id="389bd-111">Description</span></span>|  
|-------------|-----------------|  
|[\<assert>](assert-element.md)|<span data-ttu-id="389bd-112"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정합니다. 또한 메시지를 작성할 파일의 이름도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-112">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[\<performanceCounters>](performancecounters-element.md)|<span data-ttu-id="389bd-113">성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-113">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[\<sharedListeners>](sharedlisteners-element.md)|<span data-ttu-id="389bd-114">소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-114">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="389bd-115">공유 수신기로 식별 된 수신기는 이름으로 원본 또는 추적에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-115">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[\<sources>](sources-element.md)|<span data-ttu-id="389bd-116">추적 메시지를 시작 하는 추적 소스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-116">Specifies trace sources that initiate tracing messages.</span></span>|  
|[\<switches>](switches-element.md)|<span data-ttu-id="389bd-117">추적 스위치 및 추적 스위치가 설정 된 수준을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-117">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[\<trace>](trace-element.md)|<span data-ttu-id="389bd-118">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-118">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="389bd-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="389bd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="389bd-120">요소</span><span class="sxs-lookup"><span data-stu-id="389bd-120">Element</span></span>|<span data-ttu-id="389bd-121">설명</span><span class="sxs-lookup"><span data-stu-id="389bd-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="389bd-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="389bd-123">예제</span><span class="sxs-lookup"><span data-stu-id="389bd-123">Example</span></span>  

 <span data-ttu-id="389bd-124">다음 예제에서는 추적 스위치 및 추적 수신기를 요소 내에 포함 하는 방법을 보여 줍니다 **\<system.diagnostics>** .</span><span class="sxs-lookup"><span data-stu-id="389bd-124">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="389bd-125">`General`추적 스위치는 수준으로 설정 됩니다 <xref:System.Diagnostics.TraceLevel> .</span><span class="sxs-lookup"><span data-stu-id="389bd-125">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="389bd-126">추적 수신기는 `myListener` 라는 파일을 만들고 `MyListener.log` 출력을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-126">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="389bd-127">.NET Framework 버전 2.0에서는 텍스트를 사용 하 여 스위치의 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-127">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="389bd-128">예를 들어에 대해를 지정 `true` <xref:System.Diagnostics.BooleanSwitch> 하거나에 대해와 같이 열거형 값을 나타내는 텍스트를 사용할 수 있습니다 `Error` <xref:System.Diagnostics.TraceSwitch> .</span><span class="sxs-lookup"><span data-stu-id="389bd-128">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="389bd-129">줄은 `<add name="myTraceSwitch" value="Error" />` 와 동일 `<add name="myTraceSwitch" value="1" />` 합니다.</span><span class="sxs-lookup"><span data-stu-id="389bd-129">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="389bd-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="389bd-130">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="389bd-131">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="389bd-131">Trace and Debug Settings Schema</span></span>](index.md)
