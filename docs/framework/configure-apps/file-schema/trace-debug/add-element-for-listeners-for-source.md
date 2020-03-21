---
title: <add>에 <listeners> 대 한 요소<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153687"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="d6796-102">\<소스> \<>> 요소를 추가합니다. \<</span><span class="sxs-lookup"><span data-stu-id="d6796-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="d6796-103">추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="d6796-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d6796-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d6796-105">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="d6796-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="d6796-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="d6796-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="d6796-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="d6796-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="d6796-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<청취자>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="d6796-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="d6796-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**</span><span class="sxs-lookup"><span data-stu-id="d6796-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d6796-110">구문</span><span class="sxs-lookup"><span data-stu-id="d6796-110">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6796-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d6796-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d6796-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6796-113">특성</span><span class="sxs-lookup"><span data-stu-id="d6796-113">Attributes</span></span>  
  
|<span data-ttu-id="d6796-114">attribute</span><span class="sxs-lookup"><span data-stu-id="d6796-114">Attribute</span></span>|<span data-ttu-id="d6796-115">Description</span><span class="sxs-lookup"><span data-stu-id="d6796-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="d6796-116">`sharedListeners` 컬렉션에서 리스너를 참조하지 않는 한 필수 특성은 이름으로만 참조하면 [됩니다(예제](#example)참조).</span><span class="sxs-lookup"><span data-stu-id="d6796-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="d6796-117">수신기의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-117">Specifies the type of the listener.</span></span> <span data-ttu-id="d6796-118">[정규화된 형식 이름 지정에](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)지정된 요구 사항을 충족하는 문자열을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="d6796-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d6796-120">문자열은 지정된 클래스의 생성자에게 전달되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="d6796-121">클래스에 문자열을 받는 생성자가 없는 경우 A가 <xref:System.Configuration.ConfigurationException> throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="d6796-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d6796-123">수신기의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="d6796-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d6796-125">추적 수신기에 <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> 대한 속성 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="d6796-126">[사용자 지정 속성]</span><span class="sxs-lookup"><span data-stu-id="d6796-126">[custom attributes]</span></span>|<span data-ttu-id="d6796-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="d6796-128">해당 수신기에 대 한 메서드에서 식별 하는 <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> 수신기 별 특성에 대 한 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="d6796-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>는 클래스에 고유한 추가 특성의 <xref:System.Diagnostics.DelimitedListTraceListener> 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6796-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d6796-130">Child Elements</span></span>  
  
|<span data-ttu-id="d6796-131">요소</span><span class="sxs-lookup"><span data-stu-id="d6796-131">Element</span></span>|<span data-ttu-id="d6796-132">Description</span><span class="sxs-lookup"><span data-stu-id="d6796-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6796-133">\<필터></span><span class="sxs-lookup"><span data-stu-id="d6796-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="d6796-134">추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6796-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d6796-135">Parent Elements</span></span>  
  
|<span data-ttu-id="d6796-136">요소</span><span class="sxs-lookup"><span data-stu-id="d6796-136">Element</span></span>|<span data-ttu-id="d6796-137">Description</span><span class="sxs-lookup"><span data-stu-id="d6796-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d6796-138">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d6796-139">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="d6796-140">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="d6796-141">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d6796-142">메시지를 수집, 저장 및 라우팅하는 리스너를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6796-143">설명</span><span class="sxs-lookup"><span data-stu-id="d6796-143">Remarks</span></span>  
 <span data-ttu-id="d6796-144">.NET Framework와 함께 제공되는 수신기 클래스는 <xref:System.Diagnostics.TraceListener> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="d6796-145">추적 수신기의 특성을 `name` 지정하지 않으면 추적 <xref:System.Diagnostics.TraceListener.Name%2A> 수신기의 속성이 빈 문자열("")으로 기본설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="d6796-146">응용 프로그램에 수신기가 하나만 있는 경우 이름을 지정하지 않고 추가할 수 있으며 이름에 대한 빈 문자열을 지정하여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="d6796-147">그러나 응용 프로그램에 두 개 이상의 수신기가 있는 경우 각 추적 수신기에 대해 고유한 이름을 지정해야 하므로 <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> 컬렉션에서 개별 추적 리스너를 식별하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6796-148">동일한 형식의 추적 수신기를 두 개 이상 추가하고 이름이 같은 경우 해당 형식과 이름의 추적 `Listeners` 수신기가 하나만 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="d6796-149">그러나 프로그래밍 방식으로 컬렉션에 동일한 여러 `Listeners` 수신기를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="d6796-150">특성의 `initializeData` 값은 만드는 수신기의 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="d6796-151">모든 추적 리스너가 `initializeData`을 지정해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6796-152">특성을 `initializeData` 사용하면 컴파일러 경고 "initializeData" 특성이 선언되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="d6796-153">이 경고는 구성 설정이 특성을 인식하지 <xref:System.Diagnostics.TraceListener>못하는 추상 기본 `initializeData` 클래스에 대해 유효성을 검사하기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="d6796-154">일반적으로 매개 변수를 취하는 생성자가 있는 추적 수신기 구현에 대해 이 경고를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="d6796-155">다음 표에서는 .NET Framework에 포함된 추적 수신기를 보여 주며 `initializeData` 해당 특성의 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="d6796-156">추적 리스너 클래스</span><span class="sxs-lookup"><span data-stu-id="d6796-156">Trace listener class</span></span>|<span data-ttu-id="d6796-157">initializeData 특성 값</span><span class="sxs-lookup"><span data-stu-id="d6796-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d6796-158">생성자의 `useErrorStream` 값입니다. <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="d6796-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="d6796-159">추적 `initializeData` 및 디버그 출력을 표준 오류 스트림에 쓰기 위해 ""`true`특성을 설정합니다. 을`false`"로 설정하여 표준 출력 스트림에 쓰도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d6796-160"><xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d6796-161">기존 이벤트 로그 소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d6796-162"><xref:System.Diagnostics.EventSchemaTraceListener> 기록하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d6796-163"><xref:System.Diagnostics.TextWriterTraceListener> 기록하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d6796-164"><xref:System.Diagnostics.XmlWriterTraceListener> 기록하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="d6796-165">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d6796-165">Configuration File</span></span>  
 <span data-ttu-id="d6796-166">이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6796-167">예제</span><span class="sxs-lookup"><span data-stu-id="d6796-167">Example</span></span>  
 <span data-ttu-id="d6796-168">다음 예제에서는 요소를 `<add>` 사용하여 `console` 리스너를 `textListener` 추가하고 추적 `Listeners` 소스에 `TraceSourceApp`대한 컬렉션을 추가하는 방법을 보여 주어집니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="d6796-169">수신기는 `textListener` myListener.log 파일에 추적 출력을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="d6796-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"
        type="System.Diagnostics.TextWriterTraceListener"
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="d6796-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6796-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="d6796-171">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d6796-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d6796-172">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="d6796-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
