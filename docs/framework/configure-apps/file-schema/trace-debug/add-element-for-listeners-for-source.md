---
title: <source>에 대 한 <listeners>에 대 한 <add> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 0818d7ec248b210f215759069b9f69a3e29637f5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699397"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="b57f8-102">\< @no__t-> 1listeners에 대 한 > 요소 추가 \<source ></span><span class="sxs-lookup"><span data-stu-id="b57f8-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="b57f8-103">추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="b57f8-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b57f8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b57f8-105">&nbsp; @ no__t[ **\< >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b57f8-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="b57f8-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="b57f8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="b57f8-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="b57f8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="b57f8-108">&nbsp; @ no__t @ no__t @ no__t @ @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0 수신기 >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="b57f8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="b57f8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="b57f8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b57f8-110">구문</span><span class="sxs-lookup"><span data-stu-id="b57f8-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b57f8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b57f8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b57f8-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b57f8-113">특성</span><span class="sxs-lookup"><span data-stu-id="b57f8-113">Attributes</span></span>  
  
|<span data-ttu-id="b57f8-114">특성</span><span class="sxs-lookup"><span data-stu-id="b57f8-114">Attribute</span></span>|<span data-ttu-id="b57f8-115">설명</span><span class="sxs-lookup"><span data-stu-id="b57f8-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="b57f8-116">@No__t-0 컬렉션에서 수신기를 참조 하는 경우를 제외 하 고는 필수 특성입니다 ( [예제](#example)참조).</span><span class="sxs-lookup"><span data-stu-id="b57f8-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="b57f8-117">수신기의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-117">Specifies the type of the listener.</span></span> <span data-ttu-id="b57f8-118">정규화 된 [형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)에 지정 된 요구 사항을 충족 하는 문자열을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="b57f8-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b57f8-120">지정 된 클래스의 생성자에 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="b57f8-121">클래스에 문자열을 사용 하는 생성자가 없으면 <xref:System.Configuration.ConfigurationException>이 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="b57f8-122">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b57f8-123">수신기의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="b57f8-124">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b57f8-125">추적 수신기의 <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> 속성 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="b57f8-126">[사용자 지정 특성]</span><span class="sxs-lookup"><span data-stu-id="b57f8-126">[custom attributes]</span></span>|<span data-ttu-id="b57f8-127">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="b57f8-128">수신기에 대 한 <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> 메서드로 식별 되는 수신기 별 특성의 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="b57f8-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>은 <xref:System.Diagnostics.DelimitedListTraceListener> 클래스에 고유한 추가 특성의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b57f8-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b57f8-130">Child Elements</span></span>  
  
|<span data-ttu-id="b57f8-131">요소</span><span class="sxs-lookup"><span data-stu-id="b57f8-131">Element</span></span>|<span data-ttu-id="b57f8-132">설명</span><span class="sxs-lookup"><span data-stu-id="b57f8-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b57f8-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="b57f8-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="b57f8-134">추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b57f8-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b57f8-135">Parent Elements</span></span>  
  
|<span data-ttu-id="b57f8-136">요소</span><span class="sxs-lookup"><span data-stu-id="b57f8-136">Element</span></span>|<span data-ttu-id="b57f8-137">설명</span><span class="sxs-lookup"><span data-stu-id="b57f8-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b57f8-138">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b57f8-139">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b57f8-140">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="b57f8-141">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b57f8-142">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b57f8-143">설명</span><span class="sxs-lookup"><span data-stu-id="b57f8-143">Remarks</span></span>  
 <span data-ttu-id="b57f8-144">.NET Framework와 함께 제공 되는 수신기 클래스는 <xref:System.Diagnostics.TraceListener> 클래스에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="b57f8-145">추적 수신기의 `name` 특성을 지정 하지 않은 경우 추적 수신기의 <xref:System.Diagnostics.TraceListener.Name%2A> 속성은 기본적으로 빈 문자열 ("")로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="b57f8-146">응용 프로그램에 수신기가 하나만 있는 경우 이름을 지정 하지 않고 수신기를 추가 하 고 이름에 대해 빈 문자열을 지정 하 여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="b57f8-147">그러나 응용 프로그램에 둘 이상의 수신기가 있는 경우 각 추적 수신기에 고유한 이름을 지정 하 여 <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> 컬렉션에서 개별 추적 수신기를 식별 하 고 관리할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b57f8-148">동일한 형식의 추적 수신기를 둘 이상 추가 하 고 이름이 동일한 경우 해당 형식 및 이름에 대 한 추적 수신기는 `Listeners` 컬렉션에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="b57f8-149">그러나 `Listeners` 컬렉션에 여러 개의 동일한 수신기를 프로그래밍 방식으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="b57f8-150">@No__t-0 특성의 값은 사용자가 만드는 수신기의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="b57f8-151">모든 추적 수신기에 `initializeData`을 지정 해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b57f8-152">@No__t-0 특성을 사용 하는 경우 컴파일러 경고 "' initializeData ' 특성이 선언 되지 않았습니다." 라는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="b57f8-153">이 경고는 `initializeData` 특성을 인식 하지 않는 추상 기본 클래스 <xref:System.Diagnostics.TraceListener>에 대해 구성 설정의 유효성을 검사 하기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="b57f8-154">일반적으로 매개 변수를 사용 하는 생성자가 있는 추적 수신기 구현에 대해서는이 경고를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="b57f8-155">다음 표에서는 .NET Framework에 포함 된 추적 수신기를 보여 주고 `initializeData` 특성의 값을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="b57f8-156">추적 수신기 클래스</span><span class="sxs-lookup"><span data-stu-id="b57f8-156">Trace listener class</span></span>|<span data-ttu-id="b57f8-157">initializeData 특성 값</span><span class="sxs-lookup"><span data-stu-id="b57f8-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="b57f8-158">@No__t-1 생성자의 @no__t 0 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="b57f8-159">@No__t-0 특성을 "`true`"로 설정 하 여 추적 및 디버그 출력을 표준 오류 스트림에 씁니다. 표준 출력 스트림에 쓰려면 "`false`"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="b57f8-160">파일의 이름을 합니다 <xref:System.Diagnostics.DelimitedListTraceListener> 를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="b57f8-161">기존 이벤트 로그 원본의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="b57f8-162">@No__t-0에서 쓸 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="b57f8-163">@No__t-0에서 쓸 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="b57f8-164">@No__t-0에서 쓸 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="b57f8-165">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b57f8-165">Configuration File</span></span>  
 <span data-ttu-id="b57f8-166">이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b57f8-167">예제</span><span class="sxs-lookup"><span data-stu-id="b57f8-167">Example</span></span>  
 <span data-ttu-id="b57f8-168">다음 예제에서는 `<add>` 요소를 사용 하 여 `console` 및 `textListener` 수신기를 추적 소스 `TraceSourceApp`의 @no__t 3 컬렉션에 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="b57f8-169">@No__t-0 수신기는 추적 출력을 myListener .log 파일에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b57f8-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b57f8-170">참조</span><span class="sxs-lookup"><span data-stu-id="b57f8-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="b57f8-171">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b57f8-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b57f8-172">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="b57f8-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
