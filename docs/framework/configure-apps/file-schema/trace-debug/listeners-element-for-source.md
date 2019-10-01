---
title: <source>에 대한 <listeners> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: d7641611e5d8257b49bc6a6abd0a2fadfde66e91
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697296"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="972fa-102">\<source >에 대 한 \<listeners > 요소</span><span class="sxs-lookup"><span data-stu-id="972fa-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="972fa-103">@No__t-1에 대 한 <xref:System.Diagnostics.TraceSource.Listeners%2A> 컬렉션에서 수신기를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="972fa-104">수신기는 추적 출력을 로그, 창 또는 텍스트 파일과 같은 적절 한 대상으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="972fa-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="972fa-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="972fa-106">&nbsp; @ no__t[ **\< >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="972fa-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="972fa-107">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="972fa-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="972fa-108">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="972fa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="972fa-109">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\< 수신기 >**</span><span class="sxs-lookup"><span data-stu-id="972fa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="972fa-110">구문</span><span class="sxs-lookup"><span data-stu-id="972fa-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="972fa-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="972fa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="972fa-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="972fa-113">특성</span><span class="sxs-lookup"><span data-stu-id="972fa-113">Attributes</span></span>  
 <span data-ttu-id="972fa-114">없음</span><span class="sxs-lookup"><span data-stu-id="972fa-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="972fa-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="972fa-115">Child Elements</span></span>  
  
|<span data-ttu-id="972fa-116">요소</span><span class="sxs-lookup"><span data-stu-id="972fa-116">Element</span></span>|<span data-ttu-id="972fa-117">설명</span><span class="sxs-lookup"><span data-stu-id="972fa-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="972fa-118">\<add></span><span class="sxs-lookup"><span data-stu-id="972fa-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="972fa-119">`Listeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="972fa-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="972fa-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="972fa-121">@No__t-0 컬렉션에서 수신기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="972fa-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="972fa-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="972fa-123">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="972fa-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="972fa-124">Parent Elements</span></span>  
  
|<span data-ttu-id="972fa-125">요소</span><span class="sxs-lookup"><span data-stu-id="972fa-125">Element</span></span>|<span data-ttu-id="972fa-126">설명</span><span class="sxs-lookup"><span data-stu-id="972fa-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="972fa-127">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="972fa-128">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="972fa-129">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="972fa-130">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="972fa-131">설명</span><span class="sxs-lookup"><span data-stu-id="972fa-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="972fa-132">구성 파일</span><span class="sxs-lookup"><span data-stu-id="972fa-132">Configuration File</span></span>  
 <span data-ttu-id="972fa-133">이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="972fa-134">예제</span><span class="sxs-lookup"><span data-stu-id="972fa-134">Example</span></span>  
 <span data-ttu-id="972fa-135">다음 예제에서는 `<listeners>` 요소를 사용 하 여 콘솔 추적 수신기를 `mySource` 소스에 추가 하 고 기본 추적 수신기를 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="972fa-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="972fa-136">참조</span><span class="sxs-lookup"><span data-stu-id="972fa-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="972fa-137">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="972fa-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="972fa-138">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="972fa-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
