---
title: <clear>의에 대 한 요소 <listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153583"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="b3983-102">\<clear>의에 대 한 요소 \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="b3983-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="b3983-103">추적 소스의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="b3983-103">Clears the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="b3983-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3983-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3983-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b3983-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b3983-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b3983-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3983-107">특성</span><span class="sxs-lookup"><span data-stu-id="b3983-107">Attributes</span></span>  
 <span data-ttu-id="b3983-108">없음</span><span class="sxs-lookup"><span data-stu-id="b3983-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b3983-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b3983-109">Child Elements</span></span>  
 <span data-ttu-id="b3983-110">없음</span><span class="sxs-lookup"><span data-stu-id="b3983-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3983-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b3983-111">Parent Elements</span></span>  
  
|<span data-ttu-id="b3983-112">요소</span><span class="sxs-lookup"><span data-stu-id="b3983-112">Element</span></span>|<span data-ttu-id="b3983-113">Description</span><span class="sxs-lookup"><span data-stu-id="b3983-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b3983-114">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b3983-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b3983-115">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3983-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b3983-116">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3983-116">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="b3983-117">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3983-117">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b3983-118">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3983-118">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3983-119">설명</span><span class="sxs-lookup"><span data-stu-id="b3983-119">Remarks</span></span>  
 <span data-ttu-id="b3983-120">`<clear>`요소는 `Listeners` 를 포함 하 여 추적 소스에 대 한 컬렉션에서 모든 수신기를 제거 <xref:System.Diagnostics.DefaultTraceListener> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3983-120">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="b3983-121">요소를 사용 하기 전에 요소를 사용 하 여 `<clear>` `<add>` 컬렉션에 다른 활성 수신기가 없음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3983-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="b3983-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b3983-122">Configuration File</span></span>  
 <span data-ttu-id="b3983-123">이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3983-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3983-124">예제</span><span class="sxs-lookup"><span data-stu-id="b3983-124">Example</span></span>  
 <span data-ttu-id="b3983-125">다음 예제에서는 `<clear>` 요소를 사용 하 여 `<add>` 수신기 및를 `console` `textListener` `Listeners` 추적 소스에 대 한 컬렉션에 추가 하기 전에 요소를 사용 하는 방법을 보여 줍니다 `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="b3983-125">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b3983-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3983-126">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="b3983-127">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b3983-127">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b3983-128">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="b3983-128">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
