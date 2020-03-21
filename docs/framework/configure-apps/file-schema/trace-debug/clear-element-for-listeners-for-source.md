---
title: <clear>에 <listeners> 대 한 요소<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153583"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="0ecd4-102">\<소스> \<대한 청취자 \<> 대한 명확한> 요소</span><span class="sxs-lookup"><span data-stu-id="0ecd4-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="0ecd4-103">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd4-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="0ecd4-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0ecd4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0ecd4-105">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="0ecd4-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="0ecd4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="0ecd4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="0ecd4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="0ecd4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="0ecd4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<청취자>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="0ecd4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="0ecd4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<클리어>**</span><span class="sxs-lookup"><span data-stu-id="0ecd4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0ecd4-110">구문</span><span class="sxs-lookup"><span data-stu-id="0ecd4-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ecd4-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0ecd4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0ecd4-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ecd4-113">특성</span><span class="sxs-lookup"><span data-stu-id="0ecd4-113">Attributes</span></span>  
 <span data-ttu-id="0ecd4-114">없음</span><span class="sxs-lookup"><span data-stu-id="0ecd4-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0ecd4-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0ecd4-115">Child Elements</span></span>  
 <span data-ttu-id="0ecd4-116">없음</span><span class="sxs-lookup"><span data-stu-id="0ecd4-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ecd4-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0ecd4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0ecd4-118">요소</span><span class="sxs-lookup"><span data-stu-id="0ecd4-118">Element</span></span>|<span data-ttu-id="0ecd4-119">Description</span><span class="sxs-lookup"><span data-stu-id="0ecd4-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0ecd4-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd4-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0ecd4-121">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd4-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="0ecd4-122">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd4-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="0ecd4-123">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd4-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="0ecd4-124">메시지를 수집, 저장 및 라우팅하는 리스너를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd4-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ecd4-125">설명</span><span class="sxs-lookup"><span data-stu-id="0ecd4-125">Remarks</span></span>  
 <span data-ttu-id="0ecd4-126">요소는 `<clear>` <xref:System.Diagnostics.DefaultTraceListener>을 포함하여 추적 `Listeners` 소스에 대한 컬렉션의 모든 수신기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd4-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="0ecd4-127">요소를 사용하기 `<clear>` 전에 요소를 사용하여 컬렉션에 다른 활성 수신기가 없는지 확인할 수 있습니다. `<add>`</span><span class="sxs-lookup"><span data-stu-id="0ecd4-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="0ecd4-128">구성 파일</span><span class="sxs-lookup"><span data-stu-id="0ecd4-128">Configuration File</span></span>  
 <span data-ttu-id="0ecd4-129">이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd4-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ecd4-130">예제</span><span class="sxs-lookup"><span data-stu-id="0ecd4-130">Example</span></span>  
 <span data-ttu-id="0ecd4-131">다음 예제에서는 `<clear>` `<add>` 요소를 사용하여 리스너를 `console` `textListener` 추가하고 추적 소스에 `Listeners` `TraceSourceApp`대한 컬렉션에 요소를 사용하는 방법을 보여 주어집니다.</span><span class="sxs-lookup"><span data-stu-id="0ecd4-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0ecd4-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ecd4-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="0ecd4-133">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="0ecd4-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0ecd4-134">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="0ecd4-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
