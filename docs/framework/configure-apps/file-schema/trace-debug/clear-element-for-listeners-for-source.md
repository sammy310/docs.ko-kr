---
title: <clear> 요소에 대 한 <listeners> 에 대 한 <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 63d3bb272fcdbee2c59b0569c85f8183cdac8666
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158355"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="66e46-102">\<지우기 > 요소에 대 한 \<수신기 >에 대 한 \<소스 ></span><span class="sxs-lookup"><span data-stu-id="66e46-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="66e46-103">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="66e46-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="66e46-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="66e46-104">\<configuration></span></span>  
<span data-ttu-id="66e46-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="66e46-105">\<system.diagnostics></span></span>  
<span data-ttu-id="66e46-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="66e46-106">\<sources></span></span>  
<span data-ttu-id="66e46-107">\<source></span><span class="sxs-lookup"><span data-stu-id="66e46-107">\<source></span></span>  
<span data-ttu-id="66e46-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="66e46-108">\<listeners></span></span>  
<span data-ttu-id="66e46-109">\<clear></span><span class="sxs-lookup"><span data-stu-id="66e46-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66e46-110">구문</span><span class="sxs-lookup"><span data-stu-id="66e46-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66e46-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="66e46-111">Attributes and Elements</span></span>  
 <span data-ttu-id="66e46-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66e46-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66e46-113">특성</span><span class="sxs-lookup"><span data-stu-id="66e46-113">Attributes</span></span>  
 <span data-ttu-id="66e46-114">없음</span><span class="sxs-lookup"><span data-stu-id="66e46-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="66e46-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="66e46-115">Child Elements</span></span>  
 <span data-ttu-id="66e46-116">없음</span><span class="sxs-lookup"><span data-stu-id="66e46-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66e46-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="66e46-117">Parent Elements</span></span>  
  
|<span data-ttu-id="66e46-118">요소</span><span class="sxs-lookup"><span data-stu-id="66e46-118">Element</span></span>|<span data-ttu-id="66e46-119">설명</span><span class="sxs-lookup"><span data-stu-id="66e46-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="66e46-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="66e46-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="66e46-121">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66e46-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="66e46-122">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e46-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="66e46-123">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66e46-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="66e46-124">수집, 저장 하 고 메시지를 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e46-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66e46-125">설명</span><span class="sxs-lookup"><span data-stu-id="66e46-125">Remarks</span></span>  
 <span data-ttu-id="66e46-126">`<clear>` 요소에서 모든 수신기를 제거 합니다 `Listeners` 추적 원본에 대 한 컬렉션 포함 하 여는 <xref:System.Diagnostics.DefaultTraceListener>합니다.</span><span class="sxs-lookup"><span data-stu-id="66e46-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="66e46-127">사용할 수 있습니다를 `<clear>` 요소를 사용 하기 전에 `<add>` 요소 컬렉션에 다른 활성 수신기 수입니다.</span><span class="sxs-lookup"><span data-stu-id="66e46-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="66e46-128">구성 파일</span><span class="sxs-lookup"><span data-stu-id="66e46-128">Configuration File</span></span>  
 <span data-ttu-id="66e46-129">이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e46-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66e46-130">예제</span><span class="sxs-lookup"><span data-stu-id="66e46-130">Example</span></span>  
 <span data-ttu-id="66e46-131">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<clear>` 요소를 사용 하기 전에 `<add>` 수신기를 추가할 요소입니다 `console` 및 `textListener` 에 `Listeners` 추적 소스에 대 한 컬렉션 `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="66e46-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66e46-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="66e46-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="66e46-133">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="66e46-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="66e46-134">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="66e46-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
