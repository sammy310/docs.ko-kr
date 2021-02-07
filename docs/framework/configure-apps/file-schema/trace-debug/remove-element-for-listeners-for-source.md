---
description: '자세히 알아보기: <remove> 의에 대 한 요소 <listeners><source>'
title: <remove>의에 대 한 요소 <listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 2f7a815fe97fda95d71bc2a5a1b8fdda7bc2a0ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750626"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="fbaf2-103">\<remove>의에 대 한 요소 \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="fbaf2-103">\<remove> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="fbaf2-104">추적 소스의 `Listeners` 컬렉션에서 수신기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-104">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="fbaf2-105">구문</span><span class="sxs-lookup"><span data-stu-id="fbaf2-105">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbaf2-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fbaf2-106">Attributes and Elements</span></span>  

 <span data-ttu-id="fbaf2-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbaf2-108">특성</span><span class="sxs-lookup"><span data-stu-id="fbaf2-108">Attributes</span></span>  
  
|<span data-ttu-id="fbaf2-109">attribute</span><span class="sxs-lookup"><span data-stu-id="fbaf2-109">Attribute</span></span>|<span data-ttu-id="fbaf2-110">설명</span><span class="sxs-lookup"><span data-stu-id="fbaf2-110">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="fbaf2-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="fbaf2-112">컬렉션에서 제거할 수신기의 이름입니다 `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="fbaf2-112">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbaf2-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fbaf2-113">Child Elements</span></span>  

 <span data-ttu-id="fbaf2-114">없음</span><span class="sxs-lookup"><span data-stu-id="fbaf2-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbaf2-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fbaf2-115">Parent Elements</span></span>  
  
|<span data-ttu-id="fbaf2-116">요소</span><span class="sxs-lookup"><span data-stu-id="fbaf2-116">Element</span></span>|<span data-ttu-id="fbaf2-117">설명</span><span class="sxs-lookup"><span data-stu-id="fbaf2-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fbaf2-118">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fbaf2-119">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-119">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="fbaf2-120">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-120">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="fbaf2-121">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-121">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="fbaf2-122">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-122">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbaf2-123">설명</span><span class="sxs-lookup"><span data-stu-id="fbaf2-123">Remarks</span></span>  

 <span data-ttu-id="fbaf2-124">`<remove>`요소는 `Listeners` 추적 소스에 대 한 컬렉션에서 지정 된 수신기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-124">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="fbaf2-125">`Listeners` <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> 인스턴스의 속성에서 메서드를 호출 하 여 프로그래밍 방식으로 추적 소스에 대 한 컬렉션에서 요소를 제거할 수 있습니다 <xref:System.Diagnostics.TraceSource.Listeners%2A> <xref:System.Diagnostics.TraceSource> .</span><span class="sxs-lookup"><span data-stu-id="fbaf2-125">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="fbaf2-126">이 요소는 컴퓨터 구성 파일 (Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbaf2-126">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbaf2-127">예제</span><span class="sxs-lookup"><span data-stu-id="fbaf2-127">Example</span></span>  

 <span data-ttu-id="fbaf2-128">다음 예제에서는 `<remove>` 요소를 사용 하 여 `<add>` `console` `Listeners` 추적 소스에 대 한 컬렉션에 수신기를 추가 하기 전에 요소를 사용 하는 방법을 보여 줍니다 `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="fbaf2-128">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fbaf2-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbaf2-129">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="fbaf2-130">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="fbaf2-130">Trace and Debug Settings Schema</span></span>](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="fbaf2-131">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="fbaf2-131">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
