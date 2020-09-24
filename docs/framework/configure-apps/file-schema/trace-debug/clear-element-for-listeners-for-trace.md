---
title: <clear>의에 대 한 요소 <listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 2d301d588e33b0eea4164a6bf62dedd7b0c450ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149272"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="07932-102">\<clear>의에 대 한 요소 \<listeners>\<trace></span><span class="sxs-lookup"><span data-stu-id="07932-102">\<clear> Element for \<listeners> for \<trace></span></span>

<span data-ttu-id="07932-103">추적의 `Listeners` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="07932-103">Clears the `Listeners` collection for trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="07932-104">구문</span><span class="sxs-lookup"><span data-stu-id="07932-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07932-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="07932-105">Attributes and Elements</span></span>  

 <span data-ttu-id="07932-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07932-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07932-107">특성</span><span class="sxs-lookup"><span data-stu-id="07932-107">Attributes</span></span>  

 <span data-ttu-id="07932-108">없음</span><span class="sxs-lookup"><span data-stu-id="07932-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07932-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="07932-109">Child Elements</span></span>  

 <span data-ttu-id="07932-110">없음</span><span class="sxs-lookup"><span data-stu-id="07932-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07932-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="07932-111">Parent Elements</span></span>  
  
|<span data-ttu-id="07932-112">요소</span><span class="sxs-lookup"><span data-stu-id="07932-112">Element</span></span>|<span data-ttu-id="07932-113">설명</span><span class="sxs-lookup"><span data-stu-id="07932-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="07932-114">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="07932-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="07932-115">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="07932-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="07932-116">추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07932-116">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="07932-117">메시지를 수집, 저장 및 라우팅하는 수신기를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="07932-117">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="07932-118">수신기는 추적 출력을 적절 한 대상으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="07932-118">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07932-119">설명</span><span class="sxs-lookup"><span data-stu-id="07932-119">Remarks</span></span>  

 <span data-ttu-id="07932-120">`<clear>`요소는 `Listeners` 추적을 위해 컬렉션에서 모든 수신기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="07932-120">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="07932-121">요소를 사용 하기 전에 요소를 사용 하 여 `<clear>` `<add>` 컬렉션에 다른 활성 수신기가 없음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07932-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="07932-122">`Listeners` <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> 속성 ()에서 메서드를 호출 하 여 프로그래밍 방식으로 컬렉션을 지울 수 있습니다 <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> `System.Diagnostics.Trace.Listeners.Clear()` .</span><span class="sxs-lookup"><span data-stu-id="07932-122">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="07932-123">이 요소는 컴퓨터 구성 파일 (Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07932-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07932-124">`<clear>`요소는 <xref:System.Diagnostics.DefaultTraceListener> 컬렉션에서을 제거 `Listeners` 하 여,, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> 및 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 메서드의 동작을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="07932-124">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="07932-125">`Assert`또는 메서드를 호출 `Fail` 하면 일반적으로 메시지 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07932-125">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="07932-126">그러나가 컬렉션에 없으면 메시지 상자가 표시 되지 않습니다 <xref:System.Diagnostics.DefaultTraceListener> `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="07932-126">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07932-127">예제</span><span class="sxs-lookup"><span data-stu-id="07932-127">Example</span></span>  

 <span data-ttu-id="07932-128">다음 예제에서는 요소를 사용 하 여 `<clear>` `<add>` `console` 추적을 위한 컬렉션에 수신기를 추가 하기 전에 요소를 사용 하는 방법을 보여 줍니다 `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="07932-128">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07932-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07932-129">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="07932-130">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="07932-130">Trace and Debug Settings Schema</span></span>](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="07932-131">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="07932-131">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
