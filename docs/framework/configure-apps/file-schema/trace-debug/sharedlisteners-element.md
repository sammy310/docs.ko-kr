---
description: '다음에 대 한 자세한 정보: <sharedListeners> 요소'
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
ms.openlocfilehash: 904648754c99464e1109a04a5a19b52ec1a1cace
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750561"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="98399-103">\<sharedListeners> 요소</span><span class="sxs-lookup"><span data-stu-id="98399-103">\<sharedListeners> Element</span></span>

<span data-ttu-id="98399-104">소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98399-104">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="98399-105">이러한 수신기는 기본적으로 추적을 수신 하지 않으며 런타임에 이러한 수신기를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98399-105">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="98399-106">공유 수신기로 식별 된 수신기는 이름으로 원본 또는 추적에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98399-106">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a><span data-ttu-id="98399-107">구문</span><span class="sxs-lookup"><span data-stu-id="98399-107">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98399-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="98399-108">Attributes and Elements</span></span>  

 <span data-ttu-id="98399-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="98399-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98399-110">특성</span><span class="sxs-lookup"><span data-stu-id="98399-110">Attributes</span></span>  

 <span data-ttu-id="98399-111">없음</span><span class="sxs-lookup"><span data-stu-id="98399-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="98399-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="98399-112">Child Elements</span></span>  
  
|<span data-ttu-id="98399-113">요소</span><span class="sxs-lookup"><span data-stu-id="98399-113">Element</span></span>|<span data-ttu-id="98399-114">설명</span><span class="sxs-lookup"><span data-stu-id="98399-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="98399-115">`sharedListeners` 컬렉션에 수신기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="98399-115">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98399-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="98399-116">Parent Elements</span></span>  
  
|<span data-ttu-id="98399-117">요소</span><span class="sxs-lookup"><span data-stu-id="98399-117">Element</span></span>|<span data-ttu-id="98399-118">설명</span><span class="sxs-lookup"><span data-stu-id="98399-118">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="98399-119">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="98399-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="98399-120">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="98399-120">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98399-121">설명</span><span class="sxs-lookup"><span data-stu-id="98399-121">Remarks</span></span>  

 <span data-ttu-id="98399-122">수신기를 공유 수신기 컬렉션에 추가 해도 활성 수신기로 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98399-122">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="98399-123">추적 소스를 `Listeners` 해당 추적 요소에 대 한 컬렉션에 추가 하 여 추적 소스 나 추적에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98399-123">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="98399-124">.NET Framework의 수신기 클래스는 클래스에서 파생 <xref:System.Diagnostics.TraceListener> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98399-124">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="98399-125">이 요소는 컴퓨터 구성 파일 (Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98399-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98399-126">예제</span><span class="sxs-lookup"><span data-stu-id="98399-126">Example</span></span>  

 <span data-ttu-id="98399-127">다음 예제에서는 요소를 사용 하 여 `<sharedListeners>` `console` `Listeners` 및 클래스의 컬렉션에 수신기를 추가 하는 방법을 보여 줍니다 <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> .</span><span class="sxs-lookup"><span data-stu-id="98399-127">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="98399-128">콘솔 추적 수신기는 또는에 대 한 호출을 통해 추적 정보를 콘솔에 씁니다 <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> .</span><span class="sxs-lookup"><span data-stu-id="98399-128">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98399-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98399-129">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="98399-130">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="98399-130">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="98399-131">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="98399-131">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
