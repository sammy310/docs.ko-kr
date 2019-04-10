---
title: <add> 요소에 대 한 <listeners> 에 대 한 <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 4d2952e29b09fcf9f81624317e30caf301a61a51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165487"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="4ed6c-102">\<추가 > 요소에 대 한 \<수신기 >에 대 한 \<소스 ></span><span class="sxs-lookup"><span data-stu-id="4ed6c-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="4ed6c-103">추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="4ed6c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4ed6c-104">\<configuration></span></span>  
<span data-ttu-id="4ed6c-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="4ed6c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="4ed6c-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="4ed6c-106">\<sources></span></span>  
<span data-ttu-id="4ed6c-107">\<source></span><span class="sxs-lookup"><span data-stu-id="4ed6c-107">\<source></span></span>  
<span data-ttu-id="4ed6c-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="4ed6c-108">\<listeners></span></span>  
<span data-ttu-id="4ed6c-109">\<add></span><span class="sxs-lookup"><span data-stu-id="4ed6c-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ed6c-110">구문</span><span class="sxs-lookup"><span data-stu-id="4ed6c-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ed6c-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4ed6c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4ed6c-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ed6c-113">특성</span><span class="sxs-lookup"><span data-stu-id="4ed6c-113">Attributes</span></span>  
  
|<span data-ttu-id="4ed6c-114">특성</span><span class="sxs-lookup"><span data-stu-id="4ed6c-114">Attribute</span></span>|<span data-ttu-id="4ed6c-115">설명</span><span class="sxs-lookup"><span data-stu-id="4ed6c-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="4ed6c-116">필수 특성에서 수신기를 참조 하는 하지 않는 경우는 `sharedListeners` 컬렉션에 있는 경우 이름으로 참조 하는 데만 필요 (참조를 [예제](#example)).</span><span class="sxs-lookup"><span data-stu-id="4ed6c-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="4ed6c-117">수신기의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-117">Specifies the type of the listener.</span></span> <span data-ttu-id="4ed6c-118">에 지정 된 요구 사항을 충족 하는 문자열을 사용 해야 합니다 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="4ed6c-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4ed6c-120">지정된 된 클래스에 대 한 생성자에 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="4ed6c-121"><xref:System.Configuration.ConfigurationException> 클래스에는 문자열을 사용 하는 생성자가 없는 경우 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="4ed6c-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4ed6c-123">수신기의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="4ed6c-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4ed6c-125">지정 된 <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> 추적 수신기에 대 한 속성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="4ed6c-126">[사용자 지정 특성]</span><span class="sxs-lookup"><span data-stu-id="4ed6c-126">[custom attributes]</span></span>|<span data-ttu-id="4ed6c-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="4ed6c-128">으로 식별 된 수신기 별 특성의 값을 지정 합니다 <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> 수신기 메서드.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> <span data-ttu-id="4ed6c-129">추가 특성의 예로 고유는 <xref:System.Diagnostics.DelimitedListTraceListener> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-129">is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ed6c-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4ed6c-130">Child Elements</span></span>  
  
|<span data-ttu-id="4ed6c-131">요소</span><span class="sxs-lookup"><span data-stu-id="4ed6c-131">Element</span></span>|<span data-ttu-id="4ed6c-132">설명</span><span class="sxs-lookup"><span data-stu-id="4ed6c-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ed6c-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="4ed6c-133">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="4ed6c-134">추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4ed6c-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4ed6c-135">Parent Elements</span></span>  
  
