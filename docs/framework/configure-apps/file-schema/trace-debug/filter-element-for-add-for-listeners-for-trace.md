---
title: <filter>에 <add> 대 <listeners> 한 요소<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153468"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="f9141-102">\<추적> \<> 동안 \<청취자에 \<대한> 추가하기 위해> 요소를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="f9141-103">추적에 대한 컬렉션의 `Listeners` 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

<span data-ttu-id="f9141-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f9141-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f9141-105">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="f9141-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="f9141-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="f9141-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="f9141-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<청취자>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="f9141-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="f9141-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>추가**](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="f9141-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>\
<span data-ttu-id="f9141-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<필터>**</span><span class="sxs-lookup"><span data-stu-id="f9141-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f9141-110">구문</span><span class="sxs-lookup"><span data-stu-id="f9141-110">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9141-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f9141-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f9141-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9141-113">특성</span><span class="sxs-lookup"><span data-stu-id="f9141-113">Attributes</span></span>  
  
|<span data-ttu-id="f9141-114">attribute</span><span class="sxs-lookup"><span data-stu-id="f9141-114">Attribute</span></span>|<span data-ttu-id="f9141-115">Description</span><span class="sxs-lookup"><span data-stu-id="f9141-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="f9141-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="f9141-117">클래스에서 상속해야 하는 필터 유형을 지정합니다. <xref:System.Diagnostics.TraceFilter></span><span class="sxs-lookup"><span data-stu-id="f9141-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="f9141-118">형식의 <xref:System.Type.FullName%2A> 속성에 해당하는 형식의 네임스페이스 정규화된 이름을 사용하거나 <xref:System.Type.AssemblyQualifiedName%2A> 속성에 해당하는 어셈블리 정보를 포함하여 정규화된 형식 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="f9141-119">정규화된 형식 이름에 대한 자세한 내용은 [정규화된 형식 이름 지정을](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9141-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="f9141-120">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f9141-121">지정된 필터 클래스의 생성자에게 전달된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9141-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f9141-122">Child Elements</span></span>  
 <span data-ttu-id="f9141-123">없음</span><span class="sxs-lookup"><span data-stu-id="f9141-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9141-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f9141-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f9141-125">요소</span><span class="sxs-lookup"><span data-stu-id="f9141-125">Element</span></span>|<span data-ttu-id="f9141-126">Description</span><span class="sxs-lookup"><span data-stu-id="f9141-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f9141-127">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f9141-128">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="f9141-129">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="f9141-130">메시지를 수집, 저장 및 라우팅하는 리스너가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="f9141-131">리스너들은 추적 출력을 적절한 대상으로 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="f9141-132">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9141-133">설명</span><span class="sxs-lookup"><span data-stu-id="f9141-133">Remarks</span></span>  
 <span data-ttu-id="f9141-134">`<filter>` 요소는 `<add>` [ \<공유리스 ](sharedlisteners-element.md)>정의된 수신기의 이름뿐만 아니라 수신기의 형식을 지정하는 추적 수신기의 요소에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="f9141-135">수신기가 [ \<공유리스>](sharedlisteners-element.md)정의된 경우 해당 수신기에 대한 필터가 해당 요소에 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="f9141-136">이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9141-137">예제</span><span class="sxs-lookup"><span data-stu-id="f9141-137">Example</span></span>  
 <span data-ttu-id="f9141-138">다음 예제에서는 추적을 `<filter>` 위해 `console` `Listeners` 컬렉션의 리스너에 필터를 추가하고 필터 이벤트 수준을 로 `Error`지정하는 요소를 사용하여 필터를 추가하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9141-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9141-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9141-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="f9141-140">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f9141-140">Trace and Debug Settings Schema</span></span>](index.md)
