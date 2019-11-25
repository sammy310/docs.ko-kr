---
title: <source>의 <listeners>에 대 한 <clear> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 4567f236397435e89371ca4c80730ff964fddd21
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088928"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="e9c88-102">\<소스에 대 한 \<수신기 >에 대해 clear > 요소를 \<</span><span class="sxs-lookup"><span data-stu-id="e9c88-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="e9c88-103">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="e9c88-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9c88-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9c88-105">&nbsp;[ **\<&nbsp;진단 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9c88-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="e9c88-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**원본**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="e9c88-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\</span></span>
<span data-ttu-id="e9c88-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<원본 >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9c88-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="e9c88-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<수신기 >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="e9c88-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="e9c88-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**clear >**</span><span class="sxs-lookup"><span data-stu-id="e9c88-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e9c88-110">구문</span><span class="sxs-lookup"><span data-stu-id="e9c88-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9c88-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e9c88-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e9c88-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9c88-113">특성</span><span class="sxs-lookup"><span data-stu-id="e9c88-113">Attributes</span></span>  
 <span data-ttu-id="e9c88-114">없음.</span><span class="sxs-lookup"><span data-stu-id="e9c88-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9c88-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e9c88-115">Child Elements</span></span>  
 <span data-ttu-id="e9c88-116">없음.</span><span class="sxs-lookup"><span data-stu-id="e9c88-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9c88-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e9c88-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e9c88-118">요소</span><span class="sxs-lookup"><span data-stu-id="e9c88-118">Element</span></span>|<span data-ttu-id="e9c88-119">설명</span><span class="sxs-lookup"><span data-stu-id="e9c88-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e9c88-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e9c88-121">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="e9c88-122">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="e9c88-123">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="e9c88-124">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9c88-125">주의</span><span class="sxs-lookup"><span data-stu-id="e9c88-125">Remarks</span></span>  
 <span data-ttu-id="e9c88-126">`<clear>` 요소는 <xref:System.Diagnostics.DefaultTraceListener>를 포함 하 여 추적 소스에 대 한 `Listeners` 컬렉션에서 모든 수신기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="e9c88-127">`<add>` 요소를 사용 하기 전에 `<clear>` 요소를 사용 하 여 컬렉션에 다른 활성 수신기가 없음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="e9c88-128">구성 파일</span><span class="sxs-lookup"><span data-stu-id="e9c88-128">Configuration File</span></span>  
 <span data-ttu-id="e9c88-129">이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9c88-130">예제</span><span class="sxs-lookup"><span data-stu-id="e9c88-130">Example</span></span>  
 <span data-ttu-id="e9c88-131">다음 예제에서는 `<add>` 요소를 사용 하 여 수신기 `console`를 추가 하 고 추적 소스 `Listeners`에 대 한 `TraceSourceApp`컬렉션에 `textListener`를 추가 하기 전에 `<clear>` 요소를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9c88-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9c88-132">참조</span><span class="sxs-lookup"><span data-stu-id="e9c88-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="e9c88-133">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e9c88-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e9c88-134">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="e9c88-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
