---
description: '자세히 알아보기: <add> 의에 대 한 요소 <listeners><trace>'
title: <add>의에 대 한 요소 <listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: ffc0823e0c0ce1dcd9d9f19853929496b3248177
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639785"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="c6953-103">\<add>의에 대 한 요소 \<listeners>\<trace></span><span class="sxs-lookup"><span data-stu-id="c6953-103">\<add> Element for \<listeners> for \<trace></span></span>

<span data-ttu-id="c6953-104">**수신기 컬렉션에** 수신기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-104">Adds a listener to the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="c6953-105">구문</span><span class="sxs-lookup"><span data-stu-id="c6953-105">Syntax</span></span>  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6953-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c6953-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c6953-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6953-108">특성</span><span class="sxs-lookup"><span data-stu-id="c6953-108">Attributes</span></span>  
  
|<span data-ttu-id="c6953-109">attribute</span><span class="sxs-lookup"><span data-stu-id="c6953-109">Attribute</span></span>|<span data-ttu-id="c6953-110">Description</span><span class="sxs-lookup"><span data-stu-id="c6953-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6953-111">**type**</span><span class="sxs-lookup"><span data-stu-id="c6953-111">**type**</span></span>|<span data-ttu-id="c6953-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="c6953-113">수신기의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-113">Specifies the type of the listener.</span></span> <span data-ttu-id="c6953-114">정규화 된 [형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)에 지정 된 요구 사항을 충족 하는 문자열을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-114">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="c6953-115">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="c6953-115">**initializeData**</span></span>|<span data-ttu-id="c6953-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c6953-117">지정 된 클래스의 생성자에 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-117">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="c6953-118">**name**</span><span class="sxs-lookup"><span data-stu-id="c6953-118">**name**</span></span>|<span data-ttu-id="c6953-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c6953-120">수신기의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-120">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6953-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c6953-121">Child Elements</span></span>  
  
|<span data-ttu-id="c6953-122">요소</span><span class="sxs-lookup"><span data-stu-id="c6953-122">Element</span></span>|<span data-ttu-id="c6953-123">설명</span><span class="sxs-lookup"><span data-stu-id="c6953-123">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="c6953-124">추적의 컬렉션에 있는 수신기에 필터를 추가 `Listeners` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-124">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6953-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c6953-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c6953-126">요소</span><span class="sxs-lookup"><span data-stu-id="c6953-126">Element</span></span>|<span data-ttu-id="c6953-127">설명</span><span class="sxs-lookup"><span data-stu-id="c6953-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c6953-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="c6953-129">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-129">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="c6953-130">수신기는 추적 출력을 적절 한 대상으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-130">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c6953-131">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-131">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="c6953-132">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-132">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6953-133">설명</span><span class="sxs-lookup"><span data-stu-id="c6953-133">Remarks</span></span>  

 <span data-ttu-id="c6953-134"><xref:System.Diagnostics.Debug>및 <xref:System.Diagnostics.Trace> 클래스는 동일한 **Listeners** 컬렉션을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-134">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="c6953-135">이러한 클래스 중 하나에서 컬렉션에 수신기 개체를 추가 하는 경우 다른 클래스는 동일한 수신기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-135">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="c6953-136">수신기 클래스는에서 파생 <xref:System.Diagnostics.TraceListener> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-136">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="c6953-137">추적 수신기의 특성을 지정 하지 않는 경우 `name` <xref:System.Diagnostics.TraceListener.Name%2A> 추적 수신기의은 기본적으로 빈 문자열 ("")로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-137">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="c6953-138">응용 프로그램에 수신기가 하나만 있는 경우 이름을 지정 하지 않고 수신기를 추가 하 고 이름에 대해 빈 문자열을 지정 하 여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-138">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="c6953-139">그러나 응용 프로그램에 둘 이상의 수신기가 있는 경우 각 추적 수신기에 고유한 이름을 지정 해야 하며,이를 통해 및 컬렉션 내에서 개별 추적 수신기를 식별 하 고 관리할 수 있습니다 <xref:System.Diagnostics.Debug.Listeners%2A> <xref:System.Diagnostics.Trace.Listeners%2A> .</span><span class="sxs-lookup"><span data-stu-id="c6953-139">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6953-140">동일한 형식의 추적 수신기를 두 개 이상 추가 하면 해당 형식 및 이름이 컬렉션에 추가 되는 하나의 추적 수신기만 생성 `Listeners` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-140">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="c6953-141">그러나 컬렉션에 여러 개의 동일한 수신기를 프로그래밍 방식으로 추가할 수 있습니다 `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="c6953-141">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="c6953-142">**Initializedata** 특성의 값은 사용자가 만드는 수신기의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-142">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="c6953-143">모든 추적 수신기에서 **Initializedata** 를 지정 해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-143">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6953-144">특성을 사용 하는 경우 `initializeData` 컴파일러 경고 "' initializeData ' 특성이 선언 되지 않았습니다." 라는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-144">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="c6953-145">이 경고는 특성을 인식 하지 않는 추상 기본 클래스에 대해 구성 설정의 유효성을 검사 하기 때문에 발생 합니다 <xref:System.Diagnostics.TraceListener> `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="c6953-145">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="c6953-146">일반적으로 매개 변수를 사용 하는 생성자가 있는 추적 수신기 구현에 대해서는이 경고를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-146">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="c6953-147">다음 표에서는 .NET Framework에 포함 된 추적 수신기를 보여 주고 해당 **Initializedata** 특성의 값을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-147">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="c6953-148">추적 수신기 클래스</span><span class="sxs-lookup"><span data-stu-id="c6953-148">Trace listener class</span></span>|<span data-ttu-id="c6953-149">initializeData 특성 값</span><span class="sxs-lookup"><span data-stu-id="c6953-149">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c6953-150">`useErrorStream`생성자에 대 한 값 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 입니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-150">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="c6953-151">`initializeData` `true` 추적 및 디버그 출력을 쓰려면 특성을 ""로 설정 합니다 <xref:System.Console.Error%2A?displayProperty=nameWithType> . `false`쓸 "" <xref:System.Console.Out%2A?displayProperty=nameWithType> 입니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-151">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c6953-152"><xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-152">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c6953-153">기존 이벤트 로그 원본의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-153">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c6953-154">에서 쓰는 파일의 이름입니다 <xref:System.Diagnostics.EventSchemaTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="c6953-154">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c6953-155">에서 쓰는 파일의 이름입니다 <xref:System.Diagnostics.TextWriterTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="c6953-155">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="c6953-156">에서 쓰는 파일의 이름입니다 <xref:System.Diagnostics.XmlWriterTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="c6953-156">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c6953-157">예제</span><span class="sxs-lookup"><span data-stu-id="c6953-157">Example</span></span>  

 <span data-ttu-id="c6953-158">다음 예제에서는 요소를 사용 하 여 수신기 **\<add>** `MyListener` 및 수신기 `MyEventListener` 컬렉션에 추가  하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-158">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="c6953-159">`MyListener` 이라는 파일을 만들고 `MyListener.log` 출력을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-159">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="c6953-160">`MyEventListener` 이벤트 로그에 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c6953-160">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c6953-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6953-161">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="c6953-162">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c6953-162">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c6953-163">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="c6953-163">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
