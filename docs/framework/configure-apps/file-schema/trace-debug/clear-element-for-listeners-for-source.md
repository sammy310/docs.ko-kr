---
title: <source>에 대 한 <listeners>에 대 한 <clear> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 05c20040ef59f4dee6b15bbe0b0369281b532754
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697178"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="e7933-102">\< 수신기 >에 대 한 \<clear > 요소 \<source ></span><span class="sxs-lookup"><span data-stu-id="e7933-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="e7933-103">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="e7933-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e7933-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e7933-105">&nbsp; @ no__t[ **\< >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="e7933-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="e7933-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="e7933-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="e7933-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="e7933-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="e7933-108">&nbsp; @ no__t @ no__t @ no__t @ @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0 수신기 >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="e7933-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="e7933-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="e7933-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7933-110">구문</span><span class="sxs-lookup"><span data-stu-id="e7933-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7933-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e7933-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e7933-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7933-113">특성</span><span class="sxs-lookup"><span data-stu-id="e7933-113">Attributes</span></span>  
 <span data-ttu-id="e7933-114">없음</span><span class="sxs-lookup"><span data-stu-id="e7933-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e7933-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e7933-115">Child Elements</span></span>  
 <span data-ttu-id="e7933-116">없음</span><span class="sxs-lookup"><span data-stu-id="e7933-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7933-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e7933-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e7933-118">요소</span><span class="sxs-lookup"><span data-stu-id="e7933-118">Element</span></span>|<span data-ttu-id="e7933-119">설명</span><span class="sxs-lookup"><span data-stu-id="e7933-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e7933-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e7933-121">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="e7933-122">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="e7933-123">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="e7933-124">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7933-125">설명</span><span class="sxs-lookup"><span data-stu-id="e7933-125">Remarks</span></span>  
 <span data-ttu-id="e7933-126">@No__t-0 요소는 <xref:System.Diagnostics.DefaultTraceListener>를 포함 하 여 추적 소스에 대 한 `Listeners` 컬렉션에서 모든 수신기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="e7933-127">@No__t-1 요소를 사용 하기 전에 `<clear>` 요소를 사용 하 여 컬렉션에 다른 활성 수신기가 없음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="e7933-128">구성 파일</span><span class="sxs-lookup"><span data-stu-id="e7933-128">Configuration File</span></span>  
 <span data-ttu-id="e7933-129">이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7933-130">예제</span><span class="sxs-lookup"><span data-stu-id="e7933-130">Example</span></span>  
 <span data-ttu-id="e7933-131">다음 예제에서는 `<add>` 요소를 사용 하 여 `<clear>` 요소를 사용 하는 방법을 보여 줍니다.-1 요소를 사용 하 여 추적 소스 `TraceSourceApp`에 대 한 `Listeners` 컬렉션에 수신기 `console` 및 `textListener`을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7933-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
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
  
## <a name="see-also"></a><span data-ttu-id="e7933-132">참조</span><span class="sxs-lookup"><span data-stu-id="e7933-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="e7933-133">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e7933-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e7933-134">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="e7933-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
