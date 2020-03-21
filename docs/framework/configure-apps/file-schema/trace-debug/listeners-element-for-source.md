---
title: <source>에 대한 <listeners> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 0eee325e01b41a15a19e4f40f479596f9d70f73b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153414"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="25537-102">\<청취자> 소스 \<> 대한 요소</span><span class="sxs-lookup"><span data-stu-id="25537-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="25537-103"><xref:System.Diagnostics.TraceSource>에 대한 컬렉션의 <xref:System.Diagnostics.TraceSource.Listeners%2A> 리스너를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="25537-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="25537-104">수신기는 추적 출력을 로그, 창 또는 텍스트 파일과 같은 적절한 대상으로 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="25537-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="25537-105">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="25537-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="25537-106">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="25537-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="25537-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="25537-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="25537-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="25537-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="25537-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<청취자>**</span><span class="sxs-lookup"><span data-stu-id="25537-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25537-110">구문</span><span class="sxs-lookup"><span data-stu-id="25537-110">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25537-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="25537-111">Attributes and Elements</span></span>  
 <span data-ttu-id="25537-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="25537-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25537-113">특성</span><span class="sxs-lookup"><span data-stu-id="25537-113">Attributes</span></span>  
 <span data-ttu-id="25537-114">없음</span><span class="sxs-lookup"><span data-stu-id="25537-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="25537-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="25537-115">Child Elements</span></span>  
  
|<span data-ttu-id="25537-116">요소</span><span class="sxs-lookup"><span data-stu-id="25537-116">Element</span></span>|<span data-ttu-id="25537-117">Description</span><span class="sxs-lookup"><span data-stu-id="25537-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25537-118">\<>추가</span><span class="sxs-lookup"><span data-stu-id="25537-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="25537-119">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25537-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="25537-120">\<>제거</span><span class="sxs-lookup"><span data-stu-id="25537-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="25537-121">컬렉션에서 수신기를 제거합니다. `Listeners`</span><span class="sxs-lookup"><span data-stu-id="25537-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="25537-122">\<클리어></span><span class="sxs-lookup"><span data-stu-id="25537-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="25537-123">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="25537-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25537-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="25537-124">Parent Elements</span></span>  
  
|<span data-ttu-id="25537-125">요소</span><span class="sxs-lookup"><span data-stu-id="25537-125">Element</span></span>|<span data-ttu-id="25537-126">Description</span><span class="sxs-lookup"><span data-stu-id="25537-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="25537-127">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="25537-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="25537-128">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25537-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="25537-129">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25537-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="25537-130">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="25537-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25537-131">설명</span><span class="sxs-lookup"><span data-stu-id="25537-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="25537-132">구성 파일</span><span class="sxs-lookup"><span data-stu-id="25537-132">Configuration File</span></span>  
 <span data-ttu-id="25537-133">이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25537-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25537-134">예제</span><span class="sxs-lookup"><span data-stu-id="25537-134">Example</span></span>  
 <span data-ttu-id="25537-135">다음 예제에서는 `<listeners>` 요소를 사용하여 콘솔 추적 수신기를 소스에 `mySource` 추가하고 기본 추적 리스너를 제거하는 방법을 보여 주며, 이 예제에서는 이 요소를 사용하는 방법을 보여 주며, 이 예제에서는 이 요소를 사용하여 소스에 대한 추적 리스너를 제거하는 방법을 보여 주며, 이 예제에서는 이 요소를 사용하여 소스에 대한 추적 리스너를 제거하는 방법을 보여 주며, 이 예제에서는 이 요소를 사용하여 소스에 콘솔 추적 리스너를 추가하는</span><span class="sxs-lookup"><span data-stu-id="25537-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="25537-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25537-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="25537-137">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="25537-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="25537-138">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="25537-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
