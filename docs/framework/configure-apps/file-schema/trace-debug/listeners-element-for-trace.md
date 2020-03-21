---
title: <trace>에 대한 <listeners> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: fd12be1b775d7611ef3f16d23147470313bf9866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153375"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="da95b-102">\<추적> \<위해 요소를> 리스너</span><span class="sxs-lookup"><span data-stu-id="da95b-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="da95b-103">메시지를 수집, 저장 및 라우팅하는 수신기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="da95b-104">리스너들은 추적 출력을 적절한 대상으로 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-104">Listeners direct the tracing output to an appropriate target.</span></span>  

<span data-ttu-id="da95b-105">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="da95b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="da95b-106">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="da95b-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="da95b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="da95b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="da95b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<청취자>**</span><span class="sxs-lookup"><span data-stu-id="da95b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>

## <a name="syntax"></a><span data-ttu-id="da95b-109">구문</span><span class="sxs-lookup"><span data-stu-id="da95b-109">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da95b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="da95b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="da95b-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da95b-112">특성</span><span class="sxs-lookup"><span data-stu-id="da95b-112">Attributes</span></span>  
 <span data-ttu-id="da95b-113">없음</span><span class="sxs-lookup"><span data-stu-id="da95b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="da95b-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="da95b-114">Child Elements</span></span>  
  
|<span data-ttu-id="da95b-115">요소</span><span class="sxs-lookup"><span data-stu-id="da95b-115">Element</span></span>|<span data-ttu-id="da95b-116">Description</span><span class="sxs-lookup"><span data-stu-id="da95b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da95b-117">\<>추가</span><span class="sxs-lookup"><span data-stu-id="da95b-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="da95b-118">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="da95b-119">\<클리어></span><span class="sxs-lookup"><span data-stu-id="da95b-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="da95b-120">추적의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="da95b-121">\<>제거</span><span class="sxs-lookup"><span data-stu-id="da95b-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="da95b-122">컬렉션에서 수신기를 제거합니다. `Listeners`</span><span class="sxs-lookup"><span data-stu-id="da95b-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da95b-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="da95b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="da95b-124">요소</span><span class="sxs-lookup"><span data-stu-id="da95b-124">Element</span></span>|<span data-ttu-id="da95b-125">Description</span><span class="sxs-lookup"><span data-stu-id="da95b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="da95b-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="da95b-127">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="da95b-128">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da95b-129">설명</span><span class="sxs-lookup"><span data-stu-id="da95b-129">Remarks</span></span>  
 <span data-ttu-id="da95b-130">및 <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> 클래스는 동일한 리스너 컬렉션을 **공유합니다.**</span><span class="sxs-lookup"><span data-stu-id="da95b-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="da95b-131">이러한 클래스 중 하나에서 컬렉션에 수신기 개체를 추가하면 다른 클래스는 동일한 수신기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="da95b-132">.NET Framework와 함께 제공되는 수신기 클래스는 <xref:System.Diagnostics.TraceListener> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="da95b-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="da95b-133">Configuration File</span></span>  
 <span data-ttu-id="da95b-134">이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da95b-135">예제</span><span class="sxs-lookup"><span data-stu-id="da95b-135">Example</span></span>  
 <span data-ttu-id="da95b-136">다음 예제에서는 \*\* \<리스너를\*\*>요소를 사용하여 `MyListener` 리스를 `MyEventListener` 추가하고 **리스너** 컬렉션에 추가하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="da95b-137">`MyListener`이라는 `MyListener.log` 파일을 만들고 출력을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="da95b-138">`MyEventListener`이벤트 로그에 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da95b-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"
          type="System.Diagnostics.TextWriterTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="da95b-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da95b-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="da95b-140">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="da95b-140">Trace and Debug Settings Schema</span></span>](index.md)
