---
title: <trace>에 대 한 <listeners>에 대 한 <remove> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 56d1e56514aed98d5f3b9f7363e461af6ac68a8c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697214"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="7b989-102">\< \< 수신기 >에 대 한 > 요소 제거 \<trace ></span><span class="sxs-lookup"><span data-stu-id="7b989-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="7b989-103">**수신기 컬렉션에서** 수신기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-103">Removes a listener from the **Listeners** collection.</span></span>  
  
[<span data-ttu-id="7b989-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="7b989-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="7b989-105">&nbsp; @ no__t[ **\< >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b989-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="7b989-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b989-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="7b989-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="7b989-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="7b989-108">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="7b989-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b989-109">구문</span><span class="sxs-lookup"><span data-stu-id="7b989-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b989-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7b989-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7b989-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b989-112">특성</span><span class="sxs-lookup"><span data-stu-id="7b989-112">Attributes</span></span>  
  
|<span data-ttu-id="7b989-113">특성</span><span class="sxs-lookup"><span data-stu-id="7b989-113">Attribute</span></span>|<span data-ttu-id="7b989-114">설명</span><span class="sxs-lookup"><span data-stu-id="7b989-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b989-115">**name**</span><span class="sxs-lookup"><span data-stu-id="7b989-115">**name**</span></span>|<span data-ttu-id="7b989-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="7b989-117">**Listeners** 컬렉션에서 제거할 수신기의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b989-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7b989-118">Child Elements</span></span>  
 <span data-ttu-id="7b989-119">없음</span><span class="sxs-lookup"><span data-stu-id="7b989-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b989-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7b989-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7b989-121">요소</span><span class="sxs-lookup"><span data-stu-id="7b989-121">Element</span></span>|<span data-ttu-id="7b989-122">설명</span><span class="sxs-lookup"><span data-stu-id="7b989-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7b989-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="7b989-124">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="7b989-125">수신기는 추적 출력을 적절 한 대상으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="7b989-126">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="7b989-127">ASP.NET 추적 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b989-128">설명</span><span class="sxs-lookup"><span data-stu-id="7b989-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b989-129">@No__t-1 컬렉션에서 <xref:System.Diagnostics.DefaultTraceListener>을 제거 하면 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> 및 @no__t 방법의 동작이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="7b989-130">@No__t-0 또는 `Fail` 메서드를 호출 하면 일반적으로 메시지 상자가 표시 되지만 <xref:System.Diagnostics.DefaultTraceListener>가 `Listeners` 컬렉션에 없으면 메시지 상자가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b989-131">예제</span><span class="sxs-lookup"><span data-stu-id="7b989-131">Example</span></span>  
 <span data-ttu-id="7b989-132">다음 예제에서는 추적 **수신기** 컬렉션에서 기본 추적 수신기를 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b989-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b989-133">참조</span><span class="sxs-lookup"><span data-stu-id="7b989-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="7b989-134">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7b989-134">Trace and Debug Settings Schema</span></span>](index.md)
