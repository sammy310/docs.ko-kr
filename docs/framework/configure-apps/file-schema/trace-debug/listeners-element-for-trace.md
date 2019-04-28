---
title: <trace>에 대한 <listeners> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: f9f12d9e61e2472b897169727bbb4fbf9833efd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701348"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="8f033-102">\<수신기 > 요소에 대 한 \<추적 ></span><span class="sxs-lookup"><span data-stu-id="8f033-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="8f033-103">저장소를 수집 하는 수신기를 지정 하 고 메시지를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="8f033-104">수신기는 추적 출력을 적절 한 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="8f033-105">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="8f033-105">\<configuration> Element</span></span>  
<span data-ttu-id="8f033-106">\<system.diagnostics> Element</span><span class="sxs-lookup"><span data-stu-id="8f033-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="8f033-107">\<추적 > 요소</span><span class="sxs-lookup"><span data-stu-id="8f033-107">\<trace> Element</span></span>  
<span data-ttu-id="8f033-108">\<수신기 > 요소에 대 한 \<추적 ></span><span class="sxs-lookup"><span data-stu-id="8f033-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f033-109">구문</span><span class="sxs-lookup"><span data-stu-id="8f033-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f033-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8f033-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8f033-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f033-112">특성</span><span class="sxs-lookup"><span data-stu-id="8f033-112">Attributes</span></span>  
 <span data-ttu-id="8f033-113">없음</span><span class="sxs-lookup"><span data-stu-id="8f033-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8f033-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8f033-114">Child Elements</span></span>  
  
|<span data-ttu-id="8f033-115">요소</span><span class="sxs-lookup"><span data-stu-id="8f033-115">Element</span></span>|<span data-ttu-id="8f033-116">설명</span><span class="sxs-lookup"><span data-stu-id="8f033-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f033-117">\<add></span><span class="sxs-lookup"><span data-stu-id="8f033-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="8f033-118">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="8f033-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="8f033-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="8f033-120">추적의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="8f033-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="8f033-121">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="8f033-122">수신기를 제거 합니다 `Listeners` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8f033-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8f033-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8f033-124">요소</span><span class="sxs-lookup"><span data-stu-id="8f033-124">Element</span></span>|<span data-ttu-id="8f033-125">설명</span><span class="sxs-lookup"><span data-stu-id="8f033-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8f033-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8f033-127">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="8f033-128">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f033-129">설명</span><span class="sxs-lookup"><span data-stu-id="8f033-129">Remarks</span></span>  
 <span data-ttu-id="8f033-130">합니다 <xref:System.Diagnostics.Debug> 하 고 <xref:System.Diagnostics.Trace> 클래스에 동일한 공유 **수신기** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="8f033-131">이러한 클래스 중 하나에서 컬렉션에 수신기 개체를 추가 하는 경우 다른 클래스는 같은 수신기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="8f033-132">.NET Framework와 함께 제공 되는 수신기 클래스에서 파생 된 <xref:System.Diagnostics.TraceListener> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="8f033-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="8f033-133">Configuration File</span></span>  
 <span data-ttu-id="8f033-134">이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f033-135">예제</span><span class="sxs-lookup"><span data-stu-id="8f033-135">Example</span></span>  
 <span data-ttu-id="8f033-136">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다  **\<수신기 >** 수신기에 추가할 요소 `MyListener` 및 `MyEventListener` 에 **수신기** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="8f033-137">`MyListener` 라는 파일을 만들고 `MyListener.log` 출력 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="8f033-138">`MyEventListener` 이벤트 로그에 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8f033-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8f033-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="8f033-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="8f033-140">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8f033-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
