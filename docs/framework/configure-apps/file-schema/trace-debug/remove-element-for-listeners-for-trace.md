---
title: <remove>의에 대 한 요소 <listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: f06973ec30d5061e4a200d6bf7e68adcf6302018
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088839"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="eb856-102">\<remove>의에 대 한 요소 \<listeners>\<trace></span><span class="sxs-lookup"><span data-stu-id="eb856-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="eb856-103">**수신기 컬렉션에서** 수신기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-103">Removes a listener from the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="eb856-104">구문</span><span class="sxs-lookup"><span data-stu-id="eb856-104">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb856-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eb856-105">Attributes and Elements</span></span>  
 <span data-ttu-id="eb856-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb856-107">특성</span><span class="sxs-lookup"><span data-stu-id="eb856-107">Attributes</span></span>  
  
|<span data-ttu-id="eb856-108">attribute</span><span class="sxs-lookup"><span data-stu-id="eb856-108">Attribute</span></span>|<span data-ttu-id="eb856-109">Description</span><span class="sxs-lookup"><span data-stu-id="eb856-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb856-110">**name**</span><span class="sxs-lookup"><span data-stu-id="eb856-110">**name**</span></span>|<span data-ttu-id="eb856-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="eb856-112">**Listeners** 컬렉션에서 제거할 수신기의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-112">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb856-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eb856-113">Child Elements</span></span>  
 <span data-ttu-id="eb856-114">없음</span><span class="sxs-lookup"><span data-stu-id="eb856-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb856-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eb856-115">Parent Elements</span></span>  
  
|<span data-ttu-id="eb856-116">요소</span><span class="sxs-lookup"><span data-stu-id="eb856-116">Element</span></span>|<span data-ttu-id="eb856-117">Description</span><span class="sxs-lookup"><span data-stu-id="eb856-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eb856-118">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="eb856-119">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-119">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="eb856-120">수신기는 추적 출력을 적절 한 대상으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-120">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="eb856-121">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="eb856-122">ASP.NET 추적 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-122">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb856-123">설명</span><span class="sxs-lookup"><span data-stu-id="eb856-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb856-124">컬렉션에서를 제거 하면 <xref:System.Diagnostics.DefaultTraceListener> `Listeners` ,, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 및 메서드의 동작이 변경 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-124">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="eb856-125">또는 메서드를 호출 하면 `Assert` `Fail` 일반적으로 메시지 상자가 표시 되지만 <xref:System.Diagnostics.DefaultTraceListener> 가 컬렉션에 없으면 메시지 상자가 표시 되지 않습니다 `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="eb856-125">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb856-126">예제</span><span class="sxs-lookup"><span data-stu-id="eb856-126">Example</span></span>  
 <span data-ttu-id="eb856-127">다음 예제에서는 추적 **수신기** 컬렉션에서 기본 추적 수신기를 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb856-127">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eb856-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb856-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="eb856-129">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="eb856-129">Trace and Debug Settings Schema</span></span>](index.md)
