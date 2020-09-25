---
title: <remove>의에 대 한 요소 <listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 53ba773ea1cb31955e59c1f57e1c0cc807227402
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173875"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="cff7d-102">\<remove>의에 대 한 요소 \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="cff7d-102">\<remove> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="cff7d-103">추적 소스의 `Listeners` 컬렉션에서 수신기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cff7d-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="cff7d-104">구문</span><span class="sxs-lookup"><span data-stu-id="cff7d-104">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cff7d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cff7d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="cff7d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cff7d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cff7d-107">특성</span><span class="sxs-lookup"><span data-stu-id="cff7d-107">Attributes</span></span>  
  
|<span data-ttu-id="cff7d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="cff7d-108">Attribute</span></span>|<span data-ttu-id="cff7d-109">설명</span><span class="sxs-lookup"><span data-stu-id="cff7d-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="cff7d-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="cff7d-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="cff7d-111">컬렉션에서 제거할 수신기의 이름입니다 `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="cff7d-111">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cff7d-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cff7d-112">Child Elements</span></span>  

 <span data-ttu-id="cff7d-113">없음</span><span class="sxs-lookup"><span data-stu-id="cff7d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cff7d-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cff7d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="cff7d-115">요소</span><span class="sxs-lookup"><span data-stu-id="cff7d-115">Element</span></span>|<span data-ttu-id="cff7d-116">설명</span><span class="sxs-lookup"><span data-stu-id="cff7d-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cff7d-117">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cff7d-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="cff7d-118">메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cff7d-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="cff7d-119">추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff7d-119">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="cff7d-120">추적 메시지를 시작하는 추적 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cff7d-120">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="cff7d-121">메시지를 수집, 저장 및 라우팅하는 수신기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff7d-121">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cff7d-122">설명</span><span class="sxs-lookup"><span data-stu-id="cff7d-122">Remarks</span></span>  

 <span data-ttu-id="cff7d-123">`<remove>`요소는 `Listeners` 추적 소스에 대 한 컬렉션에서 지정 된 수신기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff7d-123">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="cff7d-124">`Listeners` <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> 인스턴스의 속성에서 메서드를 호출 하 여 프로그래밍 방식으로 추적 소스에 대 한 컬렉션에서 요소를 제거할 수 있습니다 <xref:System.Diagnostics.TraceSource.Listeners%2A> <xref:System.Diagnostics.TraceSource> .</span><span class="sxs-lookup"><span data-stu-id="cff7d-124">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="cff7d-125">이 요소는 컴퓨터 구성 파일 (Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff7d-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cff7d-126">예제</span><span class="sxs-lookup"><span data-stu-id="cff7d-126">Example</span></span>  

 <span data-ttu-id="cff7d-127">다음 예제에서는 `<remove>` 요소를 사용 하 여 `<add>` `console` `Listeners` 추적 소스에 대 한 컬렉션에 수신기를 추가 하기 전에 요소를 사용 하는 방법을 보여 줍니다 `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="cff7d-127">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cff7d-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cff7d-128">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="cff7d-129">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="cff7d-129">Trace and Debug Settings Schema</span></span>](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="cff7d-130">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="cff7d-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
