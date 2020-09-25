---
title: <filter>의에 <add> 대 한의 요소 <listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 2b83fd10da506202427aaeee454411822ff1ae5b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201683"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="1417d-102">\<filter>의에 \<add> 대 한의 요소 \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="1417d-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>

<span data-ttu-id="1417d-103">추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="1417d-104">구문</span><span class="sxs-lookup"><span data-stu-id="1417d-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1417d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1417d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1417d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1417d-107">특성</span><span class="sxs-lookup"><span data-stu-id="1417d-107">Attributes</span></span>  
  
|<span data-ttu-id="1417d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="1417d-108">Attribute</span></span>|<span data-ttu-id="1417d-109">설명</span><span class="sxs-lookup"><span data-stu-id="1417d-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="1417d-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="1417d-111">클래스에서 상속 해야 하는 필터의 유형을 지정 합니다 <xref:System.Diagnostics.TraceFilter> .</span><span class="sxs-lookup"><span data-stu-id="1417d-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="1417d-112">형식의 네임 스페이스 정규화 된 이름을 사용 하거나, 형식의 속성에 해당 하는 형식의 정규화 된 <xref:System.Type.FullName%2A> 형식 이름을 사용 하거나, 속성에 해당 하는 어셈블리 정보를 포함 하 여 정규화 된 형식 이름을 사용할 수 있습니다 <xref:System.Type.AssemblyQualifiedName%2A> .</span><span class="sxs-lookup"><span data-stu-id="1417d-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="1417d-113">정규화 된 형식 이름에 대 한 자세한 내용은 정규화 된 [형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1417d-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="1417d-114">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1417d-115">지정 된 필터 클래스의 생성자에 전달 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1417d-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1417d-116">Child Elements</span></span>  

 <span data-ttu-id="1417d-117">없음</span><span class="sxs-lookup"><span data-stu-id="1417d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1417d-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1417d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1417d-119">요소</span><span class="sxs-lookup"><span data-stu-id="1417d-119">Element</span></span>|<span data-ttu-id="1417d-120">설명</span><span class="sxs-lookup"><span data-stu-id="1417d-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1417d-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1417d-122">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="1417d-123">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-123">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="1417d-124">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-124">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="1417d-125">메시지를 수집, 저장 및 라우팅하는 수신기를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-125">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="1417d-126">수신기는 추적 출력을 적절 한 대상으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-126">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="1417d-127">추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-127">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1417d-128">설명</span><span class="sxs-lookup"><span data-stu-id="1417d-128">Remarks</span></span>  

 <span data-ttu-id="1417d-129">`<filter>`요소는 `<add>` 에 정의 된 수신기의 이름 뿐만 아니라 수신기의 형식을 지정 하는 추적 소스 수신기의 요소에 포함 되어야 합니다 [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="1417d-129">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="1417d-130">수신기가에 정의 된 경우 해당 [\<sharedListeners>](sharedlisteners-element.md) 수신기의 필터를 해당 요소에 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-130">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="1417d-131">이 요소는 컴퓨터 구성 파일 (Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1417d-132">예제</span><span class="sxs-lookup"><span data-stu-id="1417d-132">Example</span></span>  

 <span data-ttu-id="1417d-133">다음 예제에서는 요소를 사용 하 여 `<filter>` `console` 추적 소스에 대 한 컬렉션의 수신기에 필터를 추가 하 `Listeners` `myTraceSource` 고 필터 이벤트 수준을로 지정 `Error` 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1417d-133">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1417d-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1417d-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="1417d-135">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="1417d-135">Trace and Debug Settings Schema</span></span>](index.md)