|<span data-ttu-id="4ed6c-136">요소</span><span class="sxs-lookup"><span data-stu-id="4ed6c-136">Element</span></span>|<span data-ttu-id="4ed6c-137">설명</span><span class="sxs-lookup"><span data-stu-id="4ed6c-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4ed6c-138">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4ed6c-139">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="4ed6c-140">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="4ed6c-141">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="4ed6c-142">수집, 저장 하 고 메시지를 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ed6c-143">설명</span><span class="sxs-lookup"><span data-stu-id="4ed6c-143">Remarks</span></span>  
 <span data-ttu-id="4ed6c-144">.NET Framework와 함께 제공 되는 수신기 클래스에서 파생 된 <xref:System.Diagnostics.TraceListener> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="4ed6c-145">지정 하지 않는 경우는 `name` 추적 수신기의 특성을 <xref:System.Diagnostics.TraceListener.Name%2A> 의 추적 수신기는 속성의 기본값은 빈 문자열 ("").</span><span class="sxs-lookup"><span data-stu-id="4ed6c-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="4ed6c-146">하나의 수신기만이 응용 프로그램에 이름을 지정 하지 않고 추가할 수 있습니다 하 고 이름에 대 한 빈 문자열을 지정 하 여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="4ed6c-147">그러나 응용 프로그램에 둘 이상의 수신기를 식별 하 고 개별 추적 수신기에 관리할 수 있게 하는 각 추적 수신기에 대 한 고유한 이름을 지정 해야 합니다 <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ed6c-148">하나의 추적 수신기가 해당 형식의 결과 같은 동일한 유형의 추적 수신기를 여러 개 추가 이름과 이름에 추가 되는 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="4ed6c-149">그러나 동일한 여러 수신기를 프로그래밍 방식으로 추가할 수는 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="4ed6c-150">에 대 한 값을 `initializeData` 특성 만든 수신기의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="4ed6c-151">모든 추적 수신기에 지정 해야 `initializeData`합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ed6c-152">사용 하는 경우는 `initializeData` 특성인 컴파일러 "'initializeData' 특성이 선언 되지 않았습니다." 경고를 발생할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="4ed6c-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="4ed6c-153">이 경고는 추상 기본 클래스에 대 한 구성 설정이 검증 되었으며 때문에 발생 <xref:System.Diagnostics.TraceListener>를 인식 하지 않습니다는 `initializeData` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="4ed6c-154">일반적으로 매개 변수를 사용 하는 생성자가 하는 추적 수신기 구현에 대 한이 경고를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="4ed6c-155">다음 표는.NET Framework에 포함 된 추적 수신기를 보여 주고 값을 설명 합니다 해당 `initializeData` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="4ed6c-156">추적 수신기 클래스</span><span class="sxs-lookup"><span data-stu-id="4ed6c-156">Trace listener class</span></span>|<span data-ttu-id="4ed6c-157">initializeData 특성 값</span><span class="sxs-lookup"><span data-stu-id="4ed6c-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ed6c-158">합니다 `useErrorStream` 에 대 한 값을 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="4ed6c-159">설정 된 `initializeData` 특성을 "`true`"쓸 추적 및 디버그 출력을 표준 오류 스트림에;로 설정"`false`" 표준 출력 스트림에 쓸입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ed6c-160"><xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ed6c-161">기존 이벤트 로그 소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ed6c-162">파일의 이름을는 <xref:System.Diagnostics.EventSchemaTraceListener> 를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ed6c-163">파일의 이름을는 <xref:System.Diagnostics.TextWriterTraceListener> 를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="4ed6c-164">파일의 이름을는 <xref:System.Diagnostics.XmlWriterTraceListener> 를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="4ed6c-165">구성 파일</span><span class="sxs-lookup"><span data-stu-id="4ed6c-165">Configuration File</span></span>  
 <span data-ttu-id="4ed6c-166">이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ed6c-167">예제</span><span class="sxs-lookup"><span data-stu-id="4ed6c-167">Example</span></span>  
 <span data-ttu-id="4ed6c-168">다음 예제에서는 사용 하는 방법을 보여 줍니다 `<add>` 요소를 추가 하는 수신기 `console` 및 `textListener` 에 `Listeners` 추적 소스에 대 한 컬렉션 `TraceSourceApp`합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="4ed6c-169">`textListener` 수신기 파일 myListener.log에 추적 출력을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="4ed6c-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ed6c-170">참고자료</span><span class="sxs-lookup"><span data-stu-id="4ed6c-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="4ed6c-171">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4ed6c-171">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="4ed6c-172">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="4ed6c-172">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
