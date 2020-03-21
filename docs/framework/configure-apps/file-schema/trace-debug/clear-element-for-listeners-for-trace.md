---
title: <clear>에 <listeners> 대 한 요소<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153544"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="42071-102">\<추적> \<> 청취자를 위한 \<지우기> 요소</span><span class="sxs-lookup"><span data-stu-id="42071-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="42071-103">추적의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="42071-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="42071-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="42071-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="42071-105">&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="42071-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="42071-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="42071-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="42071-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<청취자>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="42071-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="42071-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<클리어>**</span><span class="sxs-lookup"><span data-stu-id="42071-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="42071-109">구문</span><span class="sxs-lookup"><span data-stu-id="42071-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42071-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="42071-110">Attributes and Elements</span></span>  
 <span data-ttu-id="42071-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42071-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42071-112">특성</span><span class="sxs-lookup"><span data-stu-id="42071-112">Attributes</span></span>  
 <span data-ttu-id="42071-113">없음</span><span class="sxs-lookup"><span data-stu-id="42071-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="42071-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="42071-114">Child Elements</span></span>  
 <span data-ttu-id="42071-115">없음</span><span class="sxs-lookup"><span data-stu-id="42071-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42071-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="42071-116">Parent Elements</span></span>  
  
|<span data-ttu-id="42071-117">요소</span><span class="sxs-lookup"><span data-stu-id="42071-117">Element</span></span>|<span data-ttu-id="42071-118">Description</span><span class="sxs-lookup"><span data-stu-id="42071-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="42071-119">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="42071-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="42071-120">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="42071-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="42071-121">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42071-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="42071-122">메시지를 수집, 저장 및 라우팅하는 리스너가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42071-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="42071-123">리스너들은 추적 출력을 적절한 대상으로 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="42071-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42071-124">설명</span><span class="sxs-lookup"><span data-stu-id="42071-124">Remarks</span></span>  
 <span data-ttu-id="42071-125">요소는 `<clear>` 추적에 대 한 `Listeners` 컬렉션에서 모든 수신기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="42071-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="42071-126">요소를 사용하기 `<clear>` 전에 요소를 사용하여 컬렉션에 다른 활성 수신기가 없는지 확인할 수 있습니다. `<add>`</span><span class="sxs-lookup"><span data-stu-id="42071-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="42071-127"><xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> 속성 ()에서`System.Diagnostics.Trace.Listeners.Clear()`메서드를 `Listeners` <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> 호출하여 프로그래밍 방식으로 컬렉션을 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42071-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="42071-128">이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42071-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42071-129">`<clear>` 요소는 <xref:System.Diagnostics.DefaultTraceListener> `Listeners` 컬렉션에서 를 제거하여 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>의 <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 동작을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="42071-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="42071-130">또는 `Fail` `Assert` 메서드를 호출하면 일반적으로 메시지 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="42071-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="42071-131">그러나 컬렉션에 없는 경우 메시지 <xref:System.Diagnostics.DefaultTraceListener> 상자가 `Listeners` 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42071-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42071-132">예제</span><span class="sxs-lookup"><span data-stu-id="42071-132">Example</span></span>  
 <span data-ttu-id="42071-133">다음 `<clear>` 예제에서는 `<add>` 추적을 위해 `console` `Listeners` 컬렉션에 수신기를 추가하기 위해 요소를 사용하기 전에 요소를 사용하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42071-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="42071-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42071-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="42071-135">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="42071-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="42071-136">\<>제거</span><span class="sxs-lookup"><span data-stu-id="42071-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="42071-137">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="42071-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
