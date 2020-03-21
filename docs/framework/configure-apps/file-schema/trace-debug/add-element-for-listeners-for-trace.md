---
title: <add>에 <listeners> 대 한 요소<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153674"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="2ff26-102">\<추적> \<대한> \<청취자에 대한> 요소 추가</span><span class="sxs-lookup"><span data-stu-id="2ff26-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="2ff26-103">리스너 컬렉션에 수신기를 **추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="2ff26-103">Adds a listener to the **Listeners** collection.</span></span>  

<span data-ttu-id="2ff26-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ff26-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2ff26-105">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ff26-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="2ff26-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ff26-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="2ff26-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<청취자>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="2ff26-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="2ff26-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**</span><span class="sxs-lookup"><span data-stu-id="2ff26-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2ff26-109">구문</span><span class="sxs-lookup"><span data-stu-id="2ff26-109">Syntax</span></span>  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ff26-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2ff26-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2ff26-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ff26-112">특성</span><span class="sxs-lookup"><span data-stu-id="2ff26-112">Attributes</span></span>  
  
|<span data-ttu-id="2ff26-113">attribute</span><span class="sxs-lookup"><span data-stu-id="2ff26-113">Attribute</span></span>|<span data-ttu-id="2ff26-114">Description</span><span class="sxs-lookup"><span data-stu-id="2ff26-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ff26-115">**종류**</span><span class="sxs-lookup"><span data-stu-id="2ff26-115">**type**</span></span>|<span data-ttu-id="2ff26-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="2ff26-117">수신기의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-117">Specifies the type of the listener.</span></span> <span data-ttu-id="2ff26-118">[정규화된 형식 이름 지정에](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)지정된 요구 사항을 충족하는 문자열을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="2ff26-119">**초기화데이터**</span><span class="sxs-lookup"><span data-stu-id="2ff26-119">**initializeData**</span></span>|<span data-ttu-id="2ff26-120">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2ff26-121">문자열은 지정된 클래스의 생성자에게 전달되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="2ff26-122">**(이름)**</span><span class="sxs-lookup"><span data-stu-id="2ff26-122">**name**</span></span>|<span data-ttu-id="2ff26-123">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2ff26-124">수신기의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ff26-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2ff26-125">Child Elements</span></span>  
  
|<span data-ttu-id="2ff26-126">요소</span><span class="sxs-lookup"><span data-stu-id="2ff26-126">Element</span></span>|<span data-ttu-id="2ff26-127">Description</span><span class="sxs-lookup"><span data-stu-id="2ff26-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ff26-128">\<필터></span><span class="sxs-lookup"><span data-stu-id="2ff26-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="2ff26-129">추적에 대한 컬렉션의 `Listeners` 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ff26-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2ff26-130">Parent Elements</span></span>  
  
|<span data-ttu-id="2ff26-131">요소</span><span class="sxs-lookup"><span data-stu-id="2ff26-131">Element</span></span>|<span data-ttu-id="2ff26-132">Description</span><span class="sxs-lookup"><span data-stu-id="2ff26-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2ff26-133">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="2ff26-134">메시지를 수집, 저장 및 라우팅하는 수신기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="2ff26-135">리스너들은 추적 출력을 적절한 대상으로 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2ff26-136">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="2ff26-137">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ff26-138">설명</span><span class="sxs-lookup"><span data-stu-id="2ff26-138">Remarks</span></span>  
 <span data-ttu-id="2ff26-139">및 <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> 클래스는 동일한 리스너 컬렉션을 **공유합니다.**</span><span class="sxs-lookup"><span data-stu-id="2ff26-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="2ff26-140">이러한 클래스 중 하나에서 컬렉션에 수신기 개체를 추가하면 다른 클래스는 동일한 수신기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="2ff26-141">수신기 클래스는 에서 <xref:System.Diagnostics.TraceListener>파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="2ff26-142">추적 수신기의 특성을 `name` 지정하지 않으면 추적 <xref:System.Diagnostics.TraceListener.Name%2A> 수신기의 기본값이 빈 문자열("")으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="2ff26-143">응용 프로그램에 수신기가 하나만 있는 경우 이름을 지정하지 않고 추가하고 이름에 대한 빈 문자열을 지정하여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="2ff26-144">그러나 응용 프로그램에 두 개 이상의 수신기가 있는 경우 각 추적 수신기에 대해 고유한 이름을 지정해야 <xref:System.Diagnostics.Debug.Listeners%2A> 하며, 이를 통해 컬렉션 내의 <xref:System.Diagnostics.Trace.Listeners%2A> 개별 추적 리스너를 식별하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ff26-145">동일한 형식의 추적 수신기를 두 개 이상 추가하고 이름이 같은 경우 해당 형식과 이름의 추적 `Listeners` 수신기가 하나만 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="2ff26-146">그러나 프로그래밍 방식으로 컬렉션에 동일한 여러 `Listeners` 수신기를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="2ff26-147">**initializeData** 특성의 값은 만드는 수신기의 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="2ff26-148">모든 추적 리스너가 **initializeData**를 지정해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ff26-149">특성을 `initializeData` 사용하면 컴파일러 경고 "initializeData" 특성이 선언되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="2ff26-150">이 경고는 구성 설정이 특성을 인식하지 <xref:System.Diagnostics.TraceListener>못하는 추상 기본 `initializeData` 클래스에 대해 유효성을 검사하기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="2ff26-151">일반적으로 매개 변수를 취하는 생성자가 있는 추적 수신기 구현에 대해 이 경고를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="2ff26-152">다음 표에서는 .NET Framework에 포함된 추적 리스너와 **initializeData** 특성의 값을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="2ff26-153">추적 리스너 클래스</span><span class="sxs-lookup"><span data-stu-id="2ff26-153">Trace listener class</span></span>|<span data-ttu-id="2ff26-154">initializeData 특성 값</span><span class="sxs-lookup"><span data-stu-id="2ff26-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2ff26-155">생성자의 `useErrorStream` 값입니다. <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="2ff26-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="2ff26-156">추적 `initializeData` 및 디버그 출력을 작성하려면 " <xref:System.Console.Error%2A?displayProperty=nameWithType>특성을 "로`true`설정합니다. "`false`" 에 <xref:System.Console.Out%2A?displayProperty=nameWithType>쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2ff26-157"><xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2ff26-158">기존 이벤트 로그 원본의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2ff26-159"><xref:System.Diagnostics.EventSchemaTraceListener> 기록하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2ff26-160"><xref:System.Diagnostics.TextWriterTraceListener> 기록하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="2ff26-161"><xref:System.Diagnostics.XmlWriterTraceListener> 기록하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2ff26-162">예제</span><span class="sxs-lookup"><span data-stu-id="2ff26-162">Example</span></span>  
 <span data-ttu-id="2ff26-163">다음 예제에서는>\*\* \<추가\*\* 요소를 사용하여 리스너와 `MyListener` `MyEventListener` **리스너** 컬렉션을 추가하는 방법을 보여 주어집니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="2ff26-164">`MyListener`이라는 `MyListener.log` 파일을 만들고 출력을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="2ff26-165">`MyEventListener`이벤트 로그에 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2ff26-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ff26-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ff26-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="2ff26-167">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2ff26-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2ff26-168">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="2ff26-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
