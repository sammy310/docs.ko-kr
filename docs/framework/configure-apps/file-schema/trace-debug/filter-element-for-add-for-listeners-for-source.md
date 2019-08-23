---
title: <filter>의에 <add> 대 <listeners> 한의 요소<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0d25d0b955a94986147922914068c8a1cf2d96c4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920528"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="93c63-102">\<소스 >에 \< \< 대\<한 수신기 >에 대 한 > 추가의 필터 > 요소</span><span class="sxs-lookup"><span data-stu-id="93c63-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="93c63-103">추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="93c63-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="93c63-104">\<configuration></span></span>  
<span data-ttu-id="93c63-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="93c63-105">\<system.diagnostics></span></span>  
<span data-ttu-id="93c63-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="93c63-106">\<sources></span></span>  
<span data-ttu-id="93c63-107">\<source></span><span class="sxs-lookup"><span data-stu-id="93c63-107">\<source></span></span>  
<span data-ttu-id="93c63-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="93c63-108">\<listeners></span></span>  
<span data-ttu-id="93c63-109">\<add></span><span class="sxs-lookup"><span data-stu-id="93c63-109">\<add></span></span>  
<span data-ttu-id="93c63-110">\<filter></span><span class="sxs-lookup"><span data-stu-id="93c63-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93c63-111">구문</span><span class="sxs-lookup"><span data-stu-id="93c63-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93c63-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="93c63-112">Attributes and Elements</span></span>  
 <span data-ttu-id="93c63-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93c63-114">특성</span><span class="sxs-lookup"><span data-stu-id="93c63-114">Attributes</span></span>  
  
|<span data-ttu-id="93c63-115">특성</span><span class="sxs-lookup"><span data-stu-id="93c63-115">Attribute</span></span>|<span data-ttu-id="93c63-116">설명</span><span class="sxs-lookup"><span data-stu-id="93c63-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="93c63-117">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="93c63-118"><xref:System.Diagnostics.TraceFilter> 클래스에서 상속 해야 하는 필터의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="93c63-119">형식의 네임 스페이스 정규화 된 이름을 사용 하거나, 형식의 <xref:System.Type.FullName%2A> 속성에 해당 하는 형식의 정규화 된 형식 이름을 사용 하거나, <xref:System.Type.AssemblyQualifiedName%2A> 속성에 해당 하는 어셈블리 정보를 포함 하 여 정규화 된 형식 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="93c63-120">정규화 된 형식 이름에 대 한 자세한 내용은 정규화 된 [형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93c63-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="93c63-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="93c63-122">지정 된 필터 클래스의 생성자에 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93c63-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="93c63-123">Child Elements</span></span>  
 <span data-ttu-id="93c63-124">없음</span><span class="sxs-lookup"><span data-stu-id="93c63-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93c63-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="93c63-125">Parent Elements</span></span>  
  
|<span data-ttu-id="93c63-126">요소</span><span class="sxs-lookup"><span data-stu-id="93c63-126">Element</span></span>|<span data-ttu-id="93c63-127">설명</span><span class="sxs-lookup"><span data-stu-id="93c63-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="93c63-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="93c63-129">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="93c63-130">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="93c63-131">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="93c63-132">메시지를 수집, 저장 및 라우팅하는 수신기를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="93c63-133">수신기는 추적 출력을 적절 한 대상으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="93c63-134">추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93c63-135">설명</span><span class="sxs-lookup"><span data-stu-id="93c63-135">Remarks</span></span>  
 <span data-ttu-id="93c63-136">요소 `<filter>` 는 `<add>` [sharedlisteners >에 정의 된 수신기의 이름 뿐만 아니라 수신기의 형식을 지정 하는 추적 소스 수신기의 요소에 \<](sharedlisteners-element.md)포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="93c63-137">[ \<> Sharedlisteners](sharedlisteners-element.md)에 정의 되어 있는 경우 해당 수신기의 필터를 해당 요소에 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="93c63-138">이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93c63-139">예제</span><span class="sxs-lookup"><span data-stu-id="93c63-139">Example</span></span>  
 <span data-ttu-id="93c63-140">`<filter>` 다음 예제에서는 요소를 사용 하 여 추적 소스 `myTraceSource`에 대 한 `Listeners` 컬렉션의 수신기 `console` 에 필터를 추가 하 고 필터 이벤트 수준을로 `Error`지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93c63-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="93c63-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="93c63-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="93c63-142">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="93c63-142">Trace and Debug Settings Schema</span></span>](index.md)
