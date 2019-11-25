---
title: <source>에 대 한 <listeners> <add> <filter> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 766088b8a26ce3218031df74b193658ba8024280
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088905"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="40c76-102">\<>에 대 한 \<수신기 >에 대 한 >를 추가 \<> 요소를 \<</span><span class="sxs-lookup"><span data-stu-id="40c76-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="40c76-103">추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="40c76-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="40c76-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="40c76-105">&nbsp;[ **\<&nbsp;진단 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="40c76-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="40c76-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**원본**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="40c76-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\</span></span>
<span data-ttu-id="40c76-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<원본 >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="40c76-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="40c76-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<수신기 >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="40c76-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="40c76-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**추가**](add-element-for-listeners-for-source.md) ></span><span class="sxs-lookup"><span data-stu-id="40c76-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)</span></span>\
<span data-ttu-id="40c76-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**필터 >**</span><span class="sxs-lookup"><span data-stu-id="40c76-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="40c76-111">구문</span><span class="sxs-lookup"><span data-stu-id="40c76-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40c76-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="40c76-112">Attributes and Elements</span></span>  
 <span data-ttu-id="40c76-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40c76-114">특성</span><span class="sxs-lookup"><span data-stu-id="40c76-114">Attributes</span></span>  
  
|<span data-ttu-id="40c76-115">특성</span><span class="sxs-lookup"><span data-stu-id="40c76-115">Attribute</span></span>|<span data-ttu-id="40c76-116">설명</span><span class="sxs-lookup"><span data-stu-id="40c76-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="40c76-117">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="40c76-118"><xref:System.Diagnostics.TraceFilter> 클래스에서 상속 해야 하는 필터의 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="40c76-119">형식의 <xref:System.Type.FullName%2A> 속성에 해당 하는 형식의 네임 스페이스로 한정 된 이름을 사용 하거나 <xref:System.Type.AssemblyQualifiedName%2A> 속성에 해당 하는 어셈블리 정보를 포함 하 여 정규화 된 형식 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="40c76-120">정규화 된 형식 이름에 대 한 자세한 내용은 정규화 된 [형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40c76-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="40c76-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="40c76-122">지정 된 필터 클래스의 생성자에 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40c76-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="40c76-123">Child Elements</span></span>  
 <span data-ttu-id="40c76-124">없음.</span><span class="sxs-lookup"><span data-stu-id="40c76-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40c76-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="40c76-125">Parent Elements</span></span>  
  
|<span data-ttu-id="40c76-126">요소</span><span class="sxs-lookup"><span data-stu-id="40c76-126">Element</span></span>|<span data-ttu-id="40c76-127">설명</span><span class="sxs-lookup"><span data-stu-id="40c76-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="40c76-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="40c76-129">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="40c76-130">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="40c76-131">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="40c76-132">메시지를 수집, 저장 및 라우팅하는 수신기를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="40c76-133">수신기는 추적 출력을 적절 한 대상으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="40c76-134">추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40c76-135">주의</span><span class="sxs-lookup"><span data-stu-id="40c76-135">Remarks</span></span>  
 <span data-ttu-id="40c76-136">`<filter>` 요소는 [\<sharedListeners >](sharedlisteners-element.md)에 정의 된 수신기의 이름 뿐만 아니라 수신기의 형식을 지정 하는 추적 소스 수신기의 `<add>` 요소에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="40c76-137">수신기가 [\<sharedListeners >](sharedlisteners-element.md)에 정의 되어 있는 경우 해당 수신기의 필터를 해당 요소에 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="40c76-138">이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40c76-139">예제</span><span class="sxs-lookup"><span data-stu-id="40c76-139">Example</span></span>  
 <span data-ttu-id="40c76-140">다음 예제에서는 `<filter>` 요소를 사용 하 여 추적 소스 `myTraceSource`에 대 한 `Listeners` 컬렉션의 `console` 수신기에 필터를 추가 하 고 필터 이벤트 수준을 `Error`로 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40c76-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="40c76-141">참조</span><span class="sxs-lookup"><span data-stu-id="40c76-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="40c76-142">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="40c76-142">Trace and Debug Settings Schema</span></span>](index.md)
