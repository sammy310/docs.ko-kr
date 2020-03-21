---
title: <remove>에 <listeners> 대 한 요소<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153337"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="ce2de-102">\<소스> \<대한> \<청취자에 대한> 요소를 제거</span><span class="sxs-lookup"><span data-stu-id="ce2de-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="ce2de-103">추적 소스의 `Listeners` 컬렉션에서 수신기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="ce2de-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce2de-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ce2de-105">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce2de-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="ce2de-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce2de-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="ce2de-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce2de-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="ce2de-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<청취자>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="ce2de-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="ce2de-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>제거**</span><span class="sxs-lookup"><span data-stu-id="ce2de-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ce2de-110">구문</span><span class="sxs-lookup"><span data-stu-id="ce2de-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce2de-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ce2de-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ce2de-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce2de-113">특성</span><span class="sxs-lookup"><span data-stu-id="ce2de-113">Attributes</span></span>  
  
|<span data-ttu-id="ce2de-114">attribute</span><span class="sxs-lookup"><span data-stu-id="ce2de-114">Attribute</span></span>|<span data-ttu-id="ce2de-115">Description</span><span class="sxs-lookup"><span data-stu-id="ce2de-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ce2de-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="ce2de-117">컬렉션에서 제거할 수신기의 이름입니다. `Listeners`</span><span class="sxs-lookup"><span data-stu-id="ce2de-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce2de-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ce2de-118">Child Elements</span></span>  
 <span data-ttu-id="ce2de-119">없음</span><span class="sxs-lookup"><span data-stu-id="ce2de-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce2de-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ce2de-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ce2de-121">요소</span><span class="sxs-lookup"><span data-stu-id="ce2de-121">Element</span></span>|<span data-ttu-id="ce2de-122">Description</span><span class="sxs-lookup"><span data-stu-id="ce2de-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ce2de-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ce2de-124">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="ce2de-125">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="ce2de-126">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="ce2de-127">메시지를 수집, 저장 및 라우팅하는 리스너를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce2de-128">설명</span><span class="sxs-lookup"><span data-stu-id="ce2de-128">Remarks</span></span>  
 <span data-ttu-id="ce2de-129">요소는 `<remove>` 추적 소스에 대 한 `Listeners` 컬렉션에서 지정 된 수신기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="ce2de-130">인스턴스의 `Listeners` <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> <xref:System.Diagnostics.TraceSource.Listeners%2A> 속성에 메서드를 호출 하여 프로그래밍 방식으로 추적 원본에 대 한 컬렉션에서 요소를 제거할 수 있습니다. <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="ce2de-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="ce2de-131">이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce2de-132">예제</span><span class="sxs-lookup"><span data-stu-id="ce2de-132">Example</span></span>  
 <span data-ttu-id="ce2de-133">다음 `<remove>` 예제에서는 `<add>` 요소를 사용하여 추적 소스에 `console` `Listeners` `TraceSourceApp`대한 컬렉션에 수신기를 추가하기 전에 요소를 사용하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2de-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="ce2de-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce2de-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="ce2de-135">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ce2de-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ce2de-136">\<클리어></span><span class="sxs-lookup"><span data-stu-id="ce2de-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="ce2de-137">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="ce2de-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
