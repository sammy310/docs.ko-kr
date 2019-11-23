---
title: <sharedListeners> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: b419ecf451b79808e545525c7b8761175f390200
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699298"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="1577b-102">\<sharedListeners > 요소</span><span class="sxs-lookup"><span data-stu-id="1577b-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="1577b-103">소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="1577b-104">이러한 수신기는 기본적으로 추적을 수신 하지 않으며 런타임에 이러한 수신기를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="1577b-105">공유 수신기로 식별 된 수신기는 이름으로 원본 또는 추적에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[<span data-ttu-id="1577b-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1577b-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1577b-107">&nbsp;[ **\<&nbsp;진단 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="1577b-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="1577b-108">&nbsp;&nbsp;&nbsp; **\<sharedListeners &nbsp;>**</span><span class="sxs-lookup"><span data-stu-id="1577b-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1577b-109">구문</span><span class="sxs-lookup"><span data-stu-id="1577b-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1577b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1577b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1577b-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1577b-112">특성</span><span class="sxs-lookup"><span data-stu-id="1577b-112">Attributes</span></span>  
 <span data-ttu-id="1577b-113">None.</span><span class="sxs-lookup"><span data-stu-id="1577b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1577b-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1577b-114">Child Elements</span></span>  
  
|<span data-ttu-id="1577b-115">요소</span><span class="sxs-lookup"><span data-stu-id="1577b-115">Element</span></span>|<span data-ttu-id="1577b-116">Description</span><span class="sxs-lookup"><span data-stu-id="1577b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1577b-117">\<add></span><span class="sxs-lookup"><span data-stu-id="1577b-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="1577b-118">`sharedListeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1577b-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1577b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1577b-120">요소</span><span class="sxs-lookup"><span data-stu-id="1577b-120">Element</span></span>|<span data-ttu-id="1577b-121">Description</span><span class="sxs-lookup"><span data-stu-id="1577b-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="1577b-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1577b-123">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1577b-124">주의</span><span class="sxs-lookup"><span data-stu-id="1577b-124">Remarks</span></span>  
 <span data-ttu-id="1577b-125">수신기를 공유 수신기 컬렉션에 추가 해도 활성 수신기로 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="1577b-126">추적 소스를 해당 추적 요소에 대 한 `Listeners` 컬렉션에 추가 하 여 추적 소스 나 추적에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="1577b-127">.NET Framework의 수신기 클래스는 <xref:System.Diagnostics.TraceListener> 클래스에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="1577b-128">이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1577b-129">예제</span><span class="sxs-lookup"><span data-stu-id="1577b-129">Example</span></span>  
 <span data-ttu-id="1577b-130">다음 예제에서는 `<sharedListeners>` 요소를 사용 하 여 <xref:System.Diagnostics.TraceSource> 및 <xref:System.Diagnostics.Trace> 클래스에 대 한 `Listeners` 컬렉션에 `console` 수신기를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="1577b-131">콘솔 추적 수신기는 <xref:System.Diagnostics.TraceSource> 또는 <xref:System.Diagnostics.Trace>호출을 통해 추적 정보를 콘솔에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="1577b-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="1577b-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1577b-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="1577b-133">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="1577b-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1577b-134">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="1577b-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
