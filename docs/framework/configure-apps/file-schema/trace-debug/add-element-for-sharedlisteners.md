---
title: <sharedListeners>에 대한 <add> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153609"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="d893e-102">\<공유리스> \<> 요소 추가</span><span class="sxs-lookup"><span data-stu-id="d893e-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="d893e-103">`sharedListeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="d893e-104">`sharedListeners`은 [ \<>](source-element.md) [ \<추적>](trace-element.md) 참조할 수 있는 수신기 의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="d893e-105">기본적으로 컬렉션의 `sharedListeners` 리스너는 `Listeners` 컬렉션에 배치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="d893e-106">원본>이름으로 [ \<](source-element.md) [ \< ](trace-element.md)추가하거나>추적해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="d893e-107">런타임에 `sharedListeners` 코드에서 컬렉션의 리스너를 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

<span data-ttu-id="d893e-108">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d893e-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d893e-109">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="d893e-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="d893e-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<공유청취자>**](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="d893e-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="d893e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**</span><span class="sxs-lookup"><span data-stu-id="d893e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d893e-112">구문</span><span class="sxs-lookup"><span data-stu-id="d893e-112">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d893e-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d893e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d893e-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d893e-115">특성</span><span class="sxs-lookup"><span data-stu-id="d893e-115">Attributes</span></span>  
  
|<span data-ttu-id="d893e-116">attribute</span><span class="sxs-lookup"><span data-stu-id="d893e-116">Attribute</span></span>|<span data-ttu-id="d893e-117">Description</span><span class="sxs-lookup"><span data-stu-id="d893e-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d893e-118">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="d893e-119">공유 수신기를 `Listeners` 컬렉션에 추가하는 데 사용되는 수신기의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="d893e-120">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="d893e-121">수신기의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-121">Specifies the type of the listener.</span></span> <span data-ttu-id="d893e-122">[정규화된 형식 이름 지정에](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)지정된 요구 사항을 충족하는 문자열을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="d893e-123">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d893e-124">문자열은 지정된 클래스의 생성자에게 전달되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="d893e-125">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="d893e-126">추적 출력에 기록할 <xref:System.Diagnostics.TraceOptions> 데이터를 나타내는 하나 이상의 열거형 멤버의 문자열 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="d893e-127">여러 항목은 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="d893e-128">기본값은 "없음"입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d893e-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d893e-129">Child Elements</span></span>  
  
|<span data-ttu-id="d893e-130">요소</span><span class="sxs-lookup"><span data-stu-id="d893e-130">Element</span></span>|<span data-ttu-id="d893e-131">Description</span><span class="sxs-lookup"><span data-stu-id="d893e-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d893e-132">\<필터></span><span class="sxs-lookup"><span data-stu-id="d893e-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="d893e-133">`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d893e-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d893e-134">Parent Elements</span></span>  
  
|<span data-ttu-id="d893e-135">요소</span><span class="sxs-lookup"><span data-stu-id="d893e-135">Element</span></span>|<span data-ttu-id="d893e-136">Description</span><span class="sxs-lookup"><span data-stu-id="d893e-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d893e-137">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d893e-138">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="d893e-139">모든 소스 또는 추적 요소가 참조할 수 있는 리스너 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d893e-140">설명</span><span class="sxs-lookup"><span data-stu-id="d893e-140">Remarks</span></span>  
 <span data-ttu-id="d893e-141">.NET Framework와 함께 제공되는 수신기 클래스는 <xref:System.Diagnostics.TraceListener> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="d893e-142">특성의 `name` 값은 추적 또는 추적 원본에 `Listeners` 대한 컬렉션에 공유 리스터를 추가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="d893e-143">특성의 `initializeData` 값은 만드는 수신기의 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="d893e-144">모든 추적 리스너가 `initializeData`을 지정해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d893e-145">특성을 `initializeData` 사용하면 컴파일러 경고 "initializeData" 특성이 선언되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="d893e-146">이 경고는 구성 설정이 특성을 인식하지 <xref:System.Diagnostics.TraceListener>못하는 추상 기본 `initializeData` 클래스에 대해 유효성을 검사하기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="d893e-147">일반적으로 매개 변수를 취하는 생성자가 있는 추적 수신기 구현에 대해 이 경고를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="d893e-148">다음 표에서는 .NET Framework에 포함된 추적 수신기를 보여 주며 `initializeData` 해당 특성의 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="d893e-149">추적 리스너 클래스</span><span class="sxs-lookup"><span data-stu-id="d893e-149">Trace listener class</span></span>|<span data-ttu-id="d893e-150">initializeData 특성 값</span><span class="sxs-lookup"><span data-stu-id="d893e-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="d893e-151">생성자의 `useErrorStream` 값입니다. <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="d893e-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="d893e-152">추적 `initializeData` 및 디버그 출력을 표준 오류 스트림에 쓰기 위해 ""`true`특성을 설정합니다. 을`false`"로 설정하여 표준 출력 스트림에 쓰도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="d893e-153"><xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d893e-154">기존 이벤트 로그 소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d893e-155"><xref:System.Diagnostics.EventSchemaTraceListener> 기록하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d893e-156"><xref:System.Diagnostics.TextWriterTraceListener> 기록하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="d893e-157"><xref:System.Diagnostics.XmlWriterTraceListener> 기록하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="d893e-158">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d893e-158">Configuration File</span></span>  
 <span data-ttu-id="d893e-159">이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d893e-160">예제</span><span class="sxs-lookup"><span data-stu-id="d893e-160">Example</span></span>  
 <span data-ttu-id="d893e-161">다음 예제에서는 요소를 `<add>` 사용하여 컬렉션에 <xref:System.Diagnostics.TextWriterTraceListener> `textListener` 요소를 `sharedListeners` 추가하는 방법을 보여 주어집니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="d893e-162">`textListener`추적 소스에 `TraceSourceApp`대한 `Listeners` 이름으로 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="d893e-163">수신기는 `textListener` myListener.log 파일에 추적 출력을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="d893e-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d893e-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d893e-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="d893e-165">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d893e-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d893e-166">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="d893e-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
