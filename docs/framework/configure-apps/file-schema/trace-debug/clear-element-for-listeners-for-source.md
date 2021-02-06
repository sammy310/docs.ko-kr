---
description: '자세히 알아보기: <clear> 의에 대 한 요소 <listeners><source>'
title: <clear>의에 대 한 요소 <listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 731c23c73b6d149bd37672e91eca1d70431b2789
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639707"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="de9c3-103">\<clear>의에 대 한 요소 \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="de9c3-103">\<clear> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="de9c3-104">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="de9c3-104">Clears the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="de9c3-105">구문</span><span class="sxs-lookup"><span data-stu-id="de9c3-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de9c3-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="de9c3-106">Attributes and Elements</span></span>  

 <span data-ttu-id="de9c3-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de9c3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de9c3-108">특성</span><span class="sxs-lookup"><span data-stu-id="de9c3-108">Attributes</span></span>  

 <span data-ttu-id="de9c3-109">없음</span><span class="sxs-lookup"><span data-stu-id="de9c3-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="de9c3-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="de9c3-110">Child Elements</span></span>  

 <span data-ttu-id="de9c3-111">없음</span><span class="sxs-lookup"><span data-stu-id="de9c3-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de9c3-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="de9c3-112">Parent Elements</span></span>  
  
|<span data-ttu-id="de9c3-113">요소</span><span class="sxs-lookup"><span data-stu-id="de9c3-113">Element</span></span>|<span data-ttu-id="de9c3-114">설명</span><span class="sxs-lookup"><span data-stu-id="de9c3-114">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="de9c3-115">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="de9c3-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="de9c3-116">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de9c3-116">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="de9c3-117">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9c3-117">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="de9c3-118">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de9c3-118">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="de9c3-119">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="de9c3-119">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de9c3-120">설명</span><span class="sxs-lookup"><span data-stu-id="de9c3-120">Remarks</span></span>  

 <span data-ttu-id="de9c3-121">`<clear>`요소는 `Listeners` 를 포함 하 여 추적 소스에 대 한 컬렉션에서 모든 수신기를 제거 <xref:System.Diagnostics.DefaultTraceListener> 합니다.</span><span class="sxs-lookup"><span data-stu-id="de9c3-121">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="de9c3-122">요소를 사용 하기 전에 요소를 사용 하 여 `<clear>` `<add>` 컬렉션에 다른 활성 수신기가 없음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9c3-122">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="de9c3-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="de9c3-123">Configuration File</span></span>  

 <span data-ttu-id="de9c3-124">이 요소는 컴퓨터 구성 파일 (Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de9c3-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de9c3-125">예제</span><span class="sxs-lookup"><span data-stu-id="de9c3-125">Example</span></span>  

 <span data-ttu-id="de9c3-126">다음 예제에서는 `<clear>` 요소를 사용 하 여 `<add>` 수신기 및를 `console` `textListener` `Listeners` 추적 소스에 대 한 컬렉션에 추가 하기 전에 요소를 사용 하는 방법을 보여 줍니다 `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="de9c3-126">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="de9c3-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de9c3-127">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="de9c3-128">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="de9c3-128">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="de9c3-129">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="de9c3-129">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
